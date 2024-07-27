<div align='left'>
    <img src='assets/informal.svg'>
    <img src='assets/easy.svg'>
</div>

<div align='right'>
    <q><i>Success has many fathers</i></q>
    <br>
    <sub>~ First ECMA JS meeting, 1996</sub>

📜[^1]

</div>

# Глава 2: Введение

В этой главе хотелось бы поговорить о происхождении
[ECMAScript Language Specification](https://tc39.es/ecma262/multipage/) и
[JavaScript](https://en.wikipedia.org/wiki/JavaScript). <br><br> Давайте начнём с основных
определений, которые каждый сможет найти на просторах интернета. Определим для себя термины в
контексте нашего повествования, чтобы отталкиваться от них в будущем. Итак, если обращаться к
определению термина "_спецификация_", мы увидим следующее:

> **_A specification_** often refers to a set of **_documented requirements_** to be satisfied by a
> material, design, product, or service. A specification is often a type of **_technical
> standard_**.
>
> ~ [wiki](<https://en.wikipedia.org/wiki/Specification_(technical_standard)>)

Далее давайте взглянем на определение термина "_ECMAScript_":

> ECMAScript is an object-oriented programming language for performing computations and manipulating
> computational objects within a host environment.  
>  ~ [tc39](https://tc39.es/ecma262/multipage/overview.html#sec-overview)

То есть ECMAScript — это объектно-ориентированный язык программирования для выполнения вычислений и
управления вычислительными объектами в хост-среде. Для того, чтобы контролировать работу и
возможности этого языка в 1996-1997 годах была реализована
[первая версия спецификации](https://web.archive.org/web/19981203070212/http://cgi.netscape.com/newsref/pr/newsrelease289.html),
где были описаны его основополагающие механизмы работы и определения всех внутриязыковых терминов.
Современная же спецификация получила множество новых версий, которые дополнили и исправили язык, а
где-то и испортили его вовсе. На тему плюсов и минусов нововведений на протяжении всей эволюции
языка будет написана отдельная глава.

Итак, мы знаем, что существует какой-то язык программирования под названием ECMAScript; знаем, что у
него есть вполне большая история эволюции вплоть до сегодняшних дней. Но как же тут задействован
язык JavaScript, и почему разработчикам, использующим его, в целях увеличения культуры разработки и
производительности своего кода желательно знать ECMAScript? Ответ находится на поверхности.

## Сквозь призму времени...

Когда-то немалоизвестный [Брендан Эйх](https://en.wikipedia.org/wiki/Brendan_Eich), работающий в
небольшой команде в компании
[Netscape Communications Corporation](https://en.wikipedia.org/wiki/Netscape) вместе с двумя
коллегами, которых звали [Марк Андриссен](https://en.wikipedia.org/wiki/Marc_Andreessen) и
[Билл Джой](https://en.wikipedia.org/wiki/Bill_Joy),
[за 10 дней](https://brendaneich.com/2011/06/new-javascript-engine-module-owner/#:~:text=know%2C%20I%20wrote-,JavaScript%20in%20ten%20days.,-JS%20was%20born)
создал язык программирования под названием _Mocha_ (будущий JavaScript) для существовавшего на тот
момент браузера [Netscape Navigator](https://en.wikipedia.org/wiki/Netscape_Navigator). Эта
инициатива была направлена на помощь одинокому и дерзкому языку гипертекстовой разметки -
[HTML](https://en.wikipedia.org/wiki/HTML) - динамично реализовать интерфейс веб-страниц в браузере.
Также Mocha поневоле стал
[вечным младшим братом](https://brendaneich.com/2011/06/new-javascript-engine-module-owner/#:~:text=JS%20was%20born-,under%20the%20shadow%20of%20Java,-%2C%20and%20in%20spite)
мастодонта тех времён - языка [Java](<https://en.wikipedia.org/wiki/Java_(programming_language)>);
не путать Java и JavaScript. Для понимания причин "**_лёгкости_**" современного языка JavaScript
очень важно дифференциировать языки Java и Mocha в тот момент времени, когда младший брат только
родился. Mocha был призван "на коленке" создавать простенькие скрипты для страничек в интернете, в
то время как Java был громоздким в сравнении с Mocha языком для тяжёлых задач веб-индустрии того
времени. Конструкция языка Mocha была пронизана **_понятными и открытыми принципами_** его
реализации. Людям не нужен был сложный язык для "оживления" веб страниц; **_лёгкость и
примитивность_** стали во главе Mocha. Вскоре язык был переименован в **_LiveScript_** и в этом же
году после закрытия сделки между [Sun Microsystems](https://en.wikipedia.org/wiki/Sun_Microsystems)
и Netscape Communications Corporation язык получил третье и последнее название - **_JavaScript_**.

<details>
<summary><i>Интересный факт</i></summary>
<br>

> Одновременно с приобретением языка JavaScript своего культового названия Брендан Эйх разработал
> известный и по сей день движок для выполнения кода в браузере Netscape Navigator. Он получил
> название [SpiderMonkey](https://en.wikipedia.org/wiki/SpiderMonkey). Сейчас успешно используется в
> браузере [Firefox](https://en.wikipedia.org/wiki/Firefox).

</details>

Неожиданный успех в веб-индустрии, продиктованный простотой и лёгкостью использования языка
JavaScript, породил "клонов" по типу [JScript](https://en.wikipedia.org/wiki/JScript) от
[Microsoft](https://en.wikipedia.org/wiki/Microsoft), который использовался в браузере
[Internet Explorer](https://en.wikipedia.org/wiki/Internet_Explorer). Их реализации рабочего
функционала могли быть изменены относительно основного курса развития JavaScript. Так что для
стандартизирования языка и для установки требований к его внутренней "машинерии" спустя некоторое
время после
[первой встречи](<https://ecma-international.org/news/ecma-262-the-ecmascript-javascript-the-most-popular-web-scripting-standard-is-celebrating-its-20th-birthday/#:~:text=documents%20from%201997.-,The%20work%20on%20ECMAScript%20has%20started%20in%20November%201996%20(see%20the%20the%20minutes%20of%20the%201st%20TC39%20meeting),-.%20There%20was%20a>)
в ноябре 1996 года, в 1997 году
[была опубликована](https://web.archive.org/web/19981203070212/http://cgi.netscape.com/newsref/pr/newsrelease289.html)
спецификация ассоциации
<abbr title='Ранее - European Computer Manufacturers Association'>ECMA</abbr> в качестве стандарта
[ECMA-262](https://ecma-international.org/publications-and-standards/standards/ecma-262/) под
названием ECMAScript Language Specification, написанная за 7 месяцев.

В данный момент у любого человека обязательно появится вполне логичный вопрос: а почему же
спецификацию не назвали в честь языка? **_Бюрократия_**. Ранее торговая марка "_JavaScript_" с
разрешения компании Sun Microsystems использовала префикс "_Java_", но впоследствии другая известная
компания [Oracle Corporation](https://en.wikipedia.org/wiki/Oracle_Corporation)
[поглотила](https://web.archive.org/web/20100821093146/http://news.cnet.com/8301-30685_3-20000019-264.html)
убыточную Sun. Нежелание первой сделать торговую марку общественным достоянием склонило комитет
<abbr title='Ecma Technical Committee 39'>TC39</abbr> к решению, чтобы для спецификации было
установлено название _ECMAScript_.

<details>
<summary><i>Интересный факт</i></summary>
<br>

> Европейская ассоциация ECMA разрабатывает разные спецификации и по сей день не только для
> программирования, но и для разных других сфер в области коммуникаций. Например, там можно найти
> _спецификацию языка программирования C#_
> ([ECMA-334](https://ecma-international.org/publications-and-standards/standards/ecma-334/)),
> _спецификацию синтаксиса JSON_
> ([ECMA-404](https://ecma-international.org/publications-and-standards/standards/ecma-404/)) и
> другие.

</details>

И с тех самых пор печально известный JavaScript развивался согласно спецификации ECMAScript Language
Specification. Он испытывал много взлётов и падений на протяжении долгих лет, а появление на свет
грандиозной виртуальной машины [V8](<https://en.wikipedia.org/wiki/V8_(JavaScript_engine)>) для
[Goggle Chrome](https://en.wikipedia.org/wiki/Google_Chrome) снова перевернуло всю веб-индустрию и
дало языку JavaScript золотой билет в счастливое будущее.

<details>
<summary><i>Интересный факт</i></summary>
<br>

> В 2008 году даже был выпущен [веб-комикс](https://blogoscoped.com/google-chrome/) на тему "_Google
> on Google Chrome - comic book_".

</details>

## А что же сегодня?

В наши дни язык JavaScript всё так же реализует принципы, заложенные в спецификации ECMAScript. Это
скриптовый, мультипарадигменный язык высоких, даже слишком высоких абстракций, что подтверждает
большинство внутренних алгоритмов языка, где одна операция может рекурсивно вызывать множество
вложенных неочевидных абстрактных операций (сущностей спецификации). Чтобы начать разбираться, как
утроен язык JavaScript "_под капотом_", важно уметь различать, где есть JavaScript, а где —
JavaScript host environment; где есть тип языка ECMAScript, а где — тип спецификации ECMAScript; где
символы "**!**" или "**?**" учавствуют, как токены языка ECMAScript, а где — как сокращение для
более "удобного" описания алгоритмов спецификации ECMAScript. То есть для начала необходимо понять,
как спецификация написана.

Одним словом, для качественного и полноценного понимания языка нужно дифференциировать спецификацию
языка ECMAScript и язык спецификации ECMAScript (это две переплетающиеся модели повествования
официального стандарта ECMA-262). Этому посвящена [следующая глава](/get-started/index.md).

**_Вот такой JavaScript "лёгкий" язык._**

~ [Глава 1: Методология исследования](Methodology.md) > Глава 2: Введение >
[Глава 3.0: "Начало" языка](/get-started/index.md)

[^1]:
    Название темы первой встречи в ECMA в рамках стандартизации JavaScript в составе только что
    присоединившегося к ECMA Брендана Эйха, представителей Microsoft и других.
