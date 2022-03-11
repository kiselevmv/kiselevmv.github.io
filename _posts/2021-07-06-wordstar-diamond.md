---
layout: post
title:  "О ромбе Wordstar (Wordstar diamond)"
date: 20:51:00 -0000
tags: Блог Wordstar клавиатуры
description: "Пост о том, что же такое ромб Wordstar и почему он может пригодится современному пользователю."
---

Трудно перевести "wordstar diamond" на русский язык. В английском языке "diamond" это собственно алмаз и форма алмаза. В этом выражении имеется в виду форма алмаза. Давайте назовём это "ромб Wordstar". Он получил своё название из-за характерной формы основного блока клавиш.

Основа ромба Wordstar `Ctrl` + клавиши `E`, `S`, `D` и `X`. Они перемещают курсор вверх, влево, вправо и вниз соответственно.

Это "внутренний" ромб Wordstar. Вокруг него расположен "наружный" ромб Wordstar. `Ctrl+A` перемещает курсор на слово назад, а `Ctrl+F` на слово вперёд. Клавиши `Ctrl+R` и `Ctrl+C` работают как Page up / Page down. Клавиши `Ctrl+W` и `Ctrl+Z` используют тип скроллинга, который не используется в современных текстовых редакторах. Курсор остаётся на месте, а текст под ним прокручивается на строку вверх и вниз. Это характерная особенность Wordstar и некоторых других старых редакторов текста. В редакторе MS Word и других современных текстовых редакторах, ориентированных на подготовку печатных документов, текст - это набор страниц, по которым перемещается курсор. В Wordstar текст скорее похож на свиток. Можно перемещать по нему курсор-указку, а можно прокручивать сам свиток, а указка останется неподвижной. 

