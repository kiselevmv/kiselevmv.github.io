---
layout: post
title:  "Настройка MathJax на GitHub Pages"
date: 2020-07-01 19:02:00 -0000
tags: hosting blogging
---

По началу казалось, что [MathJax](https://www.mathjax.org/) будет работать на GitHub Pages "из коробки". Такое впечатление создалось у меня из-за раздела [Configuring Jekyll in your GitHub Pages site](https://help.github.com/en/github/working-with-github-pages/about-github-pages-and-jekyll#configuring-jekyll-in-your-github-pages-site) в руководстве по GitHub Pages. Руководство обещает, что некоторые настройки движка Jekyll нельзя изменить на GitHub Pages. И одна из настроек - как раз 'math_engine: mathjax'. Но рано было радоваться, на первой же странице с разметкой MathJax вся разметка "поплыла", ни одна формула не отобразилась. Пришлось читать документацию.

За перевод разметки Markdown в html страницы, отображаемые броузером, отвечает движок kramdown. [Раздел](https://kramdown.gettalong.org/math_engine/mathjax.html) посвящённый движку MathJax на сайте с документацией kramdown поясняет, что MathJax поддерживается, но сам движок не подключает библиотеки MathJax, за это отвечает пользователь. Уже что-то, осталось как-то подключить библиотеки. Это тоже оказалось непростым.

Как я понимаю, на GitHub Pages можно использовать несколько тем оформления. С этим ещё предстоит разобраться. В шаблоне для [заголовка страницы](https://github.com/jekyll/minima/blob/master/_includes/head.html) темы оформления находится символическая ссылка `{\%- include custom-head.html -%\}`. Т.е. если разместить в каталоге `_inclides` файл `custom-head.html` с кодом для включения MathJax всё должно заработать. Разместил в `_includes` файл `custom-head.html` с содержимым для включения MathJax

    <script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
    <script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
	
Но этот трюк не сработал. У меня есть предположения почему, но это не важно. К счастью работает механизм включений ([includes](https://jekyllrb.com/docs/includes/)). То есть можно вставлять код путём включения фрагментов вида `{\% include something.html %\}` прямо в markdown разметку. Справка [Linking your copy of MathJax into a web page](https://docs.mathjax.org/en/v2.7-latest/start.html#linking-your-copy-of-mathjax-into-a-web-page) сообщает, что подключать MathJax нужно в `<head>`. Но [другой раздел](https://docs.mathjax.org/en/v2.7-latest/start.html#using-a-content-delivery-network-cdn) указывает, что по необходимости можно и в `<body>`. Решил сделать быстро и грязно и указал включение `custom-head.html` прямо в заголовке документа. Работает. Но не так, как хотелось бы.

Kramdown "съедает" в последовательности из обратной наклонной черты и скобки символы \\. Документация по синтаксиcу karmdown явно советует в таких случаях экранировать символы. Пришлось переделать формулы на две обратные наклонные черты и скобка. Теперь работает. Из чего я могу сделать вывод, что на самом деле опция 'math_engine: mathjax' для karmdown не задана. Получается как обычно в IT, сплошные костыли, но работает.

P.S. Похоже, опция 'math_engine: mathjax' работает, но она устарела. Движок kramdown окружает текст с двумя \$\$ тегом `<script type="math/tex">`. Одна беда, это было нужно во времена MathJax версий 1.0 - 2.7. А сейчас уже третья версия работает. Есть возможность вернуть старое поведение, оно описано в разделе [Changes in the MathJax API](http://docs.mathjax.org/en/latest/upgrading/v2.html#changes-in-the-mathjax-api), см. последний пункт списка. Но это легко может привести к проблемам, когда API MathJax опять поменяется. Поэтому - костыли.

P.P.S. Решил проблему не вполне изящно, но работающим способом. Страницам с формулами присваиваю тег 'MathJax'. В окружение `<head>` файла шаблона страницы добавил фрагмент:

    {\% if page.tags contains "MathJax" %\}
	{\%- include mathjax-head.html -%\}
	{\% endif %\}
	
То есть, в любую страницу, где есть тег `MathJax` в `<head>` подключаются скрипты MathJax. Тег получился чисто служебный, но не лишний. Позволяет просмотреть по тегу все страницы, где есть формулы.

Обратите внимание, обратная косая черта между фигурной скобкой и знаком процентов - лишняя. Просто я ещё не нашёл способа заэкранировать операцию `include`, чтобе Jekyll её не попытался выполнить.