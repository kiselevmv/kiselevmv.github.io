---
layout: post
title:  "Таймер-помидор на micro:bit"
date: 2016-12-05 14:37:00 -0000
tags: pomodoro gtd DIY
---

Увлёкся "[помидорным тайм-менеджментом](https://lifehacker.ru/2009/06/09/izmerjajjte-zadachi-v-pomidorah-ehffektivnoe-planirovanie-proshhe-chem-vy-dumaete/)", он же Pomodoro management. И придумал сам себе этакий помидорный челлендж. Сделать десяток разных таймеров-помидорок. Любых, от механических до программ на одноплатные компьютеры. Первым устройством, конечно, должен был бы стать обычный кухонный таймер. Но мне не нравится то, что он не деликатно советует мне отдохнуть, а грубо прерывает звоном. К тому же на работе им не попользоваться. Так что мой первый таймер здесь.

## Первый таймер - на одноплатном компьютере [micro:bit](http://microbit.co.uk/)

Плюсы конструкции - на плате уже имеется матрица из 25 светодиодов для индикации и две кнопки для управления. Так что можно обойтись одной платой, без модулей расширения. Запитать плату можно через micro-USB разьём, или источником питания на 3В с двухконтактным [JST-PH разьёмом](https://en.wikipedia.org/wiki/JST_connector), либо с от любого источника питания 3В через контакты "земля" и +3В. Пока идёт с Китая батарейный отсек с JST разьёмом и выключателем на 2ААА батарейки я запитал от самого дешёвого батарейного отсека на 2АА батарейки. Питание прикрутил винтиками к плате. 

Программировать можно на python и это предпочтительно. Но первый таймер я написал на специальном языке - Microsoft Touch Develop. Это язык программирования, где программа составляется из блоков, которые перетаскивают в тач-интерфейсе. Выглядит программа так:

![Код для pomodoro timer](http://2nature.me/files/micro-code.jpg)

Проблема в том, что на питоне нет эмулятора устройства. Чтобы протестировать программу - её нужно компилировать, сохранять на устройство и запускать. Пока не освоишься с программированием - лучше полагаться на учебные языки программирования для устройства.

Если нужно, чтобы таймер издавал звуки - лучше купить [плату расширения](https://www.kitronik.co.uk/5610-mipower-board-for-the-bbc-microbit.html) с батарейным отсеком для элемента CR2032 и пьезо-пищалкой. Батарейки CD2032 хватает далеко не так надолго, как двух ААА, но часов на 8-10 работы с горящими светодиодами хватит. Мне не хочется, чтобы устройство грубо прерывало меня звонками, поэтому я просто защитил устройство простейшим корпусом из резаного оргстекла.

Возможности компьютера куда шире, чем просто быть таймером. Поддерживается радиосвязь на короткие дистанции, bluetooth. Есть компас и акселерометр. На сайте проекта есть примеры использования.

То, что программы нужно писать онлайн - и плюс и минус. Минус, несомненно, в том, что программы не получится распространять, если ты не британский учитель. Чтобы распространять код нужно иметь учётную запись на сайте, а её дают только учителям или рарегестрированным преподавателям образовательной программы micro:bit. Поэтому исходного кода таймера я здесь не привожу. Опубликую его, если перепишу таймер на питоне.

Цена решения:

- [micro:bit](https://www.kitronik.co.uk/5613-bbc-microbit-board-only.html) -  £13

- [корпус и батарейный отсек](https://www.kitronik.co.uk/5617-bbc-microbit-with-mipro-case-and-accessories.html) для micro:bit - £17 или [пьезо-пищалка](https://www.kitronik.co.uk/5610-mipower-board-for-the-bbc-microbit.html) с батарейным отсеком для элемента CR2023 - £4.15.

Итого - от 1500 до 2500 руб по курсу на декабрь 2016 года. Плюс стоимость доставки, она везде разная. Можно найти очень недорогую доставку UK Royal Mail, около 500 руб. Также можно найти micro:bit со вторичного рынка на аукционах. В самом дешёвом случае - можно напечатать корпус на 3D принтере или вовсе обойтись без копуса, а батарейный отсек заказать на Aliexpress за 130 рублей, включая доставку. Так что можно получить набор за 1000 рублей в предельном случае.

Это куда дороже обычного кухонного таймера, но дешевле большинства остальных электронных конструкций. Надёжность очень высока, micro:bit - прочное устройство, рассчитанное на школьников. А сам таймер вполне удобен для использования.