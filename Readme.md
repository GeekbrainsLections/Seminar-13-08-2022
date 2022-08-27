# Инструкция по работе с Git и с GitHub


## Что такое *Git*?
*Git* - одна из реализаций распределённых систем контроля версий, позволяющая организовать версионность, как локально, так и на удалённом серевере. Самая популярная платформа, реализующая *Git*,- [GitHub](https://github.com)

## Подготовка репозитория
Для создания в папке репозитория необходимо открыть эту папку в терминале и написать команду *git init*, после чего в этой папке создасться скрытая папка *.git*, и таким образом папка станет репозиторием


## Создание коммитов

### Просмотр состояния репозитория
Для просмотра состояния репозитория используется команда *git status*. В терминале с открытой папкой-репозиторием необходимо написать команду *git status*. В результате можно увидеть следующие выводы:
1. On branch *** nothing to commit - это означает нет активных изменений
2. Untracked file - это означает, что имеются файлы, не отслеживаемые системой контроля версий
...

### Добавление файла к коммиту
Для того, чтобы добавить файл к "сохранению", необходимо использовать команду *git add*. В терминале с открытой папкой-репозиторием необходимо написать *git add <название файла>*, и этот файл добавится к "сохранению"


### Создание фиксации
Для создания фиксации используется команда *git commit*. Для этого в терминале с папкой-репозиторием необходимо написать команду *git commit -m <сообщение к коммиту>*. Сообщение к коммиту писать **ОБЯЗАТЕЛЬНО**.


## Журнал изменений
Для просмотра истории изменений используется команда *git log*. Для этого в терминале с папкой-репозиторием необходимо написать *git log*, и Вы увидите список всех коммитов в этой ветке с описанием: имени, электронной почты, сообщением к коммиту и номер коммита.

## Перемещение между коммитами
Для перемещения между коммитами испозуется команда *git checkout*. Для этого в терминале с папкой-репозиторием необходимо написать *git checkout <номер коммита>*. Номер коммита берётся из журнала изменений ветки.

## Ветки в git
### Создание ветки
Для того, чтобы создать новую ветку используется команда *git branch*. Для этого терминале с папкой-репозиторием необходимо написать *git branch <название вертки>* и таким образом создасться новая ветка, но вы останетесь в исходной.

## Просмотр списка веток
Для того, чтобы просмотреть список веток в локальном репозитории, используется команда *git branch*. Для этого в терминале с папкой-репозиторием, напишите *git branch*, и тогда Вы увидите список всех Ваших локальных веток. Зелёным цветом и звёздочкой будет выделена ветка, на которой Вы сейчас стоите. Фалг *-a* позволяет посмотреть все ветки в том числе и в удалённом репозитории.

### Переключение между ветками
Для того, чтобы переключиться на другую ветку, используется команда *git checkout*. Для этого в терминале с папкой-репозиторием необходимо написать *git checkout <название ветки>*, и тогда Вы перейдёте в указанную ветку. Для переключения между ветками, ветка должна **СУЩЕСТВОВАТЬ**, и в текущий ветке **НЕ ДОЛЖНО** быть активных изменений


## Слияние веток и решение конфликтов
Для слияние веток используется команда *git merge*. Для этого в терминале с папкой-репозиторием  необходимо написать *git merge <название ветки>*. Название ветки указывать **которую необходимо "слиять"**. Важно находится **в ветке** в которую вы хотите провести слияние.

## Решение конфликтов
Так выглядит конфликт слияния файлов:
<<<<<<< HEAD
*=======*
*>>>>>>>* new_branch_to_merge_later
Эти новые строки можно рассматривать как «разделители конфликта». Строка ======= является «центром» конфликта. Все содержимое между этим центром и строкой <<<<<<< HEAD находится в текущей ветке main, на которую ссылается указатель HEAD. А все содержимое между центром и строкой >>>>>>> new_branch_to_merge_later является содержимым ветки для слияния.Самый простой способ разрешить конфликт — отредактировать конфликтующий файл,просто удалите все разделители конфликта. Для завершения слияния создайте новый коммит
## Удаление веток
Для удаления веток используетя команда *git branch -d <название ветки>*.
## Работа с удаленным репозиторием
Для *клонирования* репозитория необходимо использовать команду *git clone*. Для этого в терминале необходимо ввести команду *git clone<адрес репозитория>*.

### Просмотр удаленных репозиториев
Для того, чтобы просмотреть список настроенных удалённых репозиториев, вы можете запустить команду *git remote*.Она выведет названия доступных удалённых репозиториев. Если вы клонировали чей-то репозиторий, то увидите как минимум *origin* — имя по умолчанию, которое Git даёт серверу, с которого производилось клонирование.

### Добавление удаленных репозиториев
Для *клонирования* репозитория необходимо использовать команду *git clone*. Для этого в терминале необходимо ввести команду *git clone<адрес репозитория>*

### Получение изменений из удаленного репозитория
Для получения изменений из удаленного репозитория используют команду *git pull*. Для этого в терминале вводится команда *git pull<remote-name><адрес репозитория>*чтобы автоматически получить изменения из удалённой ветки и слить их со своей текущей. Этот способ может оказаться более простым или более удобным. К тому же, по умолчанию команда git clone автоматически настраивает локальную ветку master на отслеживание удалённой ветки master на сервере, с которого клонировали репозиторий. Название веток может быть другим и зависит от ветки по умолчанию на сервере. Выполнение git pull, как правило, извлекает данные с сервера, с которого изначально клонировали, и автоматически пытается слить *merge* их с кодом, над которым вы в данный момент работаете.
### Отправка изменений в удаленный репозиторий
Для того поделиться своими наработками, необходимо отправить их в удалённый репозиторий. Команда для этого действия *git push <remote-name> <имя ветки>*. Чтобы отправить вашу ветку *master* на сервер *origin*, можно выполнить следующую команду для отправки коммитов: **git push origin master** Эта команда срабатывает только в случае, если клонировали с сервера, на котором есть права на запись, и если никто другой с тех пор не выполнял команду *push*. Если вы и кто-то ещё одновременно клонирует, затем он выполняет команду push, а после него выполнить команду push попытаетесь вы, то push точно будет отклонён. Вам придётся сначала получить изменения и объединить их с вашими и только после этого вам будет позволено выполнить push.

