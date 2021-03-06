---
## Front matter
lang: ru-Ru 
title: "Лабораторная работа №7"
subtitle: "Командная оболочка Midnight Commander."
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

Освоение основных возможностей командной оболочки Midnight Commander. Приобретение навыков практической работы по просмотру каталогов и файлов; манипуляций с ними.

# Теоретическое введение

<p>

**Командная оболочка** — интерфейс взаимодействия пользователя с операционной системой и программным обеспечением посредством команд.
Midnight Commander (или mc) — псевдографическая командная оболочка для UNIX/Linux систем. Для запуска mc необходимо в командной строке набрать mc и нажать Enter . Рабочее пространство mc имеет две панели, отображающие по умолчанию списки файлов двух каталогов 
<p>

**Режимы отображения панелей и управление ими**
<p>Панель в mc отображает список файлов текущего каталога. Абсолютный путь к этому каталогу отображается в заголовке панели. У активной панели заголовок и одна из её строк подсвечиваются. Управление панелями осуществляется с помощью определённых
комбинаций клавиш или пунктов меню mc.
<p>

**Меню панелей**
<p>Перейти в строку меню панелей mc можно с помощью функциональной клавиши F9.
<p>В строке меню имеются пять меню: Левая панель , Файл , Команда , Настройки и Правая панель .
<p>Подпункт меню Быстрый просмотр позволяет выполнить быстрый просмотр содержимого
панели.
<p>Подпункт меню Информация позволяет посмотреть информацию о файле или каталоге.
<p>В меню каждой (левой или правой) панели можно выбрать Формат списка :
<p>– стандартный — выводит список файлов и каталогов с указанием размера и времени
правки;
<p>– ускоренный — позволяет задать число столбцов, на которые разбивается панель при
выводе списка имён файлов или каталогов без дополнительной информации;
<p>– расширенный — помимо названия файла или каталога выводит сведения о правах доступа, владельце, группе, размере, времени правки;
определённый пользователем — позволяет вывести те сведения о файле или каталоге, которые задаст сам пользователь.
<p>Подпункт меню Порядок сортировки позволяет задать критерии сортировки при выводе списка файлов и каталогов: без сортировки, по имени, расширенный, время правки, время доступа, время изменения атрибута, размер, узел.
<p

**Команды меню Файл**:

<p>– Просмотр ( F3 ) — позволяет посмотреть содержимое текущего (или выделенного) файла без возможности редактирования.
<p>– Просмотр вывода команды ( М + ! ) — функция запроса команды с параметрами (аргумент к текущему выбранному файлу).
<p>– Правка ( F4 ) — открывает текущий (или выделенный) файл для его редактирования.
<p>– Копирование ( F5 ) — осуществляет копирование одного или нескольких файлов или каталогов в указанное пользователем во всплывающем окне место.
<p>– Права доступа ( Ctrl-x c ) — позволяет указать (изменить) права доступа к одному или нескольким файлам или каталогамж
<p>- И др.
<p>В меню Команда содержатся более общие команды для работы с mc.
<p>

**Команды меню Команда** :
<p>– Дерево каталогов — отображает структуру каталогов системы.
<p>– Поиск файла — выполняет поиск файлов по заданным параметрам.
<p>– Переставить панели — меняет местами левую и правую панели.
<p>– Сравнить каталоги ( Ctrl-x d ) — сравнивает содержимое двух каталогов.
<p>– Размеры каталогов — отображает размер и время изменения каталога (по умолчанию в mc размер каталога корректно не отображается).
<p>– История командной строки — выводит на экран список ранее выполненных в оболочке команд.
<p>– Каталоги быстрого доступа ( Ctrl-\ ) — пр вызове выполняется быстрая смена текущего каталога на один из заданного списка.
<p>Меню Настройки содержит ряд дополнительных опций по внешнему виду и функциональности mc.
<p>

**Меню Настройки содержит:**
<p>– Конфигурация — позволяет скорректировать настройки работы с панелями.
<p>Внешний вид и Настройки панелей — определяет элементы (строка меню, командная строка, подсказки и прочее), отображаемые при вызове mc, а также геометрию расположения панелей и цветовыделение.
<p>- И другие.
<p>Встроенный в mc редактор вызывается с помощью функциональной клавиши F4 .<p>В нём удобно использовать различные комбинации клавиш при редактировании содержимого (как правило текстового) файла.

# Выполнение лабораторной работы

**Задание по mc**

<p>1. Изучите информацию о mc, вызвав в командной строке man mc.

С помощью команды man изучаем информацию о mc.

