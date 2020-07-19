---
title:  "Делаем компьютер-клавиатуру. Вечер первый"
date: 2019-07-09 14:25:00 -0000
tags: DIY retro
---

Начало публикации в [предыдущей статье](rpz_keyboard). Там описана концепция того компьютера, который я хочу получить.

Всего на проект у меня ушло три вечера. Первый ушёл на то, чтобы разобрать клавиатуру и вырезать рёбра жёсткости из нижней части клавиатуры. Именно из-за наличия изрядного размера пустотелого утолщения в нижней части клавиатуры проект стал возможным. Я уже пытался сделать клавиатуру-компьютер раньше, но нигде в клавиатурах небыло ничем не занятого пустого пространства. Я думаю, что создатели клавиатуры по крайней мере держали в голове вариант с вставкой в неё самого Raspberry Pi, это достаточно очевидное решение.

Для работы нужен дремель, резец, разделитель. Я использовал ещё и бокорезы. Я не фотографировал каждый этап процесса, т.к. не планировал делать из этого статью. Разобрать клавиатуру несложно, например, разобрать iPod Classic сложнее. Нужен пластмассовый или металлический разделитель, как на рискунке ниже. Подойдёт и пластиковый аналог, но щель между двумя половинками корпуса клавиатуры очень тонкая, чем тоньше будет инструмент - тем лучше.
  
![инструмент iFixit](http://2nature.me/files/retro-computer1.jpeg)

Им нужно надавливать на каждый замочек, соединяющий половинки клавиатуры (выделены внизу синими овалами) и разводить половинки. Начинать лучше с углов, после раскрытия 3-4 замочков половинки клавиатуры разойдуться и действовать станет легче. Верхняя и нижняя половинки клавиатуры не нужно разнимать сразу после того, как все замки будут открыты, они соединены ещё и шлейфом клавиатуры и заземлением. Заземление сделано на фольге с липучкой, её можно аккуратно отделить от металлической подложки клавиатуры. А для снятия шлейфа потребуется открутить три шурупа крышечки, прикрывающей USB-хаб и контроллер клавиатуры. Шлейф прижимается планкой, которую нужно аккуратно сдвинуть и он легко выйдет из своего паза. Теперь половинки клавиатуры разделены.

Рёбра жёсткости удобно срезать дремелем с оснасткой - отрезным диском. Проблема в том, что форма днища клавиатуры сложная, а пластик, из которого она сделана, имеет низкую температуру плавления. Поэтому дремелем можно срезать всё довольно грубо. Для чистовой обработки я использовал бокорезы для срезания рёбер прилегающих к днищу и стенкам. Совсем чистая обработка требуется только около задней стенки днища клавиатуры. Там, где Raspberry Zero будет прилегать к стенке. Это я зачистил резцом. Зачищать начисто всё будет лишней работой, небольшие "порожки" не помешают в дальнейшем. 

![расположение защёлок](http://2nature.me/files/retro-computer2.jpeg)

После зачистки днища от рёбер жёсткости нужно сделать отверстия для портов Raspberry Zero. Я решил, что питание будет подаваться прямо на Raspberry, а уже оттуда будет запитываться вся "начинка" устройства. В интернете есть и другие варианты клавиатуры-компьютера. Например, с встроенным аккумулятором и зарядным устройством. Отверстия - более ответственный этап работы, их нужно аккуратно разметить. На этом этапе нужно продумать, как плата будет крепиться к днищу. От этого будет зависеть высота, на которой будут прорезаны отверстия. Крепить Raspberry к днищу я решил на винты М2.5. Думал использовать спейсеры, просверлить под ними клавиатуру и закрепить их винтами к корпусу. Вышло бы очень надёжно, но у меня не нашлось достаточно коротких спейсеров. Думаю, это к лучшему. У меня вышло более аккуратно снаружи. Я накрутил на каждый винт гайку, прикрутил их к Raspberry, нанёс на головку каждого винта по капле суперклея для пластика и установил сборку на днище так, чтобы порты упирались в стенку. Потом перманентным маркером обвёл контуры портов, снял Raspberry с болтов и дремелем с оснасткой - сверлом я высверлил отверстия с правой и левой части контура, а резцом прорезал пластик между ними. Получилось довольно аккуратно, если не приглядываться. 

Но это было ошибкой. Мне не следовало приклеивать винты с самого начала, их нужно было закрепить потом, когда порты Raspberry можно было бы уже просунуть в готовые отверстия. Это дало бы мне всего 1-2 мм, но облегчило бы подключение пиреферии к портам. Сейчас штекеры разъёмов вставляются в гнёзда, но держатся там недостаточно плотно из-за того, что не вставляются на полную длину. Сегодня я бы сделал работу с учётом этого 

![готовые отверстия](http://2nature.me/files/retro-computer3.jpeg)

На эту работу ушёл весь первый вечер. Продолжение - в статье про [второй вечер](rpz_keyboard_day2) сборки.