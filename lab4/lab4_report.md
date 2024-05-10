# Лабораторная работа №4 «Разработка инфраструктуры MVP AI приложения»

> [!NOTE]
> University: [ITMO University](https://itmo.ru/ru/)</br>
> Faculty: [FICT](https://fict.itmo.ru)</br>
> Course: [Cloud platforms as the basis of technology entrepreneurship](https://itmo-ict-faculty.github.io/cloud-platforms-as-the-basis-of-technology-entrepreneurship/)</br>
> Year: 2023/2024</br>
> Group: U4125</br>
> Author: Novikov Gleb Vitalevich</br>
> Lab: Lab4</br>
> Date of create: 10.05.2024</br>
> Date of finished: 10.05.2024</br>

## Цель работы
Создать прототип AI-приложения с базовой функциональностью.

## Ход работы

### Описание

Web сервис для классификации фотографий документов с помощью Vision API. С помощью которого, сотрудник организации может отсканировать бумажный документ во время инвентаризации, классифицировать его с помощью искусственного интеллекта и получить информацию по нему из базы данных.

### Архитектура

![image](https://github.com/gleb-novikov/2023_2024-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-novikov_g_v/assets/57367667/ff1a01b9-2629-4926-a7d5-1115651181fd)

**Компоненты системы:**

- `Cloud Load Balancing` – для маршрутизирования трафика на web сервис
- `Cloud Storage` – для хостинга статики Frontend и хранения изображений документов
- `Cloud Run` – backend сервиса с реализацией всей бизнес-логики
- `Cloud SQL` – SQL база данных для хранения пользователей и информации о разных типах документов
- `Vision API` – AI сервис для работы с изображениями
- `Monitoring` – инструмент для мониторинга основных оказателей web сервиса

### Нагрузка

Один пользователь за день обрабатывает около 100 изображений, каждое из которых в среднем весит 1 мб. Соотвественно `1 пользователь` `в день` создаёт ~ `100 мб трафика`.

На этапе тестирования сервиса была привлечена 1 организация с 3 сотрудниками. На этапе продакшена было подключено 10 организаций, каждая из которых имела по 5 сотрудников.

### Стоимость

#### Cloud Load Balancing

$0.025 / h = **`$18 / month`**

[Источник](https://cloud.google.com/vpc/network-pricing)

#### Cloud Storage

*US (United States multi-region) | Standard storage*

`$0.000026 / mb` (1 изображение)

$0.01 / 1000 operations = `$0.00002 / 2 operations` (запись и чтение 1 изображения)

**`$0.0046 / image`** (взаимодействие с 1 изображением)

[Источник](https://cloud.google.com/storage/pricing)

#### Cloud Run

$0.000018 / vCPU-second = `$0.00009 / image` (обработка запросов на 1 изображение занимает 5 секунд)

$0.000002 / GiB-second = `$0.00001 / image` (обработка запросов на 1 изображение занимает 5 секунд)

**`$0.0001 / image`** (обработка 1 изображения)

[Источник](https://cloud.google.com/run/pricing)

#### Cloud SQL

`$30.149 per vCPU / month`

`$5.11 per GB / month`

**`$35.259 / month`**

[Источник](https://cloud.google.com/sql/pricing)

#### Vision API

*Document Text Detection*

$1.50 / 1000 images = **`$0.0015 / image`**

[Источник](https://cloud.google.com/vision/pricing)

#### Monitoring

Бестплатно, т.к. планируется использовать только стандартные метрики Google Cloud.

[Источник](https://cloud.google.com/stackdriver/pricing#monitoring-costs)

#### Итого

- `$53.259 / месяц`
- \+ `$0.0062 обработка 1 изображения`

### Расчёты

**Начальное** (100 документов в месяц) – `$53.879 / month`

**Тестирование** (9000 документов в месяц) – `$109.059 / month`

**Продакшн** (150,000 документов в месяц) – `$983.259 / month`

## Выводы

Предложенная архитектура на основе связки Cloud Run и Cloud SQL не является выгодной на начальных этапах, и эти компоненты можно было бы заменить на одну виртуальную машину. Но при увеличении нагрузки, система в текущей реализации легко масштабируема, а основные расходы при обработке документов будут в сервисе Vision API.
