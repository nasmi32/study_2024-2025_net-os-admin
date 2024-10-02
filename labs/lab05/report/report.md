---
## Front matter
title: "Отчёт по лабораторной работе №5"
subtitle: "Дисциплина: Администрирование сетевых подсистем"
author: "Мишина Анастасия Алексеевна"

## Generic options
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
fontsize: 14pt
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
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
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

#  Цель работы

Приобретение практических навыков по расширенному конфигурированию HTTP-сервера Apache в части безопасности и возможности использования PHP.

# Выполнение лабораторной работы

## Конфигурирование HTTP-сервера для работы через протокол HTTPS

Запускаем ВМ через рабочий каталог. На ВМ server входим под собственным пользователем и переходим в режим суперпользователя. В каталоге /etc/ssl создаем каталог private: mkdir -p /etc/pki/tls/private, ln -s /etc/pki/tls/private /etc/ssl/private, cd /etc/pki/tls/private. Генерируем ключ и сертификат (рис. [-@fig:1]), введя следующую команду: openssl req -x509 -nodes -newkey rsa:2048 -keyout www.aamishina.net.key -out www.aamishina.net.crt

![Генерация ключа и заполнение сертификата](image/1.png){#fig:1 width=70%}

Сгенерированные ключ и сертификат появляются в соответствующем каталоге /etc/ssl/private. Копируем сертификат в каталог /etc/ssl/certs (рис. [-@fig:2])

![Копирование сертификата в каталог /etc/ssl/certs](image/2.png){#fig:2 width=70%}

Редактируем конфигурационный файл /etc/httpd/conf.d/www.aamishina.net (рис. [-@fig:3])

![Редактирование файла /etc/httpd/conf.d/www.aamishina.net](image/3.png){#fig:3 width=70%}

Вносим изменения в настройки межсетевого экрана на сервере, перезапускаем веб-сервер (рис. [-@fig:4])

![Внесение изменений в настройки межсетевого экрана, перезапуск веб-сервера](image/4.png){#fig:4 width=70%}

На ВМ client открываем в браузере страницу www.aamishina.net с сообщением о незащищенности соединения (рис. [-@fig:5]). Добавив страницу в исключения, просматриваем информацию о сертификате (рис. [-@fig:6]). 

![Сообщение о незащищенности соединения](image/5.png){#fig:5 width=70%}

![Содержимое сертификата](image/6.png){#fig:6 width=70%}

## Конфигурирование HTTP-сервера для работы с PHP

Устанавливаем пакеты для работы с PHP: dnf -y install php.

В каталоге /var/www/html/www.aamishina.net заменяем index.html на index.php (рис. [-@fig:7]).

![Замена файла /var/www/html/www.aamishina.net/index.html на index.php ](image/7.png){#fig:7 width=70%}

Редактируем index.php (рис. [-@fig:8]).

![Редактирование index.php](image/8.png){#fig:8 width=70%}

Корректируем права доступа в каталог с веб-контентом, восстанавливаем контекст безопасности в SELinux, перезагружаем HTTP-сервер: chown -R apache:apache /var/www, restorecon -vR /etc, restorecon -vR /var/www и systemctl restart httpd (рис. [-@fig:9]).

![Корректирование прав доступа, восстановление контекста безопасности SELinux, перезагрузка HTTP-сервера](image/9.png){#fig:9 width=70%}

На ВМ client вводим в адресную строку браузера www.aamishina.net и видим веб-страницу с информацией об используемой версии PHP (рис. [-@fig:10]).

![Веб-страница с информацией об используемой версии PHP](image/10.png){#fig:10 width=70%}

## Внесение изменений в настройки внутреннего окружения виртуальной машины

На ВМ server переходим в каталог для внесения изменений в настройки внутреннего окружения /vagrant/provision/server/ и копируем в соответствующие каталоги конфигурационные файлы (рис. [-@fig:11]).

![Копируем в каталоги конфигурационные файлы](image/11.png){#fig:11 width=70%}

В скрипт /vagrant/provision/server/http.sh вносим изменения, добавив установку PHP и настройку межсетевого экрана для работы с https (рис. [-@fig:12]).

![Внесение изменений в скрипт http.sh](image/12.png){#fig:12 width=70%}

# Выводы

В результате выполнения работы были приобретены практические навыки по расширенному конфигурированию HTTP-сервера Apache в части безопасности и возможности использования PHP.

# Ответы на контрольные вопросы

1. В чём отличие HTTP от HTTPS? 

- **HTTP** (HyperText Transfer Protocol) – это протокол передачи данных, который используется для передачи информации между клиентом (например, веб-браузером) и сервером. Однако он не обеспечивает шифрование данных, что делает их уязвимыми к перехвату злоумышленниками. 

- **HTTPS** (HyperText Transfer Protocol Secure) - это расширение протокола HTTP с добавлением шифрования, обеспечивающее безопасную передачу данных между клиентом и сервером. Протокол HTTPS использует SSL (Secure Sockets Layer) или более современный TLS (Transport Layer Security) для шифрования данных.

2. Каким образом обеспечивается безопасность контента веб-сервера при работе через HTTPS? 

- Шифрование данных: при использовании HTTPS данные, передаваемые между клиентом и сервером, шифруются, что делает их невозможными для прочтения злоумышленниками, перехватывающими трафик.

- Идентификация сервера: сервер предоставляет цифровой сертификат, подтверждающий его легитимность. Этот сертификат выдается сертификационным центром и содержит информацию о владельце сертификата, публичный ключ для шифрования и подпись, подтверждающую подлинность сертификата.

3. Что такое сертификационный центр? 
- Сертификационный центр (Центр сертификации) - это доверенная сторона, которая выдает цифровые сертификаты, подтверждающие подлинность владельца сертификата. Пример: Одним из известных сертификационных центров является "Let's Encrypt". Он предоставляет бесплатные SSL-сертификаты, которые используются для обеспечения безопасного соединения на множестве веб-сайтов. Владельцы веб-сайтов могут получить сертификат от Let's Encrypt, чтобы обеспечить шифрование и подтвердить свою легитимность в онлайн-среде.