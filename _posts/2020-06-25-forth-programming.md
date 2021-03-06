---
layout: post
title:  "Учебник языка Форт со средой программирования"
date: 2020-06-25 21:22:00 -0000
tags: Forth programming
---

Форт (Forth) довольно интересный язык программирования. Я бы сказал - привлекательный. Я не буду приводить здесь его характеристики, даже статья в [википедии](https://ru.wikipedia.org/wiki/%D0%A4%D0%BE%D1%80%D1%82_(%D1%8F%D0%B7%D1%8B%D0%BA_%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F)) даст неплохое представление об этом языке. У меня в блоге есть "[Заметки про форт](/blog/2015/forth-programming)". К сожалению, некоторые премущества этого языка сегодня совершенно бесполезны. Например, Форт отлично работал на 8-битных компьютерах и его легко было "завести" на новом или экзотическом компьютере. Собственно, сегодня форт по-прежнему используется на экзотических платформах, вроде [сорокаядерных процессоров](https://www.embedded.com/news-40-core-processor-with-forth-based-ide-tools-unveiled/). Остальное можно рассматривать как недостатки, добавляющие языку шарм, но не популярности среди разработчиков. Возможно, самым популярным применением языка форт является PostScript - язык, на который переводят документы, направляемые на печать, а также используемый в формате PDF. Но это не "чистый" форт, а скорее стековый язык программирования. Т.е. язык, унаследовавший основную черту Форт, но уже далеко ушедший от него в своём развитии.

Вкратце особенности языка - особая форма записи, называемая "обратной польской нотацией". Она очень облегчает жизнь синтаксическому анализатору языка программирования, но требует привычки в использовании. Хранение данных в стеке. Хотя в языке есть строки, переменные и массивы - все операции проводятся только над числами в стеке. Отсутствие чисел с плавающей точкой. Впрочем, числа с плавающей точкой есть в некоторых диалектах Форт. Но за приведением типов, количеством аргументов и всем подобным должен следить программист. Отсутствие каких-либо стандартных библиотек. Думаю, каждый кто попытался изучать Форт назовёт ещё не один недостаток. Но в этом языке есть очарование.

Статья не о самом Форте, а о отличной находке, позволяющей выучить/вспомнить основы Форт. Особенность языка в том, что его просто реализовать. Ему не нужен соложный [синтаксический анализатор (парсер)](https://ru.wikipedia.org/wiki/%D0%A1%D0%B8%D0%BD%D1%82%D0%B0%D0%BA%D1%81%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D0%B9_%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%82%D0%BE%D1%80). Программист может перенести Форт на новую платформу за несколько дней. И нашёлся тот, кто реализовал Форт на языке JavaScript. Теперь Форт можно осваивать в [Easy Forth](https://skilldrick.github.io/easyforth/). Это одновременно и учебник языка и среда программирования. 

Более продвинутый учебник называется [Starting Forth](https://www.forth.com/starting-forth/0-starting-forth/). Надеюсь, в следующем материале я разберу несколько примеров из этого учебника, чтобы показать красоту Форт. Я сделаю это, если получится встроить среду исполнения форт-программ на JavaScript в свою запись в блоге.

Освоить азы Форт в Easy Forth можно с некоторым знанием английского языка и знанием самых основ программирования. Вся прелесть в том, что даже основы программировния тут нужны самые базовые. Стек легко представить как строчку из чисел с которыми делают какие-то манипуляции. Это даже легче, чем представить себе переменную с которых начинается освоение большинства языков программирования. Если вы знаете язык С - тем лучше, многие языковые конструкции дополнительно поясняются через аналоги на С.

Я начинал освоение Форта я книги "Язык Форт и его реализации". Этой же книгой всё для меня закончилось. Мне было лет 12-13, когда я её купил. Небыло интернета и из компьютеров был ZX Spectrum, но небыло реализации Форт для этого компьютера. Увы, я не стал программистом на Форт и программистом вообще. Но, кажется, стал любителем Форта.

P.S. Нашёл много примеров графических программ на языке PostScript

- Статья [Life in PostScript](https://www.tjhsst.edu/~edanaher/pslife/) описывает, как написать программу Life на языке PostScript. Т.к. здесь не статическая, а динамическая картинка - разные прсмотрщики по-разному её открывают. Одни показывают только первый статический экран. другие обновляют картинку каждый раз при "пролистывании" на новую страницу.
- Статья ["Снежинка Коха"](http://jonsson.eu/programs/postscript/koch/) описывыает программу, рисующую фрактальную снежинку, она же фрактал Коха.
- Статья ["Аттрактор Лоренца"](http://jonsson.eu/programs/postscript/odesolv/) описывает решение системы дифференциальных уравнений в программе на PostScript

Скачать их можно в моём githab репозитории [Postscript](https://github.com/kiselevmv/Postscript). Файлы можно скачать в консольном или графическом клиенте для Postscript, а можно вызвать выпадающее меню кнопки `Code` и выбрать пункт `Download ZIP`.