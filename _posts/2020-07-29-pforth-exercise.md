---
layout: post
title:  "Эксперементируем с pForth"
date: 2020-07-29 19:42:00 -0000
tags: programming
comments: true
---

В прошлой публикации я [установил Pelles C](/blog/2020/pellesc-portable) на рабочий компьютер без прав администратора. Мне это нужно для того, чтобы собрать одну из реализаций языка Форт - [pForth](https://github.com/philburk/pforth). В репозитории проекта на GitHub нет релиза, т.е. собранных файлов. А если бы и был - мне понадобится модифицировать код. Поэтому всё равно нужно собрать проект самому. К счастью, это оказалось несложно.

Клонируем проект командой

    git clone https://github.com/philburk/pforth
	
Или делаем это любым клиентом для GitHub с графической оболочкой. В папке проекта есть каталог `build/win32/vs2017` с файлом проекта для Visual Studio 2017. Проблема в том, что Pelles C не открывает файлы проекта VS 2017. С другой стороны, это не такая уж и проблема. Код pforth довольно прост. Открываем файл проекта `pforth_main.vcxproj`. Это xml файл, где перечислены файлы проекта:

``` xml
<ItemGroup>
    <ClCompile Include="..\..\..\csrc\pfcompil.c" />
    <ClCompile Include="..\..\..\csrc\pfcustom.c" />
    <ClCompile Include="..\..\..\csrc\pf_cglue.c" />
    <ClCompile Include="..\..\..\csrc\pf_clib.c" />
    <ClCompile Include="..\..\..\csrc\pf_core.c" />
    <ClCompile Include="..\..\..\csrc\pf_inner.c" />
    <ClCompile Include="..\..\..\csrc\pf_io.c" />
    <ClCompile Include="..\..\..\csrc\pf_io_none.c" />
    <ClCompile Include="..\..\..\csrc\pf_main.c" />
    <ClCompile Include="..\..\..\csrc\pf_mem.c" />
    <ClCompile Include="..\..\..\csrc\pf_save.c" />
    <ClCompile Include="..\..\..\csrc\pf_text.c" />
    <ClCompile Include="..\..\..\csrc\pf_words.c" />
    <ClCompile Include="..\..\..\csrc\stdio\pf_fileio_stdio.c" />
    <ClCompile Include="..\..\..\csrc\win32_console\pf_io_win32_console.c" />
  </ItemGroup>
  <ItemGroup>
    <ClInclude Include="..\..\..\csrc\pfcompfp.h" />
    <ClInclude Include="..\..\..\csrc\pfcompil.h" />
    <ClInclude Include="..\..\..\csrc\pfdicdat.h" />
    <ClInclude Include="..\..\..\csrc\pfdicdat_arm.h" />
    <ClInclude Include="..\..\..\csrc\pfinnrfp.h" />
    <ClInclude Include="..\..\..\csrc\pforth.h" />
    <ClInclude Include="..\..\..\csrc\pf_all.h" />
    <ClInclude Include="..\..\..\csrc\pf_cglue.h" />
    <ClInclude Include="..\..\..\csrc\pf_clib.h" />
    <ClInclude Include="..\..\..\csrc\pf_core.h" />
    <ClInclude Include="..\..\..\csrc\pf_float.h" />
    <ClInclude Include="..\..\..\csrc\pf_guts.h" />
    <ClInclude Include="..\..\..\csrc\pf_host.h" />
    <ClInclude Include="..\..\..\csrc\pf_inc1.h" />
    <ClInclude Include="..\..\..\csrc\pf_io.h" />
    <ClInclude Include="..\..\..\csrc\pf_mem.h" />
    <ClInclude Include="..\..\..\csrc\pf_save.h" />
    <ClInclude Include="..\..\..\csrc\pf_text.h" />
    <ClInclude Include="..\..\..\csrc\pf_types.h" />
    <ClInclude Include="..\..\..\csrc\pf_win32.h" />
    <ClInclude Include="..\..\..\csrc\pf_words.h" />
  </ItemGroup>
```

![Create pforth project](https://res.cloudinary.com/dlqc5rp9l/image/upload/v1596013459/blog/pellesc-pforth_cevrlv.png)

Теперь просто открываем Pelles C, создаём новый консольный проект для Windows 64. Создаём этот проект *внутри* клонированного с GitHub проекта pforth. Можно собрать в папке `build`, так будет правильнее, но я посчитал это неудобным и создал проект прямо в корневой папке. Вручную добавляем к проекту все файлы, которые перечислены выше и сохраняем проект.

![Add pforth files](https://res.cloudinary.com/dlqc5rp9l/image/upload/v1596013460/blog/pellesc-pforth-project_ip392j.png)

Убедился, что подключены 64-разрядные библиотеке. pforth можно собирать для 64-разрядных операционных систем.

![Check libs](https://res.cloudinary.com/dlqc5rp9l/image/upload/v1596013459/blog/pellesc-pforth-win64_sg0zvw.png)

Теперь можно жать `Project --> Build pforth.exe` и проект успешно скомпилировался.

Пока это "сырой" Форт, в котором определены только базовые слова. Читаем [руководство](http://www.softsynth.com/pforth/pf_ref.php) к pForth. Там описано четыре шага.

1. Скомпилировать pForth в исполняемый файл.

Это то, что мы сделали.

2. Запустить pForth с инсрукцией `-i`, чтобы построить словарь Форт. Основные слова языка содержатся в файле `system.fth`.

Нужный файл находится в папке "fth". Переходим в неё и исполняем команду.

    ..\pforth -i system.fth

Словарь слов форта собирается и сохраняется в файл "pforth.dic". Если теперь запускать форт просто командой `pforth` - он загрузит словарь автоматически. Самое время запустить тесты.

Запускаем Форт из той же папки "fth"

   ..\pforth
   
Запускаем тесты:

    include tester.fth
    include coretest.fth
    
Если тесты отработали хорошо, значит у нас всё получилось.

Пища для размышлений содержится в GitHub репозитории "[Graphics Lesson In Gforth](https://github.com/Lecrapouille/GraphicsLessonInGforth)". То, что проект для gForth и Linux не должно особо пугать. Я планирую добавить прямо в pforth слова для работы с графической библиотекой SDL2. Будет что-то вроде [LÖVE](https://love2d.org/) но на форте. Просто потому, что я так хочу. Проблема в том, что пока я не представляю себе, как добавить эти возможности в форт и не умею пользоваться библиотекой SDL. Думаю, стоит начать с определения собственных слов.

Для начала я хочу разобраться со словами для работы с датой и временем. В Форт нет совсем ничего для этих целей. Зато есть стандарные функции С.