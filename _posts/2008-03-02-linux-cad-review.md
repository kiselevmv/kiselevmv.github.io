---
layout: post
title:  "Нашёл старый обзор CAD-программ для Linux"
date: 2008-03-02 20:09:00 -0000
tags: Software
---

<a href="http://www.debryansk.ru/~tereshin/CAD4Linux.ru/CAD4Linux.html">CAD системы для Linux</a>.  Обзор CAD-систем для Linux по состоянию на 2000 год. Вообще, стоит помнить, что CAD вышел из мира Unix. Но если посмотреть динамику, то видно, что коммерческих CAD для Linux стало даже меньше, чем в 2000 году. Большая часть ссылок не работает, программы продолжают существовать, но на их сайтах нет даже ссылок на старые Unix-версии. Появилось большое количество open source CAD программ (и я их обязательно коснусь), но ещё не встретил ни одной, удовлетворяющей моим целям. И, если говорить о работе с форматом dwg, и не встречу. Консорциум производителей, не то лицензирующий этот формат у Autodesk, не то исследующий его методом обратной инженерии, берёт деньги за код для работы с dwg. И это вполне понятно. Так что программ под лицензией GPL, способных читать и писать файлы в формате dwg, пожалуй, ждать не стоит.

Похоже, наиболее реалистично работать с программами, запускаемыми в wine.

Преимущества: тот же Linux, окно windows-программы ничем не отличается от окон других linux-программ. Нет или почти нет потери в производительности. 

Недостатки: если текущая версия программы работает в wine - нет гарантии, что будет работать следующая. Если работает сам CAD, нет гарантии, что будут работать сторонние дополнения к нему.

Оптимально, если сам производитель приложит минимальные усилия к wineфикации своей программы. Не будет ломать совместимость в новых версиях, доработает wine до полной поддержки всех функций. Так делает, например, Google, распространяя программу <a href="http://picasa.google.com/linux/">Picasa для Linux</a>. Тратится в разы меньше усилий по сравнению с созданием "родного" для Linux приложения и достигается такой же результат. Благо, гибкости ОС Linux для этого вполне достаточно.