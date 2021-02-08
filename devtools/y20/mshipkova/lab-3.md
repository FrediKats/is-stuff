МИНИСТЕРСТВО ОБРАЗОВАНИЯ И НАУКИ РОССИЙСКОЙ ФЕДЕРАЦИИ\
ФЕДЕРАЛЬНОЕ ГОСУДАРСТВЕННОЕ АВТОНОМНОЕ ОБРАЗОВАТЕЛЬНОЕ УЧРЕЖДЕНИЕ
ВЫСШЕГО ОБРАЗОВАНИЯ

«Санкт-Петербургский национальный исследовательский университет

информационных технологий, механики и оптики»

Факультет информационных технологий и программирования

Кафедра информационных систем

Лабораторная работа № 3

Команды Git

> Выполнили студенты:\
> Шипкова Мария M3303
>
> Проверил:
>
> Липкин Евгений Олегович

САНКТ--ПЕТЕРБУРГ

2018

Общие ключи

-q/-quite - вывод только ошибок и предупреждений, игнорируя остальную
информацию -v/\--verbose - вывод более детальной информации\
-z/\--null - заканчивать вывод информации NUL-чаром вместо переноса
строки\
-p / \--patch - открывает интерфейс патча

-f/\--force - игнорирование конфликтов, несмотря на возможную потери
данных \--progress - выводить прогресса в stderr\
\--dry-run - имитирует выполнение команды и выводит логи

config - конфигурация гита (имя пользователя, текстовый редактор)

\- \--replace-all (замена всех переменных, подходящих под данную
регулярку)

\- \--add (добавляет строку настройки без изменения уже существующих
настроек) - \--get / \--get-all (получение значения / всех значений по
ключу)

\- \--unset/\--unset-all (удалить переменную / все переменные,
подходящие под данную регулярку)

\- \--rename-section/\--remove-section (переименование/удаление секции)

\- -l/\--list (список всех настроек в конфиг-файле)

\- -e/\--edit (открывает редактор для редактирования конфиг-файла)

\- \--global (установка настроек для пользователя, файл \~/.gitconfig)

\- \--system (установка настроек системы, файл /etc/.gitconfig)

\- \--local (установка настроек в локальном репозитории)

init - создание пустого git-репозитория\
\--bare - создание bare-репозитория\
\--template=\<template\_directory\> - директория с которой будут
скопированы файлы перед клонированием\
\--separate-git-dir=\<git dir\> - указание пути для папки .git/.
По-умолчанию создается в корне репозитория.\
clone \<url\> \<dir\> - клонирование репозитория в новую папку\
-l/-local - клонирование локального репозитория\
\--reference \<repository\> - использовать ссылки на другой локальный
репозиторий вместо клонирования\
-n/\--no-checkout - не выполнять команду checkout по завершению
клонирования\
\--bare - создание bare-репозитория\
-o/\--origin \<name\> - указание имя для \< upstream \>. По-умолчанию -
это origin

-b/\--branch - указать ветку на которую будет ссылаться HEAD.
По-умолчанию делает такой же, как и в клонируемом репозитории\
\--recurse-submodules - рекурсивная инициализация и клонирование
сабмодулей

\--separate-git-dir=\<git dir\> - указание пути для папки .git/.
По-умолчанию создается в корне репозитория.\
\--dissociate (позволяет отделить репозиторий, склонированный через
\--reference)

add \<filename\> - добавление файлов в индекс\
-i/\--interactive (смотреть пикчу(!); интерактивно добавить
модифицированный контент в рабочее дерево к индексу)\
\--edit - открывает diff с индексом в редакторе и дает пользователю
отредактировать его

\--update - обновляет сущности, которые уже в индексе или удаляет их, но
не добавляет новые\
-A/\--all/\--no-ignore-removal - добавить изменение всех индексируемых и
не индексируемых файлов\
\--no-all/\--ignore-removal - добавить изменение всех индексируемых, но
игнорировать удалённые из индекса файлы

\--refresh - не добавляет файлы, только обновляет информацию в индексе
\--ignore-errors - игнорировать ошибки при добавлении и продолжать
добавлять \--renormalize - удалить и добавить все файлы индекс

status - показывает статус рабочего дерева и состояния файлов\
-s/\--short - вывод в коротком формате\
-b/\--branch - отобразить информацию о ветке игнорирую -s\
\--long - вывод всех инофрмации. По-умолчанию
\--ignore-submodules\[=\<when\>\] - игнорировать изменения в сабмодулях
\--\[no-\]renames - использует/не использует трекинг переименований

