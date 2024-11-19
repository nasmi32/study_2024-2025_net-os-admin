---
## Front matter
lang: ru-RU
title: Лабораторная работа №12
subtitle: Администрирование сетевых подсистем
author:
  - Мишина А. А.
date: 20 ноября 2024

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

## Цель работы

- Приобретение практических навыков по управлению системным временем и настройке синхронизации времени.

# Выполнение лабораторной работы

# Настройка параметров времени

## ВМ server

![Параметры настройки даты и времени, текущее системное время и аппаратное время на server](image/1.png){#fig:001 width=40%}

## ВМ client

![Параметры настройки даты и времени, текущее системное время и аппаратное время на client](image/2.png){#fig:002 width=60%}

# Управление синхронизацией времени

## Источники времени

![Просмотр источников времени на сервере](image/3.png){#fig:003 width=70%}

## Источники времени

![Просмотр источников времени на клиенте](image/4.png){#fig:004 width=70%}

## ВМ server

![Файл /etc/chrony.conf.](image/5.png){#fig:005 width=70%}

## ВМ client

![Файл /etc/chrony.conf. Настройка сервера в качестве сервера синхронизации времени](image/6.png){#fig:006 width=70%}

## Источники времени

![Просмотр источников времени на клиенте](image/7.png){#fig:007 width=40%}

## Источники времени

![Просмотр источников времени на сервере](image/8.png){#fig:008 width=45%}

# Внесение изменений в настройки внутреннего окружения виртуальных машины

## ВМ server

![Создание окружения для внесения изменений в настройки окружающей среды](image/9.png){#fig:009 width=70%}

## ВМ server

![Скрипт файла /vagrant/provision/server/ntp.sh](image/10.png){#fig:010 width=50%}

## ВМ client

![Создание окружения для внесения изменений в настройки окружающей среды](image/11.png){#fig:011 width=70%}

## ВМ client

![Скрипт файла /vagrant/provision/client/ntp.sh](image/12.png){#fig:012 width=50%}

## Выводы

- В результате выполнения данной работы были приобретены практические навыки по управлению системным временем и настройке синхронизации времени.