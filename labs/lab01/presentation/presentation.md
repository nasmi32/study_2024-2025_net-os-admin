---
## Front matter
lang: ru-RU
title: Лабораторная работа №1
subtitle: Администрирование сетевых подсистем 
author:
  - Мишина А. А.
date: 7 сентября 2024

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

- Целью данной работы является приобретение практических навыков установки Rocky Linux на виртуальную машину с помощью инструмента Vagrant.

# Выполнение лабораторной работы

# Развёртывание лабораторного стенда на ОС Windows

## Rocky и box-файл

![Установка образа Rocky в Virtualbox и формирование box-файла](image/1.png){ #fig:001 width=80% }

## box-файл

![box-файл с дистрибутивом Rocky для Virtualbox](image/2.png){ #fig:002 width=80% }

## Образ ВМ

![Регистрация образа виртуальной машины в vagrant](image/3.png){ #fig:003 width=80% }

## Запуск

![Запуск виртуальной машины Server](image/4.png){ #fig:004 width=80% }

## Запуск

![Запуск виртуальной машины Client](image/5.png){ #fig:005 width=80% }

## Логин

![Логинимся в ВМ Server](image/6.png){ #fig:006 width=55% }

## Логин

![Логинимся в ВМ Client](image/7.png){ #fig:007 width=55% }

## Переход к пользователю

![Подключение к серверу и клиенту, переход к пользователю, отключение ВМ](image/8.png){ #fig:008 width=55% }

# Внесение изменений в настройки внутреннего окружения виртуальной машины

## Изменения для внутренних настроек ВМ

![Фиксируем изменения в ВМ Server](image/9.png){ #fig:009 width=55% }

## Изменения для внутренних настроек ВМ

![Фиксируем изменения в ВМ Client](image/10.png){ #fig:010 width=80% }

## Логин

![Логинимся в ВМ Server](image/11.png){ #fig:011 width=55% }

## Логин

![Логинимся в ВМ Client](image/12.png){ #fig:012 width=55% }

## Проверка приглашений

![Приглашения в терминале](image/13.png){ #fig:013 width=80% }

## Выключение ВМ

![Выключение виртуальных машин](image/14.png){ #fig:014 width=80% }

## Копирование файлов

![Копирование файлов](image/15.png){ #fig:015 width=80% }

## Вывод

- В ходе выполнения данной лабораторной работы я приобрела практические навыки установки Rocky Linux на виртуальную машину с помощью инструмента Vagrant.