diff \<objname\> \<objname\> - показывает разницу между
коммитами/ветками -s/\--no-patch - не выводить патч\
\--raw - вывод diff в формате plain text\
\--minimal - более долгий анализ для генерации минимально возможного
diff \--stat - показывает список файлов с изменениями

\--summary - вывод расширенной информации о файле вроде создания,
переименования или изменения прав на доступ\
\--name-only - отображать только название измененных файлов\
\--name-status - отображать только имя и статус измененных файлов

\--no-renames - отключить поиск переименованных файлов\
\--check - предупреждает, если существуют ошибки с пробелами (например
строки исключительно из пробелов)\
\--cached/\--staged - вывод diff между коммитом и заиндексированным
состоянием (git add)\
\--no-index - позволяет сравнить неиндексируемые файлы

commit (создание коммита т.е. фиксация некого состояние репозитория)\
-a/\--all - автоматически застейджить и закомитить все файлы, которые
были изменены или удалены\
-c/\--reedit-message=\<commit\> - изменить сообщение коммита\
\--reset-author -при изменение коммита меняется автор на того, кто менял
коммит \--author=\<author\> (указать автора)\
\--date=\<date\> (указать дату коммита)\
-m \< msg \>/\--message \< msg \> (указание сообщение коммита)\
-F \< file \>/\--file=\< file \> (взять сообщение коммита из файла)\
\--allow-empty (возможность создания пустого коммита)\
\--allow-empty-message (разрешает коммиты без сообщений)\
-e/\--edit (позволяет изменить сообщение, которое получено с -F/-m/-C)\
\--no-edit (не открывать редактор сообщения коммита)\
\--amend (отмена предыдущего коммита, создание нового на основании
сделанного и новых изменений)\
-o/\--only (коммитить только указанный файл) - \--\[no-\]status -
выводит/не выводит статус как в git status

reset \<hash\> - перемещение head, индекса и рабочего дерева до
указанного коммита \--soft - сбросить только HEAD\
\--mixed - сбросить HEAD, индекс не переносится (но отображается, как
unstaged) \--hard - сбросить HEAD и индекс и рабочее дерево

![page2image42014912](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42022784](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42015488](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42022016](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page2image42024512](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42022208](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42024704](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42021632](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42024320](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42012992](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page2image42008768](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42009728](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42012800](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42413504](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42412928](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42412736](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42412544](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42412352](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42413120](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42403328](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42402368](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42404480](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page2image42413312](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42404864](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42405056](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42405248](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42404672](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42405632](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42405440](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42406016](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42405824](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42406784](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42406208](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42407360](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42407168](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42406976](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page2image42407744](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42407552](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page2image42407936](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}

\--keep - сбросить HEAD, но сохранить изменения локально

![page2image42408128](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}

rm \<filename\> - удаление файла из рабочего дерева и индекса\
-r - разрешает рекурсивное удаление, если указано название папки
\--cached - удалить только из индекса

rebase \<branchname\> - перемещение коммитов из ветки на последний
коммит другой ветки \--autostash - сохраняет состояние рабочего дерева
перед rebase\
\--fork-point - ищет наилучшего предка для веток\
-r/\--rebase-merges - попытка пересоздать слияния после rebase, чтобы
сохранить структуру дерева

-p/\--preserve-merges - попытка сохранить структуру дерева со слияниями\
\--no-ff, -f, \--force-rebase - перемещение коммитов по одному, сохраняя
историю коммитов \--allow-empty-message - позволяет пустые сообщения\
\--\[no-\]stat - показывать/ не показывать diff\
\--verify - разрешает прекоммитные хуки\
-c - продолжить после конфликта\
Действия: \--continue, abort, skip,quit

branch (выполнение различных операций с ветками)\
-a/\--all - выводит список всех локальных и удалённых-индексируемых
веток -r - remote ветки\
-d/\--delete удалить смёрженную ветку\
-D - удалить ветку, даже если не было merge\
-m/\--move - перемещает/переименовывает ветку\
-i - игнорирует регистр\
-u \[remote branch\] - связывает текущую ветку с удаленной\
\--list - вывести список названий веток\
\--create-reflog - создаёт историю перемещения HEAD для ветки

checkout - переключение между ветками\
-b \< new\_branch \> - создание новой ветки и переход в неё\
-t/\--track \< remote\_branch \> - создаст новую ветку связанную с
удаленной (с таким же именем)\
-l - создание истории изменения HEAD (reflog)\
\--merge - переходит в ветку и сливает изменения с ней

