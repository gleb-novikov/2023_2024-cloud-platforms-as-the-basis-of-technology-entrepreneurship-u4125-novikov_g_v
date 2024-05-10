# Лабораторная работа №5 «Интеграция Jira и GitHub»

> [!NOTE]
> University: [ITMO University](https://itmo.ru/ru/)</br>
> Faculty: [FICT](https://fict.itmo.ru)</br>
> Course: [Cloud platforms as the basis of technology entrepreneurship](https://itmo-ict-faculty.github.io/cloud-platforms-as-the-basis-of-technology-entrepreneurship/)</br>
> Year: 2023/2024</br>
> Group: U4125</br>
> Author: Novikov Gleb Vitalevich</br>
> Lab: Lab5</br>
> Date of create: 10.05.2024</br>
> Date of finished: 10.05.2024</br>

## Цель работы
Интегрировать таск-трекинг в работу с багами/фичами в GitHub.

## Ход работы

`2.` Создать Team-managed Scrum проект.

<img width="1728" alt="image" src="https://github.com/gleb-novikov/2023_2024-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-novikov_g_v/assets/57367667/d2907d2f-58eb-4441-948e-d9d5890e5061">

`3.` Добавить в проект фичи Backlog и Code как минимум. Создать колонку On Check.

<img width="1728" alt="image" src="https://github.com/gleb-novikov/2023_2024-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-novikov_g_v/assets/57367667/fefde646-d1b4-4ded-ab1f-89ea5588c8de">

`4.` Заполнить бэклог парой задач.

<img width="1728" alt="image" src="https://github.com/gleb-novikov/2023_2024-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-novikov_g_v/assets/57367667/57f1259d-c61c-427f-913c-55516ff18628">

`5.` Привязать свой GitHub аккаунт и свой GitHub репозиторий, над которым Вы работаете.

<img width="1728" alt="image" src="https://github.com/gleb-novikov/2023_2024-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-novikov_g_v/assets/57367667/96679a2d-ccad-49b6-955a-0c94c0d7c626">

`6.1.` При создании ветки на GitHub, посвященной тикету (см нейминг веток), автоматически перемещать тикет в In Progress.

<img width="1728" alt="image" src="https://github.com/gleb-novikov/2023_2024-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-novikov_g_v/assets/57367667/1630b76a-c703-4716-93bf-247dc2072c72">

`6.2.` При создании PR в dev ветки, посвященной тикету, автоматически перемещать тикет в On Check.

<img width="1728" alt="image" src="https://github.com/gleb-novikov/2023_2024-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-novikov_g_v/assets/57367667/58446fa9-6cb5-40b7-9ff2-b4ae61439657">

`6.3.` При мердже ветки перемещать тикет в Done.

<img width="1728" alt="image" src="https://github.com/gleb-novikov/2023_2024-cloud-platforms-as-the-basis-of-technology-entrepreneurship-u4125-novikov_g_v/assets/57367667/e4212aa0-b40c-44fb-a1e1-172d28dad308">

### Тестирование

7. Создать тикет (или issue на GitHub, тогда проверить, что задача появилась в Backlog)
8. Переместить задачу в спринт, начать спринт, настроить его согласно своим желаниям
9. Создать на GitHub ветку, посвященную тикету, проверить, что ее статус в Jira перешел в In Progress. Обратите внимание, что ветку нужно создать силами CLI/IDE, а не из Jira.
10. Создать PR ветки в dev, проверить, что статус тикета в Jira перешел в On Check
11. Принять PR, проверить, что статус тикета - Done
