---
## Front matter
lang: ru-RU
title: Лабораторная работа №4
subtitle: Администрирование сетевых подсистем
author:
  - Мишина А. А.
date: 24 сентября 2024

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

- Приобретение практических навыков по установке и базовому конфигурированию HTTP-сервера Apache.

# Выполнение лабораторной работы

# Установка HTTP-сервера

## HTTP-сервер

![Переход в режим суперпользователя и установка стандартного веб-сервера](image/0.png){ #fig:001 width=60% }

## Каталоги

![Просмотр содержимого каталогов /etc/httpd/conf etc/httpd/conf.d](image/1.png){#fig:1 width=70%}

## Межсетевой экран узла server

![Внесение изменений в настройки межсетевого экрана, запуск HTTP-сервера](image/2.png){#fig:2 width=70%}

## Проверка запуска сервера

![Расширенный лог системных сообщений](image/3.png){#fig:3 width=70%}

# Анализ работы HTTP-сервера 

## ВМ client

![Тестовая страницы HTTP-сервера](image/4.png){#fig:4 width=50%}

## Мониторинг и лог

![Запись в мониторинге доступа. Запись в логе ошибок](image/5.png){#fig:5 width=70%}

# Настройка виртуального хостинга для HTTP-сервера

## Прямая зона

![Добавление записи в конец файла прямой DNS-зоны](image/6.png){#fig:6 width=50%}

## Обратная зона

![Добавление записи в конец файла обратной DNS-зоны](image/7.png){#fig:7 width=50%}

## Файлы и перезапуск

![Удаление файлов журналов DNS, перезапуск DNS-сервера, создание файлов](image/8.png){#fig:8 width=50%}

## Файл

![Редактирование server.aamishina.net.conf](image/9.png){#fig:9 width=70%}

## Файл

![Редактирование www.aamishina.net.conf](image/10.png){#fig:10 width=70%}

## Welcome to the server.aamishina.net server.

![Создание каталога и файла главной страницы](image/11.png){#fig:11 width=70%}

## Права доступа и SELinux

![Корректирование прав доступа, восстановление контекста безопасности, перезагрузка httpd](image/12.png){#fig:12 width=70%}

## server

![Доступ к server.aamishina.net](image/13.png){#fig:13 width=70%} 

## www

![Доступ к www.aamishina.net](image/14.png){#fig:14 width=70%}

# Внесение изменений в настройки внутреннего окружения виртуальной машины

## Конфигурационные файлы

![Создание каталога http, помещение конфигурационных файлов HTTP-сервера, заменя конфигурационных файлов DNS-сервера](image/15.png){#fig:15 width=70%} 

## Скрипт http.sh

![Создание скрипта http.sh](image/16.png){#fig:16 width=70%}

## Vagrantfile

![Vagrantfile](image/17.png){#fig:17 width=50%}

## Вывод

- В результате выполнения работы были приобретены практические навыки по установке и базовому конфигурированию HTTP-сервера Apache.