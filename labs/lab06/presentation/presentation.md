---
## Front matter
lang: ru-RU
title: Лабораторная работа №6
subtitle: Администрирование сетевых подсистем
author:
  - Мишина А. А.
date: 9 октября 2024

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'

 - '\makeatother'
---

## Цели и задачи

- Приобретение практических навыков по установке и конфигурированию системы управления базами данных на примере программного обеспечения MariaDB.

# Выполнение лабораторной работы

# Установка MariaDB

## Начало работы

![Установка пакетов](image/1.png){#fig:1 width=50%}

## Запуск mariadb

![Просмотр конфигурационных файлов. Прослушивание порта 3306](image/2.png){#fig:2 width=70%}

## Вход в базу данных

- mysql_secure_installation

![Вход в БД и просмотр списка команд](image/3.png){#fig:3 width=30%}

## Базы данных в системе

![Имеющиеся в системе БД](image/4.png){#fig:4 width=40%}

# Конфигурация кодировки символов

## Статус

![Статус MariaDB](image/5.png){#fig:5 width=30%}

## Файл utf8.cnf

![Редактирование файла /etc/my.cnf.d/utf8.cnf](image/6.png){#fig:6 width=70%}

## Новый статус

![Статус MariaDB после конфигурации кодировки символов](image/7.png){#fig:7 width=30%}

# Создание базы данных

## База данных

![Создание БД addressbook и таблицы city](image/8.png){#fig:8 width=50%}

## Заполнение

![Вставка данных в таблицу ](image/9.png){#fig:9 width=70%}

## Просмотр

![Просмотр таблицы, создание пользователя, предоставление прав, обновление привилегий](image/10.png){#fig:10 width=70%}

## Информация

![Общая информация о таблице](image/11.png){#fig:11 width=70%}

## Список БД

![Список БД, cписок таблиц БД addressbook](image/12.png){#fig:12 width=30%}

# Резервные копии

## Резервные копии

![Созданные резервные копии, восстановление резервных копий](image/13.png){#fig:13 width=70%}

# Внесение изменений в настройки внутреннего окружения виртуальной машины

## Внесение изменений в настройки внутреннего окружения

![Копирование каталогов, создание скрипта](image/14.png){#fig:14 width=70%}

## Файл mysql.sh

![Создание скрипта mysql.sh](image/15.png){#fig:15 width=20%}

## Вывод

- В результате выполнения работы были приобретены практические навыки по установке и конфигурированию системы управления базами данных на примере программного обеспечения MariaDB.