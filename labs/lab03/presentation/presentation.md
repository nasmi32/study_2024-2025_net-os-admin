---
## Front matter
lang: ru-RU
title: Лабораторная работа №3
subtitle: Администрирование сетевых подсистем
author:
  - Мишина А. А.
date: 20 сентября 2024

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

- Приобретение практических навыков по установке и конфигурированию DHCP-сервера.

# Выполнение лабораторной работы

# Установка DHCP-сервера

## Dhcp

![Переход в режим суперпользователя и установка dhcp](image/0.png){ #fig:001 
width=40% }

# Конфигурирование DHCP-сервера

## Файл dhcpd.conf

![Копирование файла примера конфигурации и переименование](image/1.png){#fig:1 width=70%}

## Файл /etc/dhcp/dhcpd.conf

![Редактирование файла /etc/dhcp/dhcpd.conf](image/2.png){#fig:2 width=50%}

## Привязка dhcpd к интерфейсу eth1

![Редактирование файла /etc/systemd/system/dhcpd.service](image/3.png){#fig:3 width=70%}

## Автозагрузка

![Перезагрузка конфигурации и автозагрузка DHCP-сервера](image/4.png){#fig:4 width=70%}

## Прямая зона

![Редактирование файла прямой DNS-зоны](image/5.png){#fig:5 width=70%}

## Обратная зона

![Редактирование файла обратной DNS-зоны](image/6.png){#fig:6 width=70%}

## DNS и DHCP

![Перезагрузка DNS-сервера и пинг DHCP-сервера](image/7.png){#fig:7 width=80%}

## Межсетевой экран и SELinux

![Внесение изменений в настройки межсетевого экрана, восстановление контекста безопасности](image/8.png){#fig:8 width=50%}

## Мониторинг процессов

![Мониторинг происходящих в системе процессов](image/9.png){#fig:9 width=70%}

## Запуск

![Запуск DHCP-сервера](image/10.png){#fig:10 width=70%}

# Анализ работы DHCP-сервера

## 01-routing.sh

![Файл 01-routing.sh](image/11.png){#fig:11 width=50%}

## ВМ client

![Запись о подключении к ВМ узла client и выдачи ему IP-адреса](image/12.png){#fig:12 width=70%}

## dhcpd.leases

![Просмотр файла /var/lib/dhcpd/dhcpd.leases](image/13.png){#fig:13 width=50%}

## Имеющиеся интерфейсы

![ifconfig на ВМ client](image/14.png){#fig:14 width=50%}

## aamishina.net

![Редактирование файла /etc/named/aamishina.net ](image/15.png){#fig:15 width=40%}

## Перезапуск и редактирование

![Редактирование файла /etc/dhcp/dhcpd.conf](image/16.png){#fig:16 width=40%}

## Перезапуск

![Успешный перезапуск DHCP-сервера](image/17.png){#fig:17 width=70%}

# Анализ работы DHCP-сервера после настройки обновления DNS-зоны

## ВМ client

![Проверка DNS-записи о клиенте в прямой DNS-зоне](image/18.png){#fig:18 width=70%}

# Внесение изменений в настройки внутреннего окружения виртуальной машины

## ВМ server

![Изменения в настройках внутреннего окружения, создание каталога dhcp, замена конфигурационных файлов DNS-сервера](image/19.png){#fig:19 width=70%}

## Скрипт dhcp.sh

![Создание скрипта dhcp.sh](image/20.png){#fig:20 width=30%}

## Отработка скрипта во время запуска

![Изменения в Vagrantfile](image/21.png){#fig:21 width=50%}

## Вывод

- В результате выполнения работы были приобретены практические навыки по установке и конфигурированию DHCP-сервера.