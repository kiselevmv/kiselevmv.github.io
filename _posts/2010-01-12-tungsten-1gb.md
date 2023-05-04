---
layout: post
title:  "Palm Tungsten T3 имеет проблемы с SD картами более 1 Гб"
date: 2010-01-12 20:46:00 -0000
tags: Гаджеты
---

В процессе освоения Tungsten T3 всплыла неприятная особенность машинки. Без проблем можно работать только с картами памяти до 1 Гб включительно. Для работы с обычными картами памяти (не SHDC) есть специальные патчи, но мой вчерашний кавалерийский наскок на 2 Гб карточку к полезному результату не привёл. Данные читаются, но вот никакие операции записи невозможны. Пока вставил карту памяти на 512 Мб с тем, чтобы или всё же вставить драйвер, который позволит писать на 2 Гб карту, либо купить карту на 1 гиг (что я, пожалуй, и сделаю). Учитывая, что T3 способен проигрывать mp3 с выключеным дисплеем около 6 часов плеера всё равно не получится. Да, это будет паркетный КПК который будет проситься к розетке каждый день-два. Но пока наконвертировал себе при помощи <a href="http://www.isilox.com/">iSiloX</a> статей из <a href="http://expert.ru">Эксперт Онлайн</a> и книгу "Ружья, микробы и сталь" и буду читать в комфортных условиях. Почему-то использовать iSilo с PocketPC у меня не получалось, созданные файлы не передавались при помощи ActiveSync на устройство автоматически, с HotSync же проблем почти нет. Почти касается того, что не получалось автоматически отправлять файлы на карту памяти, только в основную память устройства. Откуда их уже можно копировать на карту памяти, но чаще файлы просто удаляются после прочтения.

## UPDATE

<a href="http://kb.palmone.com/SRVS/CGI-BIN/WEBCGI.EXE?New,kb=PalmSupportKB,t=ooccase,case=obj%2834080%29">Согласно отчёту PalmOne</a> объём гарантированно работающих на Tungsten T3 карт памяти действительно ограничен 1 Гб. Остальные карты, как написано в отчёте, "могут работать, а могут не работать и возможно неожиданное поведение системы при их применении". Вот выдержка из отчёта.

> Maximum expansion card sizes and types compatible with Palm devices
> Article ID: 34080
>
> 1/5/2005
>
> These are the largest cards tested and certified compatible with Palm devices during product development.
>
> Important Higher capacity expansion cards may work in these devices, but they have not been tested. The device may not recognize content and free space above the stated limit below. Unless specifically listed, devices with an upper limit of 1GB or 2GB may not work with SDHC (Secure Digital High Capacity, SD 2.0) expansion cards.
>
> Note If you use a larger card than recommended, the Card Info application on your device may not report the correct amount of free space.
>
> Model 	Card type 		Maximum tested card size
> Centro 		microSD 		4GB SDHC
> Treo 755p 	miniSD 		4GB SDHC
> Treo 755p 	standard SD 	4GB SDHC
> Treo 700p 	standard SD 	4GB SDHC
> Install the Treo 700p Update to add this capacity.
> Treo 680 	standard SD 	4GB SDHC
> Install the Treo 680 Update to add this capacity.
> Treo 650 		standard SD 	2GB
> Treo 600 		standard SD 	2GB
> Tungsten T5 	standard SD 	2GB
> Tungsten T3 	standard SD 	1GB
> Tungsten T2 	standard SD 	1GB
> Tungsten T 	standard SD 	1GB
> Tungsten E2 	standard SD 	1GB
> Tungsten E 	standard SD 	1GB
> Zire 72		standard SD 	2GB
> Zire 71		standard SD 	1GB
> Zire 31		standard SD 	1GB
> Zire 21		standard SD 	1GB
> LifeDrive 		standard SD 	2GB
> See also Formatting an expansion card in a LifeDrive device.
> m515 		standard SD 	1GB
> m505 		standard SD 	1GB
> m500 		standard SD 	1GB
> m130 		standard SD 	1GB
> m125 		standard SD 	1GB 

Как это ни удивительно, но T3 работает с картами того же предельного размера, что и m125.