![Рис.1](screens/1.png)

![Рис.2](screens/2.png)

<p>2. Запустите из командной строки mc, изучите его структуру и меню.

С помощью команды mc заходим в сам редактор. Изучаем его структуру и меню.

![Рис.3](screens/3.png)

![Рис.4](screens/4.png)

<p>3. Выполните несколько операций в mc, используя управляющие клавиши (операции с панелями; выделение/отмена выделения файлов, копирование/перемещение файлов, получение информации о размере и правах доступа на файлы и/или каталоги и т.п.)


![Рис.5](screens/5.png)

Изучаем меню панелей mc.

![Рис.6](screens/6.png)

Изучаем функции панелей.

![Рис.7](screens/7.png)

![Рис.8](screens/8.png)

![Рис.9](screens/9.png)

![Рис.10](screens/10.png)

![Рис.11](screens/11.png)

Создание жёсткой ссылки к текущему (или
выделенному) файлу.

![Рис.12](screens/12.png)

![Рис.13](screens/13.png)

![Рис.15](screens/15.png)

![Рис.16](screens/16.png)

Изучаем дерево каталогов.

![Рис.18](screens/18.png)

![Рис.19](screens/19.png)

![Рис.20](screens/20.png)

![Рис.21](screens/21.png)

<p>4. Выполните основные команды меню левой (или правой) панели. Оцените степень подробности вывода информации о файлах.


![Рис.4.1](screens/51.png)

<p>

![Рис.4.2](screens/53.png)

<p>

![Рис.4.3](screens/18.png)

<p>

![Рис.4.4](screens/8.png)


<p>5. Используя возможности подменю Файл , выполните:
<p>– просмотр содержимого текстового файла;

С помощью клавиши f3 просматриваем содержимое файла.

![Рис.22](screens/22.png)

<p>– редактирование содержимого текстового файла (без сохранения результатов
редактирования);

С помощью команды f4 редактируем содержимое файла.

![Рис.23](screens/23.png)

<p>– создание каталога;

![Рис.24](screens/24.png)

<p>– копирование в файлов в созданный каталог.

![Рис.25](screens/25.png)

<p>6. С помощью соответствующих средств подменю Команда осуществите:
<p>– поиск в файловой системе файла с заданными условиями (например, файла
с расширением .c или .cpp, содержащего строку main);

Находим в файловой системе файл со строкой main. Берём любое расширение.

![Рис.26](screens/26.png)

![Рис.27](screens/27.png)

<p>– выбор и повторение одной из предыдущих команд;

Я решила снова осуществитьь поиск файла с заданными условиями.

![Рис.28](screens/28.png)

![Рис.29](screens/29.png)

<p>– переход в домашний каталог;

<p>7. Вызовите подменю Настройки . Освойте операции, определяющие структуру экрана mc (Full screen, Double Width, Show Hidden Files и т.д.)

![Рис.30](screens/30.png)

![Рис.31](screens/31.png)

![Рис.32](screens/32.png)

<p>
<p>

**Задание по встроенному редактору mc**
<p>1. Создайте текстовой файл text.txt.

С помощью команды touch создаём текстовый файл text.txt.

![Рис.33](screens/33.png)

<p>2. Откройте этот файл с помощью встроенного в mc редактора.

![Рис.34](screens/34.png)

<p>3. Вставьте в открытый файл небольшой фрагмент текста, скопированный из любого другого файла или Интернета.

Берём информацию о гепарде из интернета и вставляем в данный файл.

![Рис.34](screens/34.png)

<p>4. Проделайте с текстом следующие манипуляции, используя горячие клавиши:
<p>

*4.1. Удалите строку текста.*

С помощью команды ctrl-y удаляем строку.

![Рис.35](screens/35.png)

<p>

*4.2. Выделите фрагмент текста и скопируйте его на новую строку*

С помощью клавиш f5 и Ins мы копируем и вставляем его на другую строку.

![Рис.37](screens/38.png)

<p>

*4.3. Выделите фрагмент текста и перенесите его на новую строку.*

С помощью клавиш f5 и Ins мы копируем и вставляем его на другую строку.

![Рис.38](screens/37.png)

<p>

*4.4.Сохраните файл.*

![Рис.39](screens/48.png)

<p>

*4.5. Отмените последнее действие.*

 C помощью сочетания клавиш ctrl-u мы отменяем последнее действие. 

![Рис.40](screens/39.png)

![Рис.41](screens/40.png)

<p>

*4.6. Перейдите в конец файла (нажав комбинацию клавиш) и напишите некоторый текст.*