merge \<branchname\> - слияние веток (историй разработки)\
\--\[no-\]commit - установка флага, нужно ли комитить изменения после
вынужденного мерджа при пуле.\
-e/\--\[no-\]edit - открыть редактор до комита после мерджа\
\--\[no-\]ff - если можно резолвить конфликт fast-forward\'ом, то
обновляет указатель на ветку не создавая мердж-коммита\
\--ff-only - создавать мердж-комит, даже если можно резолвить
fast-forward\'ом -n/\--\[no-\]stat - выводить diff-статистику в конце
мерджа. -n = \--no-stat \--\[no-\]squash - сквошить комиты один вместо
мерджа\
\--\[no-\]autostash - делает stash перед выполнением merge\
-m \<msg\> - сообщение для комита, что будет создан при мердже\
\--abort, \--continue - прервать/ продолжить текущий резолвинг конфликта

stash - сохранение изменений локально без комита list - список stash\'ей

![page3image42360320](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page3image42360128](./lab-3//media/image4.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42359744](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42356288](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page3image42353408](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42353600](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42353792](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42353984](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42354176](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42354368](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42354560](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42354752](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42354944](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42355136](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42355328](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page3image42355520](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42355712](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42355904](./lab-3//media/image4.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42353024](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42356480](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42356672](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42356096](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42356864](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42357056](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42357248](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page3image42357440](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42357632](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42357824](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42358016](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42358208](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page3image42358400](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42358592](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42358784](./lab-3//media/image5.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42358976](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42359168](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42359936](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42361280](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42362624](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42342592](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page3image42352000](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page3image42351808](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}

apply - применить изменения из stash

![page3image42350848](./lab-3//media/image5.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}

drop - удалить stash\
show \[\<stash\>\] - показывает diff между stash и последним коммитом\
branch \<branchname\> \[\<stash\>\] - создает ветку branchname и
применяет туда изменения из stash\
clear - удаление все stash\'ы

tag (создание, удаление и проверка тега объекта)\
-a/\--annotate - создаёт аннотированный объект без подписи\
-d/\--delete - удаление тегов с указанными именами\
-l/\--list \<pattern\> - вывод тегов по шаблону\
\--sort=\<key\> - сортировка на основе заданного ключа\
\--points-at \<object\> - выбрать теги, которые ссылаются на данный
объект\
-m \<msg\>/\--message=\<msg\> - сообщение для тега\
-e/\--edit - открыть редактор перед созданием тега для редактирования
сообщения

fetch - скачивание объектов и ссылок из другого репозитория\
\--all - получить все данные с удалённого репозитория\
-a/\--append - добавление **ref names and object names** в
.git/FETCH\_HEAD. Без этого **атрибута** данные в этом файле будут
перезаписаны\
\--depth=\<depth\> - ограничение на кол-во комитов, которые будут
скачены с каждой ветки -p/\--prune - перед fetch удаляет ссылки на
несуществующие объекты на удаленном репозиторие\
-t/\--tags - fetch всех тегов из удаленного репозитория
\--recurse-submodules\[=yes\|on-demand\|no\] - выполнять ли fetch для
всех сабмодулей -j/\--jobs=\<n\> - максимально число fetch\'ей, которые
могут выполняться одновременно

pull \<remote\>- выполнение fetch и интеграция с другим репозиторием или
локальной веткой \--recurse-submodules\[=yes\|on-demand\|no\] -
выполнять ли fetch для всех сабмодулей
-r/\--\[no-\]rebase\[=false\|true\|merges\|preserve\|interactive\] -
после fetch выполняется rebase на последний комит с upstream\'а.

Опции, связанные с **merge** (\--ff, squash, edit, autostash)

Опции, связанные с **fetch** (\--all, append, \--no-tags)\
push \[remote\] \[branch\]- отправка объектов на удалённый репозиторий

\--all - пуш всех веток\
\--prune - удаляет удалённые ветки, у которых нет локальных копий\
-d/\--delete - удаляет все перечисленные ссылки из удаленного
репозитория\
\--tags - отправляет перечисленные теги\
-u/\--set-upstream - добавление upstream\'а для каждой ветки
\--recurse-submodules=check\|on-demand\|only\|no - проверка, обновлены
ли сабмодули до последнего комита. Если нет - абортит выполнение\
\--\[no-\]verify - включает/отключает pre-push hook

remote - управление удалёнными репозиториями\
\--list - отображает все связанные удаленные репозитории\
\--add \[name\] \[url\] - позволяет создать имя для репозитория, чтобы
было удобнее к нему обращаться\
\--rename - изменяет имя репозитория\
\--rm - удалить ссылку на репозиторий\
\--show - показать информацию о репозитории

show \<objhash\> (отображает различные типы объектов или внутренности
коммитаз)

![page4image42350272](./lab-3//media/image5.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42350080](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42351040](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42349888](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42351424](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page4image42351616](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42336256](./lab-3//media/image5.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42336448](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42336640](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42336832](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42337024](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42337408](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42337600](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page4image42337216](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42337792](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42337984](./lab-3//media/image5.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42338368](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42338560](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42338752](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42338944](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42339136](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page4image42339328](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42338176](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42339712](./lab-3//media/image5.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42339904](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42340096](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page4image42340288](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42340480](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42340672](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42340864](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42341056](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42341248](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42341440](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42341632](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page4image42341824](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42342400](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42342016](./lab-3//media/image1.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42342208](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42339520](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page4image42342976](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}

\--format=\<format\> - выбор формата вывода (oneline, short, medium\...)

\--encoding=\<encoding\> - использовать кодировку log - вывод логов
коммитов

\--pretty - форматирование\
-p - показывает diff\
\--stat - показывает статистику по каждому коммиту \--graph - вывод
дерева коммитов в виде графа

fsck - проверяет объекты в базе данных\
\--unreachable - вывод всех объектов, которые существуют, но не доступны
ни с одного узла(reference nodes)\
\--\[no-\]dangling: вывод всех объектов, которые существуют, но никогда
не используются напрямую

gc - удаление ненужных файлов и оптимизация репозитория\
\--aggressive - агрессивная(более детальная) оптимизация по памяти\
\--auto - проверяет, нужно ли выполнять сборку. Если нет - завершает
выполнение команды\
\--\[no-\]prune=\<date\> - удаляет свободные объекты старше даты (по
дефолту 2 недели) / не удалять объекты

instaweb (встроенная утилита, для просмотра состояния репозитория в
браузере) Возможные опции: \--local, \--port, \--httpd(команда для
запуска), \--browser Действия для сервера: \--stop/start/restart

archive - создание архива файлов из указанного дерева\
\--format=\<fmt\> - формат архива, tar по-умолчанию\
-l/\--list - все доступные типы архива\
-o \<file\>/\--output=\<file\> - запись архива в указанный файл вместо
stdout \--remote=\<repo\> - создание архива с удаленного сервера, а не
локального дерева

prune - удаляет все недостижимые объекты с базы данных объектов\
\--expire \<time\> - удалять только те файлы, которые старше чем
указанное время

cat-file \<objhash\> (получение содержимого объекта по хешу)\
-t - вместо содержимого вывести тип объекта\
-s - вместо содержимого вывести размер объекта\
-p - вывод содержимого \<object\> в удобном виде в зависимости от его
типа.\
-e - выход с нулевым статусом, если \<object\> существует и является
допустимым объектом, иначе выход с ненулевым значением и запуск ошибки в
stderr.

ls-tree \<treedir\> - список элементов дерева объектов\
-d - показывать только деревья\
-r - рекурсивно выводить поддеревья\
-t - выводить также инфомацию о дереве при -r\
-l/\--long - выводит размер объекта \--name-only/\--name-status -
выводить только названия файлов \--full-name - выводить полный путь до
файла

grep \<regexp\> (вывод строк, подходящих под указанный паттерн)\
\--cached - поиск blob\'ов, зарегистрированных в индексном файле
\--no-index - поиск файлов в текущем каталоге, который не управляется
Git \--exclude-standard - игнорирование файлов, описанных в .gitignore

![page5image42409280](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42408896](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42408704](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page5image42408512](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42408320](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42410240](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42410432](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42410624](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page5image42410816](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42411200](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42411392](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page5image42411584](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42411776](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42411968](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42412160](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page5image42413888](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42409088](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42413696](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page5image42414080](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42414272](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42414464](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42414656](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42414848](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page5image42415040](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42415424](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page5image42415616](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42415808](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42416000](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42416192](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42416384](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page5image42416576](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42416768](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42416960](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42417152](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42417344](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42417536](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42415232](./lab-3//media/image2.png){width="4.236111111111111e-2in"
height="4.236111111111111e-2in"}![page5image42417920](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42417728](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}![page5image42025728](./lab-3//media/image3.png){width="5.416666666666667e-2in"
height="5.416666666666667e-2in"}
