---
layout: post
title:  "OpenShell - замена кнопке пуск"
date: 2020-06-28 15:44:00 -0000
tags: lifehack
description: "Для тех, кто так и не привык к тому, что Microsoft сделали с кнопкой &#8222;Пуск&#8220; в Windows есть альтернатива - OpenShell."
---

Windows совершенствуется уже несколько десятилетий. В целом, это надёжная операционная система с неплохим интерфейсом. Но с кнопкой "Пуск" в том виде, как она выглядит сейчас многие так и не смирились. Классическая кнопка "Пуск" была простой, понятной и эффективной. Единственное, для чего нужна эта кнопка - это быстрый доступ к запуску приложений, некоторым папкам и панели управления. От этих принципов операционная система отошла. К счастью, есть возможность сделать как было. Пускай и с привлечением сторонней программы. Эта программа - OpenShell. Не буду писать про её коммерческого предшественника - Classic Shell. Эта программа больше не развивается, хотя [сайт](http://www.classicshell.net/) продолжает работать. В OpenShell два компонента: `Classic IE` (классический проводник Windows) и `Start Menu` (собственно классический интерфейс кнопки `Пуск`). 

Проблема в том, что мой основной ноутбук с Windows - рабочий. Нельзя просто взять и установить подобную программу, потому что нужны полномочия администратора. К счастью, можно обойтись без установки. Если скачивать [релиз программы](https://github.com/Open-Shell/Open-Shell-Menu/releases) то получится скачать только установщик. Но вот в разделе [последних сборок](https://ci.appveyor.com/project/passionate-coder/open-shell-menu/branch/master/artifacts) есть сборка с отладочной информацией. Она без инсталлятора. Минус сборки с отладочной информацией в большем размере файла. Но даже с отладкой размер исполняемого файла и библиотеки не превышает 10 Мб. Мелочи по современным меркам. Поэтому скачиваем файл OpenShellPDB_4_4_145.7z или более новую версию, но с суффиксом "PDB". В архиве две версии программы, 32 и 64-разрядные. Копируем содержимое каталова версии с нужной разрядностью в папку OpenShell, которая расположена в любом каталоге компьютера на который у вас есть права на чтение и запись. Добавляем файл StartMenu.exe в автозагрузку и запускаем программу, перезагружаться не требуется.

![Open-shell](https://res.cloudinary.com/dlqc5rp9l/image/upload/v1625194219/blog/software/open-shell_r5nlv9.png)

Программа работает. Кликом правой кнопкой мышки можно вызвать контекстное меню с пунктом `Настройки`, где можно поменять скины, изменить поведение программы. Настроек довольно много, но они вполне понятны.

Кнопка `Пуск` в стиле Windows 7 упростила мою работу и сделала её более приятной. Рекомендую всем.
