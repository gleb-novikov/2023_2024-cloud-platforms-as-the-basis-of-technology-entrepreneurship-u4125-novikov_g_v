# Лабораторная работа №2 «Исследование Cloud Run»

> [!NOTE]
> University: [ITMO University](https://itmo.ru/ru/)</br>
> Faculty: [FICT](https://fict.itmo.ru)</br>
> Course: [Cloud platforms as the basis of technology entrepreneurship](https://itmo-ict-faculty.github.io/cloud-platforms-as-the-basis-of-technology-entrepreneurship/)</br>
> Year: 2023/2024</br>
> Group: U4125</br>
> Author: Novikov Gleb Vitalevich</br>
> Lab: Lab2</br>
> Date of create: 10.05.2024</br>
> Date of finished: 10.05.2024</br>

## Цель работы
Ознакомиться с работой Cloud Run.

## Ход работы

`1.` Создайте Cloud Run из представленного дефолтного сервиса Hello с минимальным количеством ресурсов.

<img width="1728" alt="image" src="https://github.com/gleb-novikov/2023_2024-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-novikov_g_v/assets/57367667/466c97d1-00e7-4418-a409-5efeef843858">

`2.` Перейдите по ссылке предоставленной Cloud Run, протестируйте сервис.

<img width="1728" alt="image" src="https://github.com/gleb-novikov/2023_2024-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-novikov_g_v/assets/57367667/9aeddf94-5e80-4ebd-83a8-e1fe3b768e22">

`3.` Перейдите в разделы логи и метрики, проанализируйте их.

В разделе `Logs` отображаются все системные логи и события, связанные с жизненным циклом сервиса.

<img width="1728" alt="image" src="https://github.com/gleb-novikov/2023_2024-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-novikov_g_v/assets/57367667/d28d4a09-51c7-4355-84a1-79f4e3fd8e8b">

В разделе `Metrics` можно отслеживать доступные метрики по сервису, такие как количество запросов, нагрузка на CPU, входящий и исходящий трафик.

<img width="1728" alt="image" src="https://github.com/gleb-novikov/2023_2024-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-novikov_g_v/assets/57367667/b458dd71-ee92-441e-b01f-58d0c86ec79e">

`4.` Измените ваш Cloud Run, поменяв порт на 8090, посмотрите что произойдет. Попробуйте попереключать трафик между версиями, сравните результаты работы.

Создаём новую версию Cloud Run с портом 8090.

<img width="1725" alt="image" src="https://github.com/gleb-novikov/2023_2024-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-novikov_g_v/assets/57367667/dcbd5882-1593-41b2-af97-790fda1ace90">

Также настраиваем рапределение трафика 50% на 50%, что означает что нагрузка между двумя Cloud Runs будет распределяться равномерно.

<img width="867" alt="image" src="https://github.com/gleb-novikov/2023_2024-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-novikov_g_v/assets/57367667/0fa34cbd-6640-48af-b6c2-399bcf8842e3">

## Выводы

Освоили работу с сервисами, работающими на Cloud Run, их версиями, метриками и распределением трафика.
