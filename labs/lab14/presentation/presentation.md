---
## Front matter
lang: ru-RU
title: Лабораторная работа №14
subtitle: Администрирование сетевых подсистем
author:
  - Мишина А. А.
date: 1 декабря 2024

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

# Вводная часть

## Цель работы

Приобретение навыков настройки доступа групп пользователей к общим ресурсам по протоколу SMB.

# Выполнение лабораторной работы

## Настройка сервера Samba

На сервере установим необходимые пакеты:

```
dnf -y install samba samba-client cifs-utils
```

## Настройка сервера Samba

![Создание группы sambagroup, добавление к ней пользователя и создание каталога](image/1.png){#fig:001 width=70%}

## Настройка сервера Samba

![Добавление конфигураций в файл /etc/samba/smb.conf](image/2.png){#fig:002 width=35%}

## Настройка сервера Samba

![Запуск samba и просмотр статуса](image/3.png){#fig:003 width=40%}

## Настройка сервера Samba

![Подключение к серверу с помощью smbclient](image/4.png){#fig:004 width=40%}

## Настройка сервера Samba

![Файл конфигурации межсетевого экрана для Samba](image/5.png){#fig:005 width=70%}

## Настройка сервера Samba

![Настройка межсетевого экрана и прав доступа для каталога с разделяемым ресурсом](image/6.png){#fig:006 width=70%}

## Настройка сервера Samba

![Настройка контекста безопасности SELinux](image/7.png){#fig:007 width=70%}

## Настройка сервера Samba

![Просмотр UID нашего пользователя](image/8.png){#fig:008 width=70%}

## Настройка сервера Samba

![Создание файла на разделяемом ресурсе](image/9.png){#fig:009 width=70%}

## Настройка сервера Samba

![Добавление пользователя в базу пользователей Samba](image/10.png){#fig:010 width=70%}

## Монтирование файловой системы Samba на клиенте

![Настройка межсетевого экрана, создание группы и добавление в неё пользователя на клиенте](image/11.png){#fig:011 width=70%}

## Монтирование файловой системы Samba на клиенте

![Изменение параметра рабочей группы на клиенте](image/12.png){#fig:012 width=50%}

## Монтирование файловой системы Samba на клиенте

![Проверка наличия обшего доступа](image/13.png){#fig:013 width=35%}

## Монтирование файловой системы Samba на клиенте

![Подключение под записью пользователя](image/13-1.png){#fig:0131 width=70%}

## Монтирование файловой системы Samba на клиенте

![Получение доступа к общему ресурсу с клиента](image/14.png){#fig:014 width=70%}

## Монтирование файловой системы Samba на клиенте

![Создание файла на разделяемом ресурсе с клиента](image/15.png){#fig:015 width=70%}

## Монтирование файловой системы Samba на клиенте

![Создание файла учётных данных](image/16.png){#fig:016 width=70%}

## Монтирование файловой системы Samba на клиенте

![Внесение содержимого в файл smbusers](image/17.png){#fig:017 width=70%}

## Монтирование файловой системы Samba на клиенте

![Добавление записи в файл /etc/fstab](image/18.png){#fig:018 width=70%}

## Монтирование файловой системы Samba на клиенте

![Монтирование общего ресурса](image/19.png){#fig:019 width=70%}

## Монтирование файловой системы Samba на клиенте

![Проверка доступа к разделяемым ресурсам после перезапуска клиента](image/20.png){#fig:020 width=70%}

## Внесение изменений в настройки внутреннего окружения виртуальных машины

```
cd /vagrant/provision/server
mkdir -p /vagrant/provision/server/smb/etc/samba
cp -R /etc/samba/smb.conf /vagrant/provision/server/smb/etc/samba/

touch smb.sh
chmod +x smb.sh
```

## Внесение изменений в настройки внутреннего окружения виртуальных машины

![Скрипта файла /vagrant/provision/server/smb.sh](image/21.png){#fig:021 width=35%}

## Внесение изменений в настройки внутреннего окружения виртуальных машины

```
cd /vagrant/provision/client
mkdir -p /vagrant/provision/client/smb/etc/samba
cp -R /etc/samba/smb.conf /vagrant/provision/client/smb/etc/samba/
cp -R /etc/samba/smbusers /vagrant/provision/client/smb/etc/samba/

touch smb.sh
chmod +x smb.sh
```

## Внесение изменений в настройки внутреннего окружения виртуальных машины

![Скрипта файла /vagrant/provision/client/ smb.sh](image/22.png){#fig:022 width=40%}

## Внесение изменений в настройки внутреннего окружения виртуальных машины

```
server.vm.provision "SMB server",
  type: "shell",
  preserve_order: true,
  path: "provision/server/smb.sh"
client.vm.provision "SMB client",
  type: "shell",
  preserve_order: true,
  path: "provision/client/smb.sh"

```

# Заключение

## Выводы

В результате выполнения данной работы были приобретены практические навыки настройки доступа групп пользователей к общим ресурсам по протоколу SMB.