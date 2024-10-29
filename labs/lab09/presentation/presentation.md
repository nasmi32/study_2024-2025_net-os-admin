---
## Front matter
lang: ru-RU
title: Лабораторная работа №9
subtitle: Администрирование сетевых подсистем
author:
  - Мишина А. А.
date: 29 октября 2024

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

- Приобретение практических навыков по установке и простейшему конфигурированию POP3/IMAP-сервера.

# Выполнение лабораторной работы

##  Установка Dovecot

- dnf -y install dovecot telnet.

# Настройка dovecot

## Почтовые протоколы

![Редактирование файла /etc/dovecot/dovecot.conf](image/1.png){#fig:1 width=50%}

## Метод аутентификации

![Редактирование файла /etc/dovecot/conf.d/10-auth.conf](image/2.png){#fig:2 width=50%}

## Месторасположение почтовых ящиков

![Редактирование файла /etc/dovecot/conf.d/10-mail.conf](image/3.png){#fig:3 width=70%}

## Postfix, firewall, dovecot

![Конфигурация Postfix, межсетевого экрана для работы с POP3 и IMAP и запуск Dovecot](image/4.png){#fig:4 width=40%}

# Проверка работы Dovecot

## Почта

- tail -f /var/log/maillog

![Просмотр почты и mailbox](image/5.png){#fig:5 width=70%}

## ВМ client

![Evolution: настройка учетной записи](image/6.png){#fig:6 width=70%}

## Evolution

![Evolution: настройка IMAP-сервера для входящих сообщений](image/7.png){#fig:7 width=70%}

## Evolution

![Evolution: настройка SMTP-сервера для исходящих сообщений](image/8.png){#fig:8 width=70%}

## Письма

![Просмотр мониторинга почтовой службы на сервере ](image/9.png){#fig:9 width=50%}

## Письма

![Просмотр информации о почтовой службе с помощью doveadm и mail](image/10.png){#fig:10 width=70%}

## telnet

![Подключение с помощью telnet и просмотр писем](image/11.png){#fig:11 width=30%}

## telnet

![Просмотр письма, удаление, завершение сеанса в telnet](image/12.png){#fig:12 width=30%}

# Внесение изменений в настройки внутреннего окружения виртуальной машины

## ВМ server

![Редактирование mail.sh на сервере](image/13.png){#fig:13 width=30%}

## ВМ client

![Редактирование mail.sh на клиенте](image/14.png){#fig:14 width=30%}

## Выводы

- В результате выполнения работы были приобретены практические навыки по установке и простейшему конфигурированию POP3/IMAP-сервера.