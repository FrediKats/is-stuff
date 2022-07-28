# project

> “А вот iwentys похож на 1C?” (c)

Цель: ознакомиться с подходами и инструментами для организации командной работы. Применить на практике знания, разработав прототип системы, который состоит из связанных модулей, реализованных отдельными командами.

Концептуально система должна состоять из трёх модулей. Каждый модуль — это разработка команды из 3-х (по согласованию можно 4) человек.

Предпочтительным вариантом будет выбрать предметную область, которая будет интересна команде, а не брать сразу готовый пример из описания ТЗ к проекту.

<aside>
    ❗ Выбранную тему необходимо согласовать. В течение какого-то периода времени вы получите фидбек от преподавателя.
</aside>

Одно из ключевых требований к теме — это декомпозиция проекта на три подпроекта, которые могут разрабатывать отдельные команды. В качестве примеров:

1. Любая модульная CMS, в которой можно выделять границы разных зон ответственностей.
2. Магазин. Примеры модулей:
    1. Магазин (продажи): аккаунты клиентов, корзина.
    2. Склад: информации о товарах, их размещение. Возможность добавлять новые склады, контролировать поставки.
    3. Логистика: управление доставками и переводом между складами.
3. Гитхаб. Примеры модулей:
    1. VCS — отвечает за управление комитами, ветками, авторами.
    2. Управление репозиториями — репозитории, ишуи, пул реквесты. Синхронизируется с VCS (при создании PR запрашивает информацию о возможности слияния без конфликтов, при мёрдже PR отправляет запрос в VCS на мёрдж ветки).
    3. Юзер сервис — создание аккаунтов, добавление почты. Система управления репозиториями по почтам, указанным в коммитах и добавленным юзером, может мапить коммиты на аккаунты и генерировать статистику. Звёздочки на репозиториях.
4. ИСУ. Примеры модулей:
    1. Управления студнтами, группами.
    2. Управление преподавателями, их назначением.
    3. Управление аудиториями, расписанием.

## Этапы

1. Определение темы, формирование команды, согласование требований. Подготовительный этап, не оценивается баллами.
    1. Заполнить форму, указанную выше. При сборе команд стоит учитывать планы всех участников по получению баллов. Если человек планирует выполнить только первый этап, а остальные - оба, могут появиться проблемы.
    2. Создать репозиторий с названием team-N-M, где N - номер надкоманды, а M - номер команды внутри надкоманды. Эти номера вам сообщат преподаватели после согласования темы.
    3. Скорее всего, всей вашей надкоманде нужен будет доступ к каждому из репозиториев подкоманд, так что имеет смысл сразу всех добавить (свою команду с правами на запись, а остальных - на чтение).
2. Разработка PoC. Акцент на workflow, командной работе, декомпозиции и итеративности выполнения. Документация, отчёты. Первый этап, 14 баллов.
    1. Описание проекта и предметной области, способов интеграции и инструкции по развёртыванию.
    2. Проработка функционала, формально описанные фичи/юзер стори.
    3. Командная работа, использование гита, веток, пул реквестов, ревью, ишьюс, проджектов.
    4. Итеративная разработка. Подбор задач на неделю, недельные отчёты о проделанной работе.
    5. Работоспособность попротипа, его интеграция с другими модулями. Подготовка демо для демонстрации прототипа.
3. Доработки функционала, презентация MVP. Второй этап, идёт в зачёт экзамена — 20 баллов.

## Требования к описанию (Подготовительный этап)

По системе в целом ожидается описание того, как модули будут поделены и взаимодействовать.

Вариант 1. Каждый модуль - это отдельный солюшен. Если какой-то модуль зависит от другого, то он подключает его гитсабмодулем и подключает нужные проекты другого модуля себе в солюшен. Взаимодействуют модули по средствам непосредственных вызовыв в C#.  Этот вариант проще т.к. не требует использования веба, развёртывания сервисов и создания клиентов.

Вариант 2. Модуль - это отдельный сервис, который предоставляет Web API (и вероятно нюгет с клиентом). Другие модули при необходимости взаимодействуют с этим модулем вызывая методы с API. Этот вариант сложнее, если вы ранее не работали с Web API, но позволяет более независимо разрабатывать модули и минимизировать вероятность, что будет что-то сломано. Ну и также даёт возможность написать на разных языках отдельные модули.

Помимо типа взаимодействия стоит описать сам процесс взаимодействия. Самым наглядным способом является использование сиквенс диаграммы (ну или любого подобного представления). Ожидается, что будет описан порядом обращений между модулями для реализации определённого функционала. Например:

1. Пользователь отправляет команду покупки в модуль магазина через предоставляемый консольный UI
2. Модуль магазина отпраляет запрос в модуль склада и получает информацию о том, где находится ближайший склад с товаром.
3. Модуль магазина отправляет запрос в модуль логистики с информацией о том, с какого склада и куда нужно доставить товар

По каждому отдельному модулю нужно сделать:

1. Краткое описание
2. Список функционала, который точно будет в PoC
3. Список дополнительного функционала, который может попасть в PoC, если на это хватит времени
4. Список функционала, который будет готов к MVP

## Требования к ведению проекта (этап разработки PoC)

- Для проекта должен быть создан репозиторий на гитхабе. У каждой команды свой репозиторий
- Для репозитория должен быть настроен процесс разработки через ветки и пул реквесты с ревью. Можете сразу законфигать запрет пуша в мастер и требования на обязательное ревью PR.
- Описание проекта стоит добавить в ридми
- Задачи, которые выполняются дложны быть созданы ишуями. PR нужно связывать с ишуями. В задачи стоит добавлять всё то, что вы делаете для проекта, чтобы сводить к 0 задачи, котоыре не попадают. Например, настройки прав и/или настройка CI в проекта - это тоже задача вне зависимости от объема кода, который нужно сделать. Главное не забывать в задаче отписывать результат.
- Для ведения проекта создать project на котором будет отображаться прогресс по ишуям.
- Разработку стоит поделить на итерации/спринта. Для каждой итерации заводите мейлстоуны на гитхабе. Добавляйте туда те задачи, которые планируете сделать в рамках недели.
- В конце каждого спринта комнада должна написать в чате небольшой отчёт о проделанной работе. Пример:

<aside>
💡 <место для общей информаци, в каком состоянии проект, главные достижения>
Команда 1
  Человек 1
    Сделал <таска 1>, <таску 2>
Команда 2
  Человек 1
...
</aside>

## Дополнение

Все указанные требования и в целом best practice будут разбираться в ходе лекций. Не стоит волноваться, если на данном этапе нет понимания, как и куда двигаться.