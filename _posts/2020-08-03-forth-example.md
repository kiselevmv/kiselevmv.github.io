---
layout: post
title:  "Пример программы на языке Форт"
date: 2020-08-03 19:38:00 -0000
tags: Форт программирование
description: "Я успешно определяю простые Форт-слова для перевода градусов Цельсия в Фаренгейты и обратно, сохраняю и загружаю простую Форт-программу. Но понимаю, что сделать графическое расширение для Форт будет сложнее, чем я ожидал."
---

После [компиляции pForth](http://mnlist.ru/blog/2020/pforth-exercise) самое время разобраться, как в принципе работают программы на Форт. И как добавлять свои форт-слова на языке С.

Решил сделать собственную, максимально простую программу для перевода градусов Цельсия в Фаренгейты и обратно. Когда-то я видел пример такой программы на Форт. Это классика, попробую сделать её без примера под рукой. Как переводить из [градусов Цельсия в Фаренгейты](https://www.aaamath.com/mea414x2.htm) и [обратно](https://www.aaamath.com/mea414x3.htm) читаем на [AAA Math](https://www.aaamath.com/), великолепный онлайн-справочник.

Для программирования используем pForth, который мы скомпилировали раньше. Если у вас нет pForth, можно вернуться на два шага назад и собрать его:

- [Установка Pelles C без прав администратора](http://mnlist.ru/blog/2020/pellesc-portable).
- [Эксперементируем с pForth](http://mnlist.ru/blog/2020/pforth-exercise).

## [Перевод градусов Фаренгейта в градусы Цельсия](https://www.aaamath.com/mea414x3.htm)

1. Вычитаем из градусов Фаренгейта 32.
2. Умножаем результат на 5/9. 

То, что это дробь критично для Форт, мы будем придерживаться цельночисленной арифметики. Никаких десятых долей градуса ни в исходных данных, ни в результате. Потеря точности будет очень умеренная.

## Определяем слово F>C

Короткие названия - традиция Форт. Когда-то приходилось умещать программы в "экраны", фрагменты примерно по 2 кБ из-за аппаратных ограничений. К счастью, сегодня таких ограничений нет, можно давать говорящие имена, но буду придерживаться ретро-традиции.

Алгоритм, фактически, приведён в предыдущем разделе. Осталось превратить его в форт-слово.

```forth
: F>C ( n -- n ) 32 - 5 * 9 / ;
```

Можно сразу испытать слово на примере из описания методики перевода.

![Испытываем F>C](https://res.cloudinary.com/dlqc5rp9l/image/upload/v1596447238/blog/pforth-f-to-c_pif60s.png)

## [Перевод градусов Цельсия в градусы Фаренгейта](https://www.aaamath.com/mea414x2.htm)

1. Умножаем температуру в градусах Цельсия на 9/5.
2. Добавляем смещение в 32 градуса.

Аналогично примеру выше - вся арифметика цельночисленная. pForth "умеет" дробную арифметику и можно было бы определить слово FF>C, где первый F означает число с плавающей точкой. В языке Си тоже нужно было бы определить две разных функции для вычислений с целыми числами и числами с плавающей точкой. На C++ и многих других языках можно было бы использовать их продвинутые возможности и определить одну функцию для обоих случаев. И Си и Форт - простые, старые языки программирования, поэтому придётся иметь дело с примерно одинаковыми проблемами.

## Определяем слово C>F

```forth
: C>F ( n -- n ) 9 * 5 / 32 + ;
```

Здесь подсказка ( n - n ) это, фактически, комментарий. Он показывает, что солово берёт со стека одно число - n и возвращает одно число - n. У pForth есть вомзожность использовать локальные переменные внутри слова, возможно я дойду до примера, где это будет полезно. С другой стороны, такая возможность работает только на некоторых реализациях Форт, программа сразу потеряет в переносимости.

Проверяем пример.

![Проверяем C>F](https://res.cloudinary.com/dlqc5rp9l/image/upload/v1596447329/blog/pforth-c-to-f_et5f5v.png)

Оба примера дали ожидаемый результат с учётом отбрасывания дробной части. Можно было бы запустить серию тестов. Но у Форт нет развитых средств тестирования. Это простое слово и можно быть уверенным, что ошибки тут нет.

А это уже преимущество языка. В Форт можно определить сложное слово, но так обычно не делают. Задача разбивается на настолько маленькие кусочки-слова, что они понятны даже не смотря на специфический синтаксис Форта. В данном случае такое программирование поощряет и сам язык и традиция программирования на нём. Когда все параметры передаются через стек, вызов коротких слов почти ничего не "стоит" программисту, не нужно оформлять вызов функции с параметрами. Низкая цена вызова слов-функций = частое использование этой особенности языка.

## Сохраняем программу

Форт позволяет сохранить определённые ранее слова. Т.е. можно сохранить исходный код, а можно сохранить словарь, "скомпилированный" из исходного кода. Разумеется, исходный код программ хранить нужно. Поэтому создаём файл `convert.fth` с обоими словами, определёнными выше. Там же можно делать комментарии, начинающиеся с `\ `. Я сохранил файл на GitHub, конечно. А локально в ту же папку, где лежит `pforth.exe`. Теперь можно запустить pforth и набрать `include convert.fth`. Форт загрузит и скомпилирует словарь. 

Можно сохранить словарь. Назвать конкретные плюсы этого я не могу. Исходное определение слова можно восстановить декомпиляцией, которую Форт умеет делать хорошо. В pForth достаточно набрать 'SEE F>C' и Форт восстановит определение слова. Но, насколько я понял, нельзя подгружать несколько словарей. Так что в виде словаря имеет смысл хранить разве что целую программу, чтобы её можно было запускать из командной строки.

Сохраняем словарь командой `c" custom.dic" SAVE-FORTH`. Потом можно будет загрузить этот словарь из командной строки:

    pforth.exe -dcustom.dic

## Неожиданные сложности с использованием libSDL из Форт

Я засел за Форт, чтобы сделать графические расширения, позволяющие рисовать подобно тому, как это [сделано в PostScript](/blog/2020/postscript-intro).

Вообще, в Форт довольно легко определять слова на языке Си. Пользовательские слова находятся в файле `csrc\pfcustom.c`. Всё настолько просто, что я даже разобрался с тем, как это делать и смог определить своё слово. Но библиотека SDL оказалась очень капризной. Для нормальной работы ей нужен вызов из `int main(int argc, char *argv[])`. Смотри пример в "[Эксперементируем с libSDL в Windows](/blog/2020/libsdl-windows)".

В случае же Форт придётся прятать вызов в глубинах программы, в файле `pfcustom.c`. Как я понимаю, работать libSDL будет, только если спрятать создание окна прямо в главном файле `pf_main.c`, где "правильно" определена функция `main`, а в других местах только управлять уже инициализированным libSDL. В принципе, это возможно. Всё равно я модифицирую исходный код. Но теперь задача выглядит даже более сложной, чем раньше.