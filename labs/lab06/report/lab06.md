---
## Front matter
lang: ru-Ru 
title: "Лабораторная работа №6"
subtitle: "Поиск файлов. Перенаправление ввода-вывода. Просмотр запущенных процессов."
author: "Гнатюк Анастасия Станиславовна"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы
Ознакомление с инструментами поиска файлов и фильтрации текстовых данных.
Приобретение практических навыков: по управлению процессами (и заданиями), по проверке использования диска и обслуживанию файловых систем.

# Теоретическое введение
**Конвейер**
<p>Конвейер (pipe) служит для объединения простых команд или утилит в цепочки, в которых результат работы предыдущей команды передаётся последующей. Синтаксис следующий:
<p>1 команда 1 | команда 2
<p>Конвейеры можно группировать в цепочки и выводить с помощью перенаправления в файл, например:
<p>
1 ls -la |sort > sortilg_list
<p>

**Поиск файла**
<p>Команда find используется для поиска и отображения на экран имён файлов, соответствующих заданной строке символов.
<p>Формат команды:
<p>1 find путь [-опции]
<p>

**Фильтрация текста**
<p>Найти в текстовом файле указанную строку символов позволяет команда grep.
<p>Формат команды:
<p>1 grep строка имя_файла
<p>

**Проверка использования диска**
<p>Команда df показывает размер каждого смонтированного раздела диска.
<p>Формат команды:
<p>1 df [-опции] [файловая_система]
<p>

**Управление задачами**
<p>Любую выполняющуюся в консоли команду или внешнюю программу можно запустить в фоновом режиме. Для этого следует в конце имени команды указать знак амперсанда &. Например:
<p>1 gedit &
<p>Будет запущен текстовой редактор gedit в фоновом режиме. Консоль при этом не будет заблокирована.
<p>Для завершения задачи необходимо выполнить команду
<p>1 kill %номер задачи
<p>

**Получение информации о процессах**
<p>Команда ps используется для получения информации о процессах.
<p>Формат команды:
<p>1 ps [-опции]
<p>Пример работы, требующей много машинного времени для выполнения, и которую целесообразно запустить в фоновом режиме:
<p>1 find /var/log -name "*.log" -print > l.log &

# Выполнение лабораторной работы
<p>1. Я заранее осуществила вход в систему.

<p>2. С помощью команды ls -a мы берём все файлы, находящиееся в каталоге etc и переносим с помощью >> в файл file.txt.

![Рис.1](screens/1.png)

![Рис.2](screens/2.png)

![Рис.3](screens/3.png)

![Рис.4](screens/4.png)

<p>3. С помощью команды grep мы находим в файле file.txt все файлы, которые в названии имеют conf. Затем создаём файл с помощью команды touch conf.txt, куда мы и переносим все файлы с расширением .conf из file.txt.

![Рис.5](screens/5.png)

![Рис.6](screens/6.png)

![Рис.7](screens/7.png)

![Рис.8](screens/8.png)

![Рис.9](screens/9.png)

![Рис.10](screens/10.png)

<p>4. С помощью команд ls -a | grep c* и file c* выводим все файлы, названия которых начинаются с символа с.

![Рис.11: Первый способ](screens/11.png)

![Рис.12: Второй способ](screens/12.png)

<p>5. С помощью команды find /etc -name "h*" -print выводим все файлы из каталога /etc, которые начинаются на h.

![Рис.13](screens/13.png)

<p>6. С помощью команды find / -name "log*" -print > logfile переносим все файлы из домашней директории, которые начинаются с log, в logfile.

![Рис.14: ](screens/14.png)

![Рис.15: ](screens/15.png)

![Рис.17](screens/17.png)

<p>7. С помощью команды rm удаляем файл logfile.

![Рис.16](screens/16.png)

<p>8. С помощью & запускаем gedit в фоновом режиме.

![Рис.18](screens/18.png)

<p>9. С помощью команды ps изнаём идентификатор процесса gedit -> 5571.

![Рис.19](screens/19.png)

<p>10. С помощью команды man мы изучаем информацию о команде kill.

![Рис.20](screens/20.png)

<p>11. С помощью команды kill прекращаем работу gedit.

![Рис.21](screens/21.png)

<p>12. С помощью команды find -type d находим все каталоги нашей домашней директории.

![Рис.22](screens/22.png)

![Рис.23](screens/23.png)

# Выводы
Я ознакомилась с инструментами поиска файлов и фильтрации текстовых данных и
приобрела практических навыков: по управлению процессами (и заданиями), по проверке использования диска и обслуживанию файловых систем.

# Контрольные вопросы
**1. Какие потоки ввода вывода вы знаете?**
<p>
– stdin — стандартный поток ввода (по умолчанию: клавиатура), файловый дескриптор
0;
<p>
– stdout — стандартный поток вывода (по умолчанию: консоль), файловый дескриптор
1;
<p>
– stderr — стандартный поток вывод сообщений об ошибках (по умолчанию: консоль),
файловый дескриптор 2.

**2. Объясните разницу между операцией > и >>.**
<p>

">" - это открывает файл на перезапись, когда ">>" открывает файл на дозапись

**3. Что такое конвейер?**
<p>
Направление вывода на вход для следующей команды

**4. Что такое процесс? Чем это понятие отличается от программы?**
<p>
Процесс - это исполняемая программа.
<p>
Программа - это набор инструкций, которые выполняют определенную задачу при выполнении компьютером, в то время как процесс является экземпляром выполняемой компьютерной программы. Таким образом, в этом главное отличие программы и процесса.

**5. Что такое PID и GID?**
<p>
pid: это идентификатор процесса (PID) процесса, который вы вызываете
<p>
GID: идентификатор группы. Все группы Linux определяются GID (идентификаторами групп). GID хранятся в файле / etc / groups.


