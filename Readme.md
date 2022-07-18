# Инструкция по работе с Git

## Что такое Git?

Git это одна из реализаций распределенных систем контроля версий, которая позволяет иметь версионность как в локальном, так и в удаленном репозитории (общем для всех). Git (произносится «гит»[7]) — распределённая система управления версиями. Проект был создан Линусом Торвальдсом для управления разработкой ядра Linux, первая версия выпущена 7 апреля 2005 года. На сегодняшний день его поддерживает Джунио Хамано.

Git (/ɡɪt/)[8] is software for tracking changes in any set of files, usually used for coordinating work among programmers collaboratively developing source code during software development. Its goals include speed, data integrity, and support for distributed, non-linear workflows (thousands of parallel branches running on different systems).[9][10][11]

Git was originally authored by Linus Torvalds in 2005 for development of the Linux kernel, with other kernel developers contributing to its initial development.[12] Since 2005, Junio Hamano has been the core maintainer. As with most other distributed version control systems, and unlike most client–server systems, every Git directory on every computer is a full-fledged repository with complete history and full version-tracking abilities, independent of network access or a central server.[13] Git is free and open-source software distributed under the GPL-2.0-only license.

Программа является свободной и выпущена под лицензией GNU GPL версии 2. По умолчанию используется TCP порт 9418. Git на данный момент является самой популярной системой контроля версий.

## Подготовка репозитория

Для создания репозитория используется команда *git init*. В терминале в папке с будущим репозиторием достаточно написать *git init*, и эта папка станет репозиторием.

## Добавление файла в коммит

Для добавления файла в текущий коммит используется команда *git add*. Для этого достаточно в терминале с папкой текущего репозитория написать *git add <название файла>*.

## Фиксация изменений

Для сохранения коммита используется команда *git commit*. Для этого достаточно в терминале с папкой текущего репозитория написать *git commit -m "Комментарий к коммиту"*.

## Журнал изменений

Для просмотра истории коммитов, то есть истории наших измений, используется команда *git log*. Для этого необходимо в терминале с папкой репозитории написать *git log*.

## Перемещение между сохранениями

Для того, чтобы перемещаться между коммитами необходимо использовать команду *git checkout*. Для этого в терминале с папкой репозитория необходимо написать *git checkout <номер коммита>*. Номер коммита берется из истории изменений. После такого перемещения мы попадаем в состояние **Detached head**. Для возвращение в обычное состояние используется команда *git checkout master*.

## Ветки в Git

Для того чтобы создавать различные версиии файлов отличные от исходного в Git имеется функция создания "веток". Это позволяет нам работать с файлом и вносить в него различные изменения, не затрагивая основную версию файла, которая находится на ветке master. Особенно это полезно, когда мы работаем с файлом по системе "черновик-чистовик", либо когда над файлом работают несколько человек. В любой момент мы можем "слить" наши альтернативные ветки с основной веткой master и удалить их при необходимости. 

## Создание веток 

Для создания новой ветки используется команда *git branch название_ветки*. Для того, чтобы увидеть список имеющихся веток необходимо набрать команду *git brach*, после подачи данной команды, Git также покажет на какой ветке в настоящий момент мы находимся. Для перемещения на другую ветку нужно вызвать команду *git checkout название_ветки*.

## Слияние веток и решение конфликтов

Для того чтобы слить дополнительную ветку с основной веткой master необходимо находясь в ветке master использовать команду *git merge название_ветки*, в случае отсутствия критичных противоречий между ветками Git автоматически объединит данную ветку с веткой master по одной из своих стратегий, в противном же случае мы получим conflicted state (состояние конфликта), которое необходимо будет разрешить вручную.

## Удаление веток

Для того, чтобы удалить ненужную ветку, необходимо использовать команду *git branch -d название_ветки*. 

## Вспомогательные команды

Для удобства работы в Git имеется возможность очистить терминал, для этого необходимо использовать команду *clear*, при этом все предыдущие команды скроются из терминала.
Для того, чтобы посмотреть список коммитов в виде графическом виде "дерева", нужно задать команду *git log --graph*.
Для того, чтобы вызвать справку, необходимо использовать команду *git --help*. Также имеется возможность вызвать справку в браузере при помощи команды *git merge --help*.