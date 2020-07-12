---
title:  "Поиск дубликатов файлов без установки избыточного софта"
date: 2015-01-08 15:18:00 -0000
tags: science
---

Сегодня я решил навести порядок в папках со шрифтами для AutoCAD. Никогда не знаешь, какой очередной редкий шрифт используют проектировщики в своих чертежах, поэтому предпочитаю иметь у себя целую коллекцию шрифтов. Конечно в ней завелось немало дубликатов. Быстрый поиск в интернете показал, что для сравнения файлов есть множество платных и бесплатных программ. Но их нужно как минимум установить, чтобы использовать. А я не люблю засорять компьютер редкоиспользуемым софтом. К счастью, решение проблемы нашлось быстро. Искать дубликаты файлов умеет Ccleaner. На моём компьютере это и так стандартная программа, а если на вашем его ещё нет - рекомендую установить. Продукт бесплатный и редкостно эффективный для очистки компьютерных дисков от всяческого балласта. Это хорошо для быстродействия, да и для SSD жёстких дисков нужно.

Не буду описывать каждый шаг, а просто приведу краткое графическое руководство. Запускаем Ccleaner. Я сразу предпологаю, что он у вас есть.

![Cleaner](http://2nature.me/files/ccleaner.png)

Переходим на вкладку `Tools` и выбираем там инструмент `File finder`. Будем сравнивать шрифты по именам и содержимому. Если искать только по именам - можно упустить ситуацию, когда разные шрифты имеют одно имя. Такое случается. Например, я сталкивался с ситуацией, когда инженеры просто заменяли один из стандартных шрифтов своим с тем же именем. Очень плохая практика, но люди так делают. Отмечаем пункты ||`Name` и `Content`, пункт `Size` отметится автоматически. Я исключил из поиска кое-какие файлы, но этого делать совсем не обязательно. В пункт `Include` включаем кнопкой `Add` те папки, в которых лежат нужные файлы. При этом весь диск `C:\` отмеченный по умолчанию нужно, конечно, отключить. Когда всё готово жмём "Поиск" (`Search`) и ждём результата.

![Cleaner](http://2nature.me/files/ccleaner2.png)

В моём случае дубликатов нашлось более чем достаточно. Нужно долго и нудно отмечать галочками файлы для удаления. В программе нет возможности перенести выбранные файлы в какое-то временное хранилище, так что удаление безвозвратное. Кому-то это может не понравиться, меня такое устраивает.

![Cleaner](http://2nature.me/files/ccleaner2.png)

Теперь все шрифты в одном экземпляре и слиты в один каталог.