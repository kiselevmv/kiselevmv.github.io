---
layout: post
title:  "Политик с яйцами или захват RealVideo в линукс"
date: 2005-11-09 05:26:00 -0000
tags: blog Linux
description: "Отличный пример того, как всё меняется за 15 лет. Про формат RealVideo никто уже и не вспомнит, всё заменил Youtube. Моё отношение к политикам, которых вызвали для дачи объяснений, а они нападают поменялось кардинально. Я бы подозервал, что у него может быть рыльце в пуху."
---

[George Galloway - SourceWatch](http://www.sourcewatch.org/index.php?title=George_Galloway)

Захотелось мне скачать [запись речи](rtsp://video.webcastcenter.com/srs_g2/govtaff051705.rm) Джорджа Геллоувэя на слушаниях о злоупотреблениях в ходе программы "нефть в обмен на продовольствие" (кстати, наши политики там ещё как отметились, просто на слушания никто не рискнул явиться). Экспрессивная очень речь, с таким пафосом, чувак не оправдываться приехал, а обвинять.

Так вот, запись в формате RealVideo. Казалось бы чего плохого, проигрыватель RealVideo в линукс [есть](http://www.real.com/), открывай URI и проигрывай, однако я хочу иметь запись на своём винте. Под винду для скачивания роликов RealVideo есть специализированные программы в линукс для этого есть свой путь, как обычно оригинальный и простой. Для захвата RealVideo можно использовать одну из самых "острых" мультимедиа-утилит [MPlayer](http://www.mplayerhq.hu/). Комманда для этого очень простая -  `mplayer -dumpstream rtsp|mms://somehost.com/somedirectory/somefile.rm|ra|asf|wmv; mv stream.dump somefile.rm|ra|asf|wmv`. Вуля-ля, файл на диске, спасибо за совет [all-streaming-media](http://all-streaming-media.com/record-video-stream/record-streaming-video-windows-media-and-real-video.htm).