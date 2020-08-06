---
layout: post
title:  "Черим линию из точек. Часть 2"
date: 2020-08-06 21:28:00 -0000
tags: Форт программирование unfinished
description: "Пост в котором оказывается, что алгоритм Брезенхэма не так уж плох."
---

Прежде, чем приступать к экспериментам с альтернативными алгоритмами рисования линий я решил написать программы для простейшей графики. Написал процедуры из главы 2 книги "[Графика для ZX Spectrm](https://zxpress.ru/book.php?id=193)". Они позволяют перейти от абсолютных экранных координат к относительной системе координат. Плюс - масштабируют систему координат. Сами по себе процедуры крайне простые. Но их пришлось переделать, чтобы все координаты оставались только челочисленными. Так как моя конечная цель - [привязать их](/blog/2020/forth-example) к Форту. А в Форт числа с плавающей точкой есть, но они нежелательны. Фактически, я спрятал в коде на Си все операции, которые вовлекают числа с плавающей точкой.

Два простейших примера заработали. Алгоритм Брезенхэма оказался куда лучше, чем я ожидал. Он прочерчивает линии почти целиком и даёт сбой в очень ограниченных случаях. Думаю, я займусь альтернативными алгоритмами чуть позже. Если займусь когда - нибудь.

![N-gon](https://res.cloudinary.com/dlqc5rp9l/image/upload/v1596710485/graphics/ngon_beyln8.png)

У связного многоугольника появляется смещение относительно начала координат. 

![Godseye](https://res.cloudinary.com/dlqc5rp9l/image/upload/v1596710485/graphics/godseye_tml59e.png)

У фигуры, которую в книгах по компьютерной графике называют Godseye с этим всё в порядке.

Дальше в книге ещё один пример интересной фигуры, а потом постепенный переход к алгоритмам удаления скрытых поверхностей и преобразования в пространстве. Где-то на этом месте мне придётся решить, какой объём кода оставить в Си, а какой реализовать уже на Форт. Скорее всего, в Си я оставлю все преобразования относительных координат в экранные и рисование графических примитивов. А в Форт попытаюсь реализовать всё остальное.
