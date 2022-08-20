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

## Удаление веток
Для удаления веток используетя команда *git branch -d <название ветки>*.

## Отправка изменений в удалённый репозиторий

Отправлять изменения в удалённый репозиторий можно параметром push с указанием имени репозитория и ветки.

git push origin main

## Получение изменений из удалённого репозитория

Для загрузки изменений из удалённого репозитория используется параметр pull. Он скачивает копию текущей ветки с указанного удалённого репозитория и объединяет её с локальной копией.

git pull

## Слияние удалённого репозитория с локальным

Слияние удалённого репозитория с локальным выполняется параметром merge с указанием имени удалённого репозитория.

git merge origin
