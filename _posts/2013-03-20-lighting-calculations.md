---
layout: post
title:  "Расчет количества светильников для проектов"
date: 2013-03-20 21:55:00 -0000
tags: engineering MathJax
---

При разработке перечня мероприятий по охране окружающей среды приходится делать много странных и, с практической точки зрения, противоестественных вещей. Например, оценивать объем разнообразных отходов. Практической пользы в этом сейчас нет, т.к. строительный подрядчик все равно заключает договора на размещение отходов c региональным оператором, а проектная документация уже не может быть основанием для ПНЛООР (как разработчик и того и другого скажу больше, разработчик ПНЛООР проектной документации в 99% случаев в глаза не видит). Обычно цифры берутся полностью "с потолка", т.к. на стадии "проектная документация" никто лампочек не считает, их и в рабочке не считают, как правило. Здесь я лишь сделал попытку хоть как-то привязать цифры количества использованных ламп к здравому смыслу, сделать не нулевое, а первое приближение.

Одним из упрощённых способов расчёта освещённости является метод удельной мощности. Метод рекомендуется для предварительного определения осветительной нагрузки систем внутреннего освещения на начальной стадии проектирования. На стадии разработки ПМООС и ОВОС уже известна площадь помещений. Нормативы освещённости помещений заданы СП 52.13330.2011

Расчётная формула метода:

\\[P_{лр} = \frac{P_{уд} \times S}{N} \\]

Где: 
\\(P_{лр}\\) - расчетная мощность лампы, Вт;

S - площадь помещения, кв.м.;

N - количество светильников в помещении

\\(P_{уд}\\) - удельная мощность общего равномерного освещения, Вт/м2

Значение удельной мощности зависит от типа и светораспределения светильника, размеров помещения, коэффициентов отражения стен, потолка и пола, высоты подвеса светильника и выбирается по справочной литературе. Основные справочные данные приведены в приложении 1.

При отсутствии данных по площади помещения, слишком большом количестве помещений, чтобы выполнить расчёт для каждого считаю допустимым выполнить один общий расчёт для всех помещений, или для всех помещений одинаковой категории.

Пример: Примерный расчёт количества светильников на примере предпроектных данных по одному из горнолыжных курортов.

| 		   			| S 		| \\(P_{уд}\\)	| \\(P_{лр}\\) 	| N 	|
| МФСКД				| 10456 	| 8,5 			| 40			| 2222 	|
| Гаражи			| 5827		| 7				| 40			| 1020	|
| Склады			| 924		| 7				| 40			| 162	|
| Рестораны			| 7140		| 7				| 40			| 1250	|
| Магазины			| 2545		| 7				| 40			| 445	|
| СПА				| 7350		| 8,5			| 40			| 1562	|
| Школа				| 930		| 8,5			| 40			| 198	|
| Гостиницы			| 242401	| 8,5			| 40			| 51510	|
| Офисы				| 41779		| 8,5			| 40			| 8878	|
| Паркинги			| 1024		| 7				| 40			| 179	|
| МЧС и безопасность| 5228		| 8,5			| 40			| 1111	|
| Итого				| 			|				|				|		|

Для освещения принимаются лампы ЛБ40, высота помещений 2-3 м. площадь помещений принимаем равной 25-50 кв.м для МФСКД, офисных помещений, гостиничной инфраструктуры. Площадь помещений ресторанов, магазинов, гаражей, складов, паркингов принимаем 50-150 кв.м., что соответствует данным базового инжиниринга. Значение Pуд подставляем из соответствующей таблицы приложения 1. Расчётная мощность лампы – 40 Вт (так как приняли лампу ЛБ40).

Общий итог – 68537 ламп будет использовано для освещения помещений.

## Приложение 1.


<table>
    <tr>
        <td rowspan="2">Расчётная высота <br />подвеса светильника, h<sub>расч</sub>, м</td>
        <td rowspan="2">Площадь S, м<sup>2</sup></td>
        <td colspan="4">Удельная мощность (Вт/м<sup>2</sup>) для седьмой группы светильников с лампами типов &rho;<sub>п</sub>) = 70%; &rho;<sub>c</sub> = 50%; &rho;<sub>рнсч</sub> = 10%; K<sub>зап</sub> = 1,5; z = 1,1)</td>
    </tr>
    <tr>
        <td>ЛБ40, 65</td>
        <td>ЛД40, ЛБ80,<br />ЛХБ40, 65<br />ЛТ 40, 65</td>
        <td>ЛХБ80, ЛТБ80, ЛД65, ЛДЦ40</td>
        <td>ЛД80, ЛДЦ65, ЛДЦ80</td>
    </tr>
    <tr>
        <td rowspan="6">2-3</td>
        <td>10-15</td>
        <td>10,1</td>
        <td>11,6</td>
        <td>13,2</td>
        <td>15,5</td>
    </tr>
    <tr>
        <td>15-25</td>
        <td>8,5</td>
        <td>9,6</td>
        <td>10,8</td>
        <td>12,9</td>
    </tr>
    <tr>
        <td>25-50</td>
        <td>7</td>
        <td>8</td>
        <td>9,1</td>
        <td>10,4</td>
    </tr>
    <tr>
        <td>50-150</td>
        <td>5,7</td>
        <td>6,7</td>
        <td>7,7</td>
        <td>8,8</td>
    </tr>
    <tr>
        <td>150-300</td>
        <td>5,1</td>
        <td>6</td>
        <td>6,7</td>
        <td>7,8</td>
    </tr>
    <tr>
        <td>&gt; 300</td>
        <td>4,5</td>
        <td>5,4</td>
        <td>6,3</td>
        <td>7,2</td>
    </tr>
	    <tr>
        <td rowspan="7">3-4</td>
        <td>10-15</td>
        <td>14,4</td>
        <td>17,6</td>
        <td>19</td>
        <td>23</td>
    </tr>
    <tr>
        <td>15-20</td>
        <td>11,4</td>
        <td>13,4</td>
        <td>15</td>
        <td>17,6</td>
    </tr>
    <tr>
        <td>20-30</td>
        <td>9,9</td>
        <td>11,4</td>
        <td>12,9</td>
        <td>15</td>
    </tr>
    <tr>
        <td>30-50</td>
        <td>8,3</td>
        <td>9,6</td>
        <td>10,8</td>
        <td>12,7</td>
    </tr>
    <tr>
        <td>50-120</td>
        <td>6,8</td>
        <td>7,8</td>
        <td>8,9</td>
        <td>10,2</td>
    </tr>
    <tr>
        <td>120-300</td>
        <td>5,6</td>
        <td>6,6</td>
        <td>7,6</td>
        <td>8,7</td>
    </tr>
    <tr>
        <td>&gt;300</td>
        <td>4,5</td>
        <td>5,4</td>
        <td>6,3</td>
        <td>7,2</td>
    </tr>
</table>
