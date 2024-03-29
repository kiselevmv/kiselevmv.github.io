---
layout: post
title:  "Очередная пятиминутка ненависти в адрес Utel"
date: 2012-05-02 11:53:00 -0000
tags: Блог 
---

Похоже, это пятая пятиминутка ненависти в адрес Utel в моём блоге. Всё объясняется просто, эта компания раздаёт неплохой интернет. Недорогой, быстрый, особое положение компании в Тюменской области позволяет. Поэтому я пользуюсь её услугами. С другой стороны, сервис в Utel/Уралсвязьинформ настолько ужасен, что компания наверняка останется в истории. 

Вчера я заменял связку дешёвый ADSL модем/Роутер с WiFi точкой доступа на ADSL интернет-центр от ZyXEL P-660HTW EE. Покупал я этот девайс в 2008 году, оставлял его на старой квартире, так как и не думал, что ещё когда-нибудь буду пользоваться ADSL-интернетом, но возвращение в Нижневартовск сделало использование ADSL почти неизбежным. Местные провайдеры связи, Прайд и Данцер не считают нужным давать пользователям стабильную связь, а Utel обеспечивает её даже по ADSL.

Сперва я попробовал воспользоваться настройкой интернета через ZyXEL Net friend скачанный с их сайта. Последняя версия этого "сетевого друга" вообще не знала, что делать с роутером. Более старая, также обнаружившаяся на сайте, была в этом отношении не столь безнадёжна, но двухчасовые попытки настроить сеть были безуспешны. Скорее всего, у Utel изменились настройки ADSL-интернета, а в утилите этого не учли, потому что она старая и её никто не обновляет.

К счастью, в роутере есть ещё и Web-морда и даже возможность настройки через telnet. Дело за малым, найти эти новые настройки ADSL-интернета на сайте Utel. Это оказалось несложным, на [странице сайта](http://hanty.u-tel.ru/Internet/setup) вроде бы всё описано:

```
Базовые настройки DSL-модема для подключения к услуге Домашний Интернет:

VPI (Virtual Path Identifier) = 1
VCI (Virtual Circuit Identifier) = 50
Тип инкапсуляции = PPP over Ethernet with LLC/SNAP (RFC 2516)
Категория сервиса = UBR
Режим включения = Bridge
```

Выполняю настройки, ввожу логин/пароль - ура, загорается индикатор Internet. Увы, доступа в сеть нет, броузер жалуется на неверные настройки DNS-сервера. Действительно, зачем серверу провайдера в XXI веке выдавать адреса DNS динамически. Про адреса DNS на сайте ни слова, разумеется. Может где и есть, но найти информацию оказалось непросто. Вбиваю найденную в сети настройку DNS для Уралсвязьинформ-Челябинск, неудача. Звоню в службу поддержки, из разговора стало понятно, что дуболом на другом конце провода не знает что такое DNS вообще, может лишь предложить попытаться ещё раз настроить соединение через Net friend. Решение обнаружилось на [Сургутском форуме](http://forumsurgut.ru/viewtopic.php?f=58&p=175167_).

```
MalZ
Если настроите его как рутер - проблем возникнуть не должно. Просто надо будет прописать :

IP : адрес xxx.xxx.xxx.xxx (должен в первых трёх колонках совпадать с IP адресом модема... например 192.168.1.xxx)
Маска подсети - произвольная , но лучше 255.255.255.0
Шлюз : 192.168.1.1 (если вы конечно не меняли значение в модеме)
DNS 1 : 217.20.80.40
DNS 2 : 212.96.192.1
```

Спасибо, MalZ. Всё работает. Теперь WiFi интернет стабильно раздаётся по всей квартире, D-Link DIR-300 "не пробивал" даже до ванны. Освободилась одна розетка и чуть места на столе. Думаю, скоро и Utel откажется от ADSL или я уеду из Нижневартовска, но пока жизнь стала чуть комфортней, хотя на это и пришлось убить три часа, два из которых оторваны от сна.