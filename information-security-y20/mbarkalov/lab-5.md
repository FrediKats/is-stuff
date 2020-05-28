МИНИСТЕРСТВО НАУКИ И ВЫСШЕГО ОБРАЗОВАНИЯ РОССИЙСКОЙ ФЕДЕРАЦИИ

ФЕДЕРАЛЬНОЕ ГОСУДАРСТВЕННОЕ АВТОНОМНОЕ ОБРАЗОВАТЕЛЬНОЕ УЧРЕЖДЕНИЕ
ВЫСШЕГО ОБРАЗОВАНИЯ

«Санкт-Петербургский национальный исследовательский университет\
информационных технологий механики и оптики»

Факультет информационных технологий и программирования

Лабораторная работа №5

**\
Управление SQL сервером**

**\
\
\
\
\
\
\
**

> Выполнили\
> студент группы М3405\
> Баркалов Максим Максимович\
> \
> студент группы М3403\
> Шипкова Мария Александровна
>
> Проверил:\
> Хегай Максим Вилорьевич

Санкт-Петербург\
2020

1.  Скрипты создания таблиц БД

> CREATE TABLE Users
>
> (
>
> userID INT,
>
> userLogin VARCHAR(25),
>
> passHash VARCHAR(40),
>
> email VARCHAR(35),
>
> status INT,
>
> PRIMARY KEY (userID)
>
> );\
> CREATE TABLE News
>
> (
>
> newsID INT,
>
> header NTEXT,
>
> newsText NTEXT,
>
> allowComment BIT,
>
> newsDate SMALLDATETIME,
>
> userID INT FOREIGN KEY REFERENCES Users (userID),
>
> PRIMARY KEY (newsID)
>
> );
>
> CREATE TABLE Comments
>
> (
>
> commentID INT,
>
> commentDate SMALLDATETIME,
>
> commentText NTEXT,
>
> userID INT FOREIGN KEY REFERENCES Users (userID),
>
> newsID INT FOREIGN KEY REFERENCES News (newsID),
>
> PRIMARY KEY (commentID)
>
> );
>
> Хранимая процедура, получить комментарии пользователя

create procedure getUserComments

\@who nvarchar(50)

as

begin

declare \@num int

select \@num=userID from Users where userLogin=\@who

select commentText from Comments where userID=\@num

end

2.  Создание имен входа

Создание имени входа с проверкой на уровне ОС -- тут не требуется логин
и пароль при подключении к серверу, проверка выполняется на уровне входа
в ОС

﻿CREATE LOGIN \[MAX-ПК\\test\] FROM WINDOWS;

GO

Создание имени входа с проверкой на сервере -- тут потребуется ввод
логина и пароля

﻿

CREATE LOGIN testuserpasswordauth

WITH PASSWORD = \'123654\'

GO

При этом должна быть активна настройка

![Изображение выглядит как снимок экрана Автоматически созданное
описание](./lab-5//media/image1.png){width="6.491666666666666in"
height="3.0229166666666667in"}

3.  С помощью среды

> ![Изображение выглядит как снимок экрана Автоматически созданное
> описание](./lab-5//media/image2.png){width="4.541176727909011in"
> height="4.089876421697288in"}
>
> ![Изображение выглядит как снимок экрана Автоматически созданное
> описание](./lab-5//media/image3.png){width="4.529411636045494in"
> height="4.053600174978127in"}

4.  Пользователи

Роль сервера --- группы для управления правами доступа, похожи на группы
в операционной системе Windows

Существуют предопределенные:

![Изображение выглядит как снимок экрана Автоматически созданное
описание](./lab-5//media/image4.png){width="4.9509055118110235in"
height="4.741176727909012in"}

Сопоставленные пользователи требуются для имен входа: имена входа нужны
для аутентификации (проверка что пользователь является тем, за кого себя
выдаёт), пользователи для авторизации (выдача ему прав). Имени
пользователю в одной базе данных может соответствовать только один
пользователь.

Скрипты:

1.  ﻿ Имя входа testuserpasswordauth попадет в роль sysadmin и будет
    сопоставлено с пользователем labuser\
    \
    create user labuser for login testuserpasswordauth

GO

ALTER SERVER ROLE sysadmin ADD MEMBER testuserpasswordauth;

GO

2.  Имя входа (с проверкой Windows) MAX-ПК\\test2 попадет в роль
    dbcreator и будет сопоставлено с пользователем labuser2\
    \
    ﻿create user labuser2 for login \[MAX-ПК\\test2\]

GO

ALTER SERVER ROLE dbcreator ADD MEMBER MAX-ПК\\test2\];

GO

5.  GRANT\
    > \
    > Отнимем у имени входа testuserpasswordauth (который сопоставлен с
    > пользователем labuser) членство в sysadmins для проверки grant'ов\
    > \
    > ALTER SERVER ROLE sysadmin DROP MEMBER testuserpasswordauth;

```{=html}
<!-- -->
```
1.  Выдача доступа к таблице:

-   Проверим, что доступа нет\
    ![Изображение выглядит как снимок экрана Автоматически созданное
    описание](./lab-5//media/image5.png){width="2.927380796150481in"
    height="1.5084722222222222in"}\
    ﻿

-   Выполним:\
    GRANT select,insert,update,delete ON Users TO labuser

-   Доступ есть:\
    ![Изображение выглядит как снимок экрана Автоматически созданное
    описание](./lab-5//media/image6.png){width="3.450832239720035in"
    height="2.060605861767279in"}

2.  Выдача доступа к хранимой процедуре:

> ﻿GRANT execute ON getUserComments TO labuser\
> \
> Доступ появился:\
> ![Изображение выглядит как снимок экрана Автоматически созданное
> описание](./lab-5//media/image7.png){width="4.410858486439195in"
> height="2.549879702537183in"}

3.  Выдача полного доступа:\
    ﻿\
    GRANT CONTROL TO labuser\
    \
    Проверим, удалив процедуру\
    ![Изображение выглядит как снимок экрана Автоматически созданное
    описание](./lab-5//media/image8.png){width="4.239140419947507in"
    height="2.3390551181102364in"}
