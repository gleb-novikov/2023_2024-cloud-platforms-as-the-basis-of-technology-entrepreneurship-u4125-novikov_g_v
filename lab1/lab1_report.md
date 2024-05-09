# Лабораторная работа №1 «Обзор Google Cloud и исследование основных сервисов»

> [!NOTE]
> University: [ITMO University](https://itmo.ru/ru/)</br>
> Faculty: [FICT](https://fict.itmo.ru)</br>
> Course: [Cloud platforms as the basis of technology entrepreneurship](https://itmo-ict-faculty.github.io/cloud-platforms-as-the-basis-of-technology-entrepreneurship/)</br>
> Year: 2023/2024</br>
> Group: U4125</br>
> Author: Novikov Gleb Vitalevich</br>
> Lab: Lab1</br>
> Date of create: 09.05.2024</br>
> Date of finished: 09.05.2024</br>

## Цель работы
Ознакомиться с основными возможностями и преимуществами облачной платформы Google Cloud.

## Ход работы

`1.` Зайдите в вкладку IAM, создайте service account с ролью `Storage Admin`.

<img width="1317" alt="image" src="https://github.com/gleb-novikov/2023_2024-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-novikov_g_v/assets/57367667/2c975db2-c54a-4428-b628-ac1415fb3e68">

`2.` Создать минимальный compute engine (виртуальную машину) с Machine type `e2-micro` в режиме `Spot`.

<img width="1127" alt="image" src="https://github.com/gleb-novikov/2023_2024-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-novikov_g_v/assets/57367667/b8d2f788-60fa-4212-bed9-30d09bcf06fe">

`3.` С помощью утилиты `gsutils` найдите бакет `lab1-bucket-itmo` и скопируйте 3 файла в локальную папку на VM.

Добавили публичный SSH ключ для подключения к серверу.

<img width="1045" alt="image" src="https://github.com/gleb-novikov/2023_2024-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-novikov_g_v/assets/57367667/bfefabcb-ed2d-41b2-be16-7153c9cf0eff">

Скопировали файлы с помощью `gsutils`.

Используя команду `ls -lah` отобразите что эти файлы хранятся у вас на VM.

<img width="703" alt="image" src="https://github.com/gleb-novikov/2023_2024-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-novikov_g_v/assets/57367667/2e626ba1-3da8-494b-bc9e-e6b20ed143eb">

`4.` Поменяйте права доступа для вашего service account с `Storage Admin` на `Compute Viewer`, попробуйте повторить пункт с копированием данных, сделать выводы.

Т.к. на этапе создания виртуальной машины не было требования указывать свой service account, то автоматически был использован стандартный с ролью `Editor`.

<img width="1061" alt="image" src="https://github.com/gleb-novikov/2023_2024-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-novikov_g_v/assets/57367667/0b35fad3-e24e-4cca-a1c1-a94283697c7a">

После изменения роли на `Compute Viewer`, мы получаем ошибку при копировании данных, из-за того, что у нас отсутствуют соответствующие доступы.

<img width="591" alt="image" src="https://github.com/gleb-novikov/2023_2024-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-novikov_g_v/assets/57367667/a87880f5-08c5-4edb-8547-9146a1eb2c0e">

## Выводы

В рамках лабораторной работы изучили возможности создания аккаунтов с настройками доступов через AIM, а также создание и взаимодействие с виртуальными машинами на Google Cloud.