![Свиток и указка. Фотобанк Лори](https://res.cloudinary.com/dlqc5rp9l/image/upload/v1625564204/blog/keyboard/kbd-scroll_dnpohz.jpg)

Во времена, когда использовали Wordstar просто не хватало мощности компьютера, чтобы реализовать концепцию документа разбитого на страницы. Прошло время, и теперь большая часть документов, которые готовят в текстовых редакторах, никогда не появится в печатном виде. Концепция документа-свитка больше подходит для редактирования таких текстов. А значит и прежний способ скроллинга текста снова востребован.

![Base WordStar diamond](https://res.cloudinary.com/dlqc5rp9l/image/upload/v1626084234/blog/keyboard/kbd-edxs_auk29h.png)

Теперь все базовые операции навигации по тексту можно выполнять одной левой, не снимая руки с буквенных клавиш клавиатуры. Это заметно ускоряет правку текста, но при условии "правильного" расположения клавиши Ctrl вместо Caps Lock. Это работает либо с Happy hacking keyboard. Либо с помощью переопределения клавиши CapsLock при помощи программы AutoHotkey, либо с помощью программирования клавиатуры форм-фактора 60% или даже 40%.

Следующие клавиши не относятся к "ромбу WordStar", но тоже нажимаются левой рукой. Это `Ctrl+G` который аналогичен клавише `Delete` и удаляет символ справа от курсора. В оригинальном WordStar клавиша `Ctrl+H` заменяла `Backspace`, но я не переопределял ее, так как клавиша `Backspace` есть на клавиатуре и нажать ее проще. `Ctrl+T` удаляет слово справа от курсора. Слово слева от курсора удаляется "по-старинке" при помощи `Ctrl+Backspace`.

Клавиша `Ctrl+V` действовала аналогично клавише `Insert`. А клавиша `Ctrl+B` обновляла форматирование абзаца. Я не использую эти клавиши, но в оригинальном Wordstar они использовались.

 <pre>
    ^W   ^E    ^R   ^T
         |
^A---^S--+--^D---^F---^G
         | 
    ^Z   ^X    ^C   ^V  ^B
 </pre> 


В идеале - управление курсором ромбом Wordstar выполняются одной левой рукой. Когда-то клавиша `Ctrl` находилась на месте клавиши `Caps Lock` на современных клавиатурах. При таком расположении `Ctrl` все комбинации ромба Wordstar нажимаются легко. При печати десятипальцевым методом достаточно отвести влево мизинец и можно нажимать эти клавиши лёгкими движениями пальцев. С современным расположением `Ctrl` эти сочетания совершенно неудобны. Думаю, поэтому от них в конце концов и отказались. Но в клавиатуре Happy hacking keyboard `Ctrl` расположен на месте `Caps Lock` и пользоваться этими сочетаниями опять удобно. 

![Happy hacking keyboard](https://res.cloudinary.com/dlqc5rp9l/image/upload/v1624186776/blog/keyboard/hhkb-60_tmz6hd.jpg)

Исторически, такие сочетания клавиш использовались в Wordstar из-за того, что на старых компьютерах отсутствовали клавиши Insert, Home, Page up, Page down. Они стали стандартными только с появлением клавиатуры IBM PC. Вообще говоря, на тех мини-компьютерах, на которых работал Wordstar и курсорных клавиш вполне могло не быть. Это происходило по разным причинам. Одни компьютеры заимствовали клавиатуры для компьютерных терминалов - "тонких клиентов" того времени. На терминалах небыло полноэкранных текстовых редакторов. Текст редактировался построчно, поэтому и в курсорных клавишах нужды небыло. А в компьютере Macintosh 128k, например, клавиш небыло, чтобы поощрять пользователей пользоваться мышью. Универсальный текстовый редактор требовал универсальных управляющих клавиш. И ромб Wordstar, где использовались только клавиши, которые были на любом компьютере того времени и стали таким универсальным набором.

![Macintosh 128k клавиатура](https://res.cloudinary.com/dlqc5rp9l/image/upload/v1625564566/blog/keyboard/kbd-macintosh-128k_tezqrd.png)

Ромб Wordstar был очень популярен, в своё время. Эти сочетания клавиш использовались в редакторах IDE от компании Borland, очень популярных в 1990х. В текстовом редакторе для DOS `edit`. Он работал и в Windows вплоть до Windows 7. И в некоторых других, менее популярных, но многочисленных текстовых редакторах. Сейчас эти клавиши не используются. Но, парадоксальным образом, с распространением клавиатур [форм-фактора 60%](/blog/2021/keyboard_layout_form#форм-фактор-60) такие сочетания клавиш снова стали удобными. На этих клавиатурах курсорные клавиши "повешены" на буквенные клавиши, которые нужно нажимать совместно с клавишей `Fn`. К сожалению, на всех малоформатных клавиатурах это сделано отвратительно неудобно. Конкретно в "Happy hacking keyboard" курсорные клавиши разместили так

![Happy hacking keyboard arrow keys](https://res.cloudinary.com/dlqc5rp9l/image/upload/v1625686061/blog/keyboard/kbd-hhkb-arrows_tdodve.jpg)


Есть небольшая группа людей, которые и сейчас пользуются Wordstar. Джордж Мартин [пишет книги в WordStar](https://habr.com/en/post/388859/). В качестве причины он называет то, что WordStar делает всё, что требуется от текстового процессора и не делает лишнего. Другой писатель, Роберт Джеймс Сойер, тоже пишет свои произведения в Wordstar. В качестве причины он приводит удоство навигации по тексту и ту же минималистичность, что и Дж. Мартин. И я их понимаю, стоит распробовать редактирование текста с ромбом Wordstar и этот способ кажется самым естественным и удобным. Удобно всё, от логики работы блоками текста, до навигации по тексту и управлению форматированием текста с клавиатуры.

Мартин работает на отдельном старинном компьютере с Wordstar, установленном у него в подвале. Джеймс Сойкер работает на современном компьютере, на котором Wordstar запущен в [эмуляторе MS DOS](https://sfwriter.com/ws-vdos.htm). Для мня это слишком экстравагантно. Дело в том, что Wordstar очень старый текстовый редактор с очень удобными клавиатурными комбинациями. В Wordstar нет подсветки синтаксиса программ. Нет простого способа преобразовать документ Wordstar в документ MS Word. И вообще нет способа сохранить документ MS Word в формат Wordstar без потери большей части форматирования. В  Wordstar нет таблиц, нет формул, нет сносок. Короче говоря, он годится, разве что, для писателей. Но не для подготовки научного или технического текста. Это не вина текстового редактора, просто он не развивался более 20 лет. Поэтому я пошёл другим путём и перенёс сочетания клавиш Wordstar в современные текстовые редакторы. Но это уже тема другого поста.