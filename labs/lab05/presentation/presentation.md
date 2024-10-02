---
## Front matter
lang: ru-RU
title: Лабораторная работа №5
subtitle: Администрирование сетевых подсистем
author:
  - Мишина А. А.
date: 2 октября 2024

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

- Приобретение практических навыков по расширенному конфигурированию HTTP-сервера Apache в части безопасности и возможности использования PHP.

# Выполнение лабораторной работы

# Конфигурирование HTTP-сервера для работы через протокол HTTPS

## Ключ и сертификат

![Генерация ключа и заполнение сертификата](image/1.png){#fig:1 width=40%}

## Сертификат

![Копирование сертификата в каталог /etc/ssl/certs](image/2.png){#fig:2 width=70%}

## www.aamishina.net

![Редактирование файла /etc/httpd/conf.d/www.aamishina.net](image/3.png){#fig:3 width=30%}

## Межсетевой экран

![Внесение изменений в настройки межсетевого экрана, перезапуск веб-сервера](image/4.png){#fig:4 width=50%}

## ВМ client

![Сообщение о незащищенности соединения](image/5.png){#fig:5 width=70%}

## Сертификат

![Содержимое сертификата](image/6.png){#fig:6 width=70%}

# Конфигурирование HTTP-сервера для работы с PHP

## index.php

![Замена файла /var/www/html/www.aamishina.net/index.html на index.php ](image/7.png){#fig:7 width=70%}

## index.php

![Редактирование index.php](image/8.png){#fig:8 width=70%}

## Корректировка и перезагрузка

![Корректирование прав доступа, восстановление контекста безопасности SELinux, перезагрузка HTTP-сервера](image/9.png){#fig:9 width=70%}

## ВМ Client

![Веб-страница с информацией об используемой версии PHP](image/10.png){#fig:10 width=50%}

# Внесение изменений в настройки внутреннего окружения виртуальной машины

## Настройки внутреннего окружения

![Копируем в каталоги конфигурационные файлы](image/11.png){#fig:11 width=70%}

## http.sh

![Внесение изменений в скрипт http.sh](image/12.png){#fig:12 width=30%}

## Вывод

- В результате выполнения работы были приобретены практические навыки по расширенному конфигурированию HTTP-сервера Apache в части безопасности и возможности использования PHP.