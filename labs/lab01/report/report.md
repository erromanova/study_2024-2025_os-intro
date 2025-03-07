---
## Front matter
title: "Отчёт по лабораторной работе №1"
subtitle: "дисциплина: операционные системы"
author: "Романова Елизавета Романовна"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Целью данной работы является приобретение практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов.

# Задание



1. Установка операционной системы

2. Загрузка необходимых обновлений

3. Настройка раскладки клавиатуры

4. Установка ПО для создания документации

5.Выполнение домашнего задания 
# Теоретическое введение


Техническое обеспечение

Лабораторная работа подразумевает установку на виртуальную машину [VirtualBox](https://www.virtualbox.org/) операционной системы Linux(дистрибутив Fedora).
Выполнение работы возможно как в дисплейном классе факультета физико-математических и естественных наук РУДН, так и дома. Описание выполнения работы приведено для
 дисплейного класса со следующими характеристиками техники:
Intel Core i3-550 3.2 GHz, 4 GB оперативной памяти, 80 GB свободного места на жёстком диске;
[ОС Linux Gentoo](http://www.gentoo.ru/);
VirtualBox версии 7.0 или новее.
Для установки в виртуальную машину используется [дистрибутив Linux Fedora](https://getfedora.org), вариант с менеджером окон [sway](https://fedoraproject.org/spins/sway/).
При выполнении лабораторной работы на своей технике вам необходимо скачать необходимый [образ операционной системы ](https://fedoraproject.org/spins/sway/download/index.html).
В дисплейных классах можно воспользоваться образом в каталоге /afs/dk.sci.pfu.edu.ru/common/files/iso.
Для определённости в описании будем использовать версию Fedora-Sway-Live-x86_64-41-1.4.iso.в

Linux (или GNU/Linux) – семейство Unix-подобных операционных систем на базе ядра Linux, включающих тот или иной набор утилит и программ проекта GNU. Linux-системы
 распространяются в виде различных дистрибутивов, имеющих свой набор системных и прикладных компонентов (как свободных, так и проприетарных). Дистрибутив Linux — это
  операционная система, созданная на основе ядра Linux, которая включает в себя набор библиотек и утилит (пакетов), разработанных в рамках проекта GNU, а также систему 
  управления пакетами (менеджер пакетов). В настоящее время существует более 500 различных дистрибутивов, разрабатываемых как при коммерческой поддержке 
  (Red Hat / Fedora, SLED / OpenSUSE, Ubuntu и др.), так и исключительно усилиями добровольцев (Debian, Slackware, Gentoo, ArchLinux и др.).

# Выполнение лабораторной работы
Скачиваю необходимое программное ПО, VirtualBox уже был установлен, кроме него загружаю Fedora-Sway-Live-x86_64-41-1.4.iso Запускаю виртуальную машину, создаю новую.
 Настраиваю Fedora Sway. 
Лично я воспользоваалсь помощью преподавателя, поэтому фотографию приложить не могу.


Переключаюсьсь на роль супер-пользователя и устанавливаю средства разработки:
![рис.1](1.jpg){#fig:001 width=70%}


Далее обновляю все пакеты:
![рис.2](2.jpg){#fig:001 width=70%}

для повышения комфорта работы устанавливаю программы для удобства работы в консоли:
![рис.3](3.jpg){#fig:001 width=70%}

Другой вариант консоли:
![рис.4](4.jpg){#fig:001 width=70%}

Автоматическое обновление
При необходимости можно использовать автоматическое обновление.
Установка программного обеспечения:
![рис.5](5.jpg){#fig:001 width=70%}

Настройка раскладки клавиатуры

Вхожу  в ОС под заданной мною при установке учётной записью.Нажмимаю комбинацию Win+Enter для запуска терминала. Запускаю терминальный мультиплексор tmux.
Создаю конфигурационный файл ~/.config/sway/config.d/95-system-keyboard-config.conf:
![рис.6](6.jpg){#fig:001 width=70%}

Отредактировала конфигурационный файл /etc/X11/xorg.conf.d/00-keyboard.conf так, как было показано в ТУИС:
![рис.7](7.jpg){#fig:001 width=70%}

Установка имени пользователя и названия хоста. Создаю  пользователя и задаю пароль для него. Устанавливаю имя хоста и проверяю, что имя хоста установлено верно:
![рис.8](8.jpg){#fig:001 width=70%}

Далее я устанавливаю pandoc и  pandoc-crossref:
![рис.9](9.jpg){#fig:001 width=70%}


Устанавливаю  дистрибутив TeXlive:
![рис.10](10.jpg){#fig:001 width=70%}

#  Выводы
Выводом данной лабораторной работы  является приобретение практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых
 для дальнейшей работы сервисов.


# Список литературы{.unnumbered}

::: {#refs}
:::
