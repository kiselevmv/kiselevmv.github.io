---
layout: post
title:  "Эксперементируем с libsdl в Windows"
date: 2020-07-30 15:19:00 -0000
tags: programming
comments: true
description: "Об успешной попытке собрать Hello World программу с библиотекой SDL в Windows."
---

В прошлых публикациях я описывал, как [установить среду разработки Pelles C](/blog/2020/pellesc-portable) без прав администратора и как [скомпилировать pForth для Windows](http://mnlist.ru/blog/2020/pforth-exercise) в Pelles C. Теперь нужно разобраться с программированием с использованием библиотеки libsdl2 в Windows. Для этого есть великолепное и регулярно обновляемое руководство [Beginning Game Programming v2.0](https://lazyfoo.net/tutorials/SDL/index.php). В качестве среды разработки для Windows рассматриваются `Code::blocks`, `Visual Studio 2019`, `Visual Studio.NET 2010 Ultimate` и компилятор MinGW для командной строки. Для `Pelles C` отдельного раздела руководства нет, но разобраться оказалось не так уж и сложно.

Библиотеки SDL2 для разработки нужно скачать с [сайта проекта](http://libsdl.org/download-2.0.php). Нужны библиотеки для Visual C++, а не для MinGW. Дальше нужно создать новый проект для программы для командной строки Windows 64. 

![Pelles C new project](https://res.cloudinary.com/dlqc5rp9l/image/upload/v1596084327/blog/pellesc-sdl2-new_k46yyn.png)

Содержимое пакета с библиотекой разработчика SDL2 я распаковал прямо в папку проекта. Не важно, куда именно она будет распакована, всё равно придётся подключать эту библиотеку вручную. Для этого редактируем свойства проекта `Project --> Project options` переходим на пункт `Folders`, там опцией `New folder` добавляем папку `Lib\x64` для `Type --> Libraries` и папку `include` для `Type --> Includes`

![Pelles C includes](https://res.cloudinary.com/dlqc5rp9l/image/upload/v1596084327/blog/pellesc-sdl2-includes_x3rebs.png)

Дальше нужно подключить библиотеку в линкере. Переходим к пункту `Linker` и указываем библиотеку `SDL2.lib`.

![Pelles C linker](https://res.cloudinary.com/dlqc5rp9l/image/upload/v1596084327/blog/pellesc-sdl2-linker_bs73fy.png)

Наконец, на пункте `Compiler` ставим галочку `Enable Microsoft extensions`. Это подавит огромное количество предупреждений компилятора при подключении библиотеки libsdl2.dll. Вроде бы, этот шаг необязательный, т.к. мы уже указали линкеру использовать статическую библиотеку. Но лучше сделать.

![Pelles C compiler](https://res.cloudinary.com/dlqc5rp9l/image/upload/v1596084327/blog/pellesc-sdl2-compiler_uf22xn.png)

Теперь в проекте можно содать файл `test1.c` и ввести туда программу из [первого урока руководства](https://lazyfoo.net/tutorials/SDL/01_hello_SDL/index2.php). Попытка компиляции закончится ошибкой. 

```
test1.c(10): error #2120: Redeclaration of 'SDL_main', previously declared at C:\Apps\Doc\Prog\SDL2-test\include\SDL_main.h(121); expected 'int __cdecl function(int, char * *)' but found 'int __cdecl function(int, char * * *)'.
*** Error code: 1 ***
```

Либо руководство чуть устарело, либо то, что работает на других компиляторах не работает с Pelles C. Я даже не понимаю в чём проблема, но благодаря гуглу есть [рецепт решения](https://stackoverflow.com/questions/37219760/bypassing-int-mainint-argc-char-argv-in-sdl2). Добавляем строчку `#define SDL_MAIN_HANDLED` непосредственно перед `#include <SDL.h>`. Компиляция успешна и тестовая программа работает. Можно двигаться к следующим урокам.