С помощью сочетания клавиш Alt-\ мы переходим в конец файла.

![Рис.42](screens/41.png)

<p

*4.7. Перейдите в начало файла (нажав комбинацию клавиш) и напишите некоторый текст.*

С помощью сочетания клавиш Alt-\\ мы переходим в начало файла.

![Рис.43](screens/43.png)

<p>

*4.8. Сохраните и закройте файл.*

![Рис.44](screens/49.png)

<p>5. Откройте файл с исходным текстом на некотором языке программирования (например C или Java)

Находим файл с расширением с и открываем его.

![Рис.45](screens/50.png)

![Рис.46](screens/45.png)

<p>6. Используя меню редактора, включите подсветку синтаксиса, если она не включена, или выключите, если она включена.

В панели Команда находим команду Включить/выключить подсветку синтаксиса, выключаем и кайфуем)

![Рис.47](screens/46.png)

![Рис.48](screens/47.png)

# Вывод

Я освоила основные возможности командной оболочки Midnight Commander и приобрела навыки практической работы по просмотру каталогов и файлов; манипуляций с ними.

# Контрольные вопросы

<p>

**1. Какие режимы работы есть в mc. Охарактеризуйте их.**

<p>Экран MC делится на четыре части. Почти весь зкран занят двумя панелями. По умолчанию, вторая строка снизу является командной, а в самой нижней отображается назначение функциональных клавиш. Самая верхняя строка - строка меню. Она может быть не видна, но при нажатии клавиши F9 или при щелчке мыши эта строка отображается в верхней части экрана.

<p>MC позволяет одновременно наблюдать содержимое двух каталогов. Одна из панелей является текущей (в этой панели находится выделитель). Практически все команды оперируют над текущей панелью. Хотя некоторые файловые операции, такие как Rename или Copy, по умолчанию используют каталог неактивной панели в качестве каталога назначения (при выполнении подобных команд всегда появляется запрос на подтверждение). Для более подробной информации просмотрите разделы 'ПАНЕЛИ', 'МЕНЮ Left', 'МЕНЮ Right' и 'МЕНЮ File'.

<p>Можно выполнять системные команды прямо из MC просто путём их набора на клавиатуре. Всё, что Вы набираете, появляется в командной строке, а при нажатии клавиши Enter, MC выполнит набранную строку. Просмотрите разделы 'КОМАНДНАЯ СТРОКА' и 'КЛАВИШИ РЕДАКТИРОВАНИЯ' для более подробной информации.

<p>

**2. Какие операции с файлами можно выполнить как с помощью команд shell, так и с помощью меню (комбинаций клавиш) mc? Приведите несколько примеров.**

<p>-Просмотр ( F3 ) — позволяет посмотреть содержимое текущего (или выделенного) файла без возможности редактирования.
<p>– Просмотр вывода команды ( М + ! ) — функция запроса команды с параметрами (аргумент к текущему выбранному файлу).
<p>– Правка ( F4 ) — открывает текущий (или выделенный) файл для его редактирования.
<p>– Копирование ( F5 ) — осуществляет копирование одного или нескольких файлов или каталогов в указанное пользователем во всплывающем окне место.
<p>– Права доступа ( Ctrl-x c ) — позволяет указать (изменить) права доступа к одному или нескольким файлам или каталогам.
<p>– Переименование ( F6 ) — позволяет переименовать (или переместить) один или несколько файлов или каталогов.
<p>– Создание каталога ( F7 ) — позволяет создать каталог.
<p>– Удалить ( F8 ) — позволяет удалить один или несколько файлов или каталогов.
<p>– Выход ( F10 ) — завершает работу mc.
<p>

<p>

**3. Опишите структура меню левой (или правой) панели mc, дайте характеристику командам.**

В меню каждой (левой или правой) панели можно выбрать Формат списка :
<p>– стандартный — выводит список файлов и каталогов с указанием размера и времени правки;
<p>– ускоренный — позволяет задать число столбцов, на которые разбивается панель при выводе списка имён файлов или каталогов без дополнительной информации;
<p>– расширенный — помимо названия файла или каталога выводит сведения о правах доступа, владельце, группе, размере, времени правки;
<p>– определённый пользователем — позволяет вывести те сведения о файле или каталоге,которые задаст сам пользователь.
<p>Подпункт меню Порядок сортировки позволяет задать критерии сортировки при выводе списка файлов и каталогов: без сортировки, по имени, расширенный, время правки, время доступа, время изменения атрибута, размер, узел.
