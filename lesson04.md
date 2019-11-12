# Лекция 4

## 1. Псевдоклассы

Взаимодействия пользователя с элементами веб-страницы отслеживаются браузером. Если говорить о ссылках, им присваивается определенный статус в зависимости от того, какое действие было совершено (наведение, нажатие, переход по ссылке и т. д.). Это мы и называем состояниями ссылок.

Псевдоклассы — это классы, фактически не прикрепленные к HTML-тегам. Они позволяют применить CSS-правила к элементам при совершении события или подчиняющимся определенному правилу. Примеры псевдоклассов:

*   **:link** — не посещенная ссылка;
*   **:visited** — посещенная ссылка;
*   **:hover** — любой элемент, по которому проводят курсором мыши;
*   **:focus** — интерактивный элемент, к которому перешли с помощью клавиатуры или активировали посредством мыши;
*   **:disabled** — заблокированные поля форм, т.е., находящиеся в неактивном состоянии;
*   **:not(селектор)** — элементы, которые не содержат указанный селектор — класс, идентификатор, название или тип поля формы — :not([type="submit"]);
*   **:checked** — выделенные (выбранные пользователем) элементы формы.

Например (!!! обязательно размещайте их в следующей последовательности):

```
CSS:
    a:link { color: red; }  /* обычный цвет ссылки */
    a:visited { color: grey; }  /* цвет ссылки, которую пользователь уже посещал */
    a:hover { color: blue; }  /* цвет ссылки, на которую наведен курсор */
    a:active { background-color: yellow; }  /* цвет фона ссылки в момент нажатия на нее */

```

## 2. Структурные псевдоклассы

В CSS3 существует ряд псевдоклассов для работы с дочерними элементами. Ниже приведено описание каждого из них, примеры использования, а также отличия между псевдоклассами вида «child» и «of-type».

*   ** :nth-child(odd)** — нечётные дочерние элементы;
*   **:nth-child(even)** — чётные дочерние элементы;
*   **:nth-child(3n)** — каждый третий элемент среди дочерних;
*   **:nth-child(n+2)** — выбирает все элементы, начиная со второго;
*   **:nth-child(-n+2)** - первые 2
*   **:nth-child(3)** — выбирает третий дочерний элемент;
*   **:first-child** — позволяет оформить только самый первый дочерний элемент тега;
*   **:last-child** — позволяет форматировать последний дочерний элемент тега;
*   **:only-child** — выбирает элемент, являющийся единственным дочерним элементом;
*   **:empty** — выбирает элементы, у которых нет дочерних элементов;

Почитать можно и [тут](https://code.tutsplus.com/ru/tutorials/the-30-css-selectors-you-must-memorize--net-16048)

Потренироваться в использовании можно [тут](https://css-tricks.com/examples/nth-child-tester/) 

## 3. Структурные псевдоэлементы

Если псевдоклассы записываются с одним двоеточием, то псевдоэлементы – с двумя. Это было внедрено в CSS3 для того, чтобы различать псевдоклассы и псевдоэлементы между собой. Однако раньше этой разницы не существовало и с псевдоэлементами использовалось одно двоеточие. Сейчас браузеры поддерживают оба варианта написания (но не для всех случаев). Рассмотрим некоторые псевдоэлементы:

*   **::after** – используется вместе со свойством **content** и позволяет вывести необходимые данные после содержимого элемента;
*   **::before** – выполняет похожую функцию, что и предыдущий, только выводит данные _перед_ содержимым элемента;
*   **::selection** – этот псевдоэлемент распознается браузерами только при использовании двух двоеточий и позволяет установить цвет и фон для текста, который выделен пользователем;
*   **::first-letter** – используется для изменения стиля первого символа в тексте элемента;
*   **::first-line** – используется для изменения стиля первой строки текста элемента.


Например:

```
HTML: 
    <p>При выделении этого текста он изменит свой цвет.</p>

CSS:
    p::selection {
        color: #ff0; /* Цвет текста */
        background: #000; /* Цвет фона */
    }
    
    p::first-letter {
        font-family: "Times New Roman", Times, serif; /* Гарнитура шрифта первой буквы */
        font-size: 20px; /* Размер шрифта первого символа */
        color: red; /* Красный цвет текста */
    }
```

---

Остановимся подробнее на **::after** и  **::before**.  Псэвдоелементы :before и :after предельно просто прописываются в css-коде. Вот простой пример использования:


```
CSS:
    #example::before {
       content: "#";
    }
    #example::after {
       content: ".";
    }
```


:heavy_exclamation_mark: Здесь важно отметить две вещи:

*   **Во первых**, мы указываем на реальный html элемент с помощью строк #example::before и #example::after. Приставки после двоеточия, означают, что это стиль не просто элемента, а его псевдоэлементов.
*   **Во-вторых**, вы не сможете ничего добавить без свойства **content**, которое указывает, что именно должно отображаться как псевдоэлемент.

Вы можете оставить свойство **content** пустым, и создать блок.


```
CSS:
    #example:before {
       content: "";
       display: block;
       width: 100px;
       height: 100px;
    }
```


Если вы удалите свойство content, псевдоэлемент работать не будет. По крайней мере, это совойство должно оставаться пустым. 

Если прописать `normal`, `none` — содержимое псевдоэлемента не отображается. (полезно, если нужно скрыть ранее заданный псевдоэлемент)

Контент, который вставляется невидим на html странице. Он видим только в CSS.

Также, вставляемый контент, по умолчанию будет строчным элементом. Чтобы сделать его блочным достаточно указать **display:block;**, указать ширину и высоту блока. Это очень удобно при создании вкладок, кнопок и т.д.

Важно заметить, что псевдоэлементы не наследуют стилей от родительских элементов (такие как внутренний и внешний отступы). Поэтому для каждого псевдоэлемента, необходимо указывать свои параметры стилей.

### Возможности псевдоэлеметов `::after` и  `::before`
Что же мы можем вставить с помощью этих псевдоэлементов?

:rocket: 1. **Символы и текст**. Рассмотрим пример: давайте добавим кавычки в начало и конец текста тега  **<blockquote>:**

![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-401.jpg)

```
CSS:
    blockquote::before {
    	content: """;
    }
    
    blockquote::after {
        	content: """;
    }
    
    blockquote::selection {
    	color: #c8f7c5;
    	background-color: #f9f0de;
    }
```

Мы написали стиль для  длинных цитат, который добавляет кавычки в начале и в конце содержимого тега **<blockquote>**, а также изменяет цвет и фон выделенного пользователем текста цитаты.

Можем вместо кавычек вставить [символы юникода](http://yoksel.github.io/unicode-table/):


```
CSS:
    blockquote::before {
    	content: "\2728";
    }

```

или текст:
```
CSS:
    blockquote::before {
        content: "Цитата:";
        color: red;
    }

```


:rocket: 2. **Изображения в качестве фона**. Давайте перед каждым пунктом списка сделаем вместо “точек”, например, цветочки: 

![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-404.jpg)"float: right; margin-top: 20px;"
```
HTML:
    <ul>
      <li>Item 1</li>
      <li>Item 2</li>
      <li>Item 3</li>
      <li>Item 4</li>
      <li>Item 5</li>
    </ul>

CSS:
    li {
      list-style: none;
    }
    
    li:before {
        background-image: url('http://image.flaticon.com/icons/png/512/253/253551.png');
        background-size: 20px 20px;
        background-repeat: no-repeat;
        background-position: 50% 50%;
        display: inline-block;
        width: 25px; 
        height: 20px;
        content:"";
    }
```

:rocket: 3. **Картинку**. Для этого в свойстве _content_ вы можете прописать URL картинки( как это делается в background). Важно помнить, что нельзя URL брать в кавычки, это будет значить что контент является текстом.

```
HTML:
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Perspiciatis, odit?</p>

CSS:
    p:before {
      content: url(https://i.gifer.com/PUM3.gif);
    }

```

:rocket: 4. **Cчетчик** - `<counter>`. С помощью этого значения можно пронумеровать не только списки, но и любые элементы на странице. Например, разделы статьи.

```
CSS:
    body {
        counter-reset: h2-counter;
        counter-reset: p-counter;
    }
    div{
        counter-increment: h2-counter;
    }
    
    h2:before {
        content: counter(h2-counter) ". ";
    }
    
    p:before {
        content: counter(p-counter) ". ";
        counter-increment: p-counter;
    }

```

:rocket: 5. **Содержимое заданного атрибута** - `attr(<identifier>`). Удобно использовать для вывода атрибутов `href` в версии для печати и для разных интересных эффектов.


```
HTML:
    <p>I'm text. <a href="#" title="I'm link">I'm link</a></p>

CSS:
    a {
      position: relative;
    }
    
    a:before {
        content: attr(title);
        position: absolute;
        z-index: 10;
        right: 0;
        top: 0;
        left: 0;
        height: 0;
        overflow: hidden;
        background: red;
        color: #FFF;
        transition: all .3s;
    }
    
    a:hover:before {
        height: 100%;
    }
```

Мы видим, что возможности использования псевдоэлементов достаточно обширны. Нужно лишь знать где их и как применить))

## 4. Единицы измерения в CSS

![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-402.jpg)"width: 400px;"

Существует много свойств CSS, которые требуют **размер в качестве единицы**:

*   **_font-size_** определяет размер текста;
*   **_border-width_** определяет толщину границ элементов;
*   **_margin_** определяет пространство между элементами;
*   **_left/right/top/bottom_** позволяют позиционировать и перемещать элементы.

---

:pushpin: **Наиболее часто используемые единицы**:

*   px для пикселей;
*   % для процентов;
*   em для определения размера относительно родительского значения font-size.


### Пиксели (px)
Поскольку компьютерные экраны используют пиксели для отображения содержимого, это **самая распространённая единица размера в CSS**.

Пиксель может быть использован для задания фиксированной **ширины** элемента:

```
CSS:
    body { width: 400px; }
```
Или установить **размер текста**:
```
CSS:
    body { font-size: 20px; }
```
Пиксели в CSS являются простыми, поскольку они определяют **абсолютные значения** и не зависят от других наследуемых свойств CSS.

Они также широко используются для **позиционирования** и **расстояния**.


### Проценты (%)

Проценты — это **относительные единицы**: они полагаются на родителя и/или предка элемента.

К примеру, блочные элементы, такие как абзацы, естественным образом занимают **всю доступную ширину**. Следующее правило CSS изменит их размер до **половины** доступной ширины.
```
CSS:
    p { width: 50%; }
```
Проценты могут помочь задать другие свойства CSS, такие как размер текста.
```
HTML:
    <p>Есть <strong>важные</strong> проблемы, стоящие перед нами.</p>

CSS:
    strong { font-size: 150%; }

```

### em

**em** является относительной единицей и **_зависит от значения font-size элемента_**.

Например, если у родителя font-size задан как 20px и вы применяете font-size: 0.8em к дочернему элементу, то этот дочерний элемент будет отображать font-size как 16px.

:heavy_exclamation_mark: Не следует путать размер em с селектором em, который ориентирован на элемент `<em>`.

Единица em интересна для определения размера шрифта элементов HTML относительно друг друга. Для создания привлекательной и комфортной для чтения веб-страницы вам необходимо обеспечить визуальную глубину. Например, вы хотите, чтобы ваши `<h1>` были вдвое больше, чем основной текст, ваши `<h2>` в 1,5 раза больше, а боковая панель немного меньше. Это можно легко получить в CSS:
```
CSS:
    body { font-size: 16px; }

    h1 { font-size: 2em; }        /* = 32px */

    h2 { font-size: 1.5em; }      /* = 24px */

    aside { font-size: 0.75em; }  /* = 12px */
```
Если вы решите изменить размер текста `<body>`, относительные размеры заголовков и боковой панели **изменятся соответственно** и ваша веб-страница останется **визуально сбалансированной**.

Только изменив одно значение, поменяются и все остальные значения:
```
CSS:
    body { font-size: 20px; }
    
    h1 { font-size: 2em; }        /* = 40px */
    
    h2 { font-size: 1.5em; }      /* = 30px */
    
    aside { font-size: 0.75em; }  /* = 15px */
```

### rem

Единица **rem** похожа на em, но вместо зависимости от родительского значения, она **опирается на значение корневого элемента**, которым является элемент `<html>`.
```
CSS:
    html { font-size: 18px; }
    
    body { font-size: 1rem; }     /* = 18px */
    
    h1 { font-size: 2rem; }       /* = 36px */
    
    h2 { font-size: 1.5rem; }     /* = 27px */
```
:point_up: Разница между rem и em в том, что значение rem фиксировано, в то время как значения em умножаются друг с другом.

```
Если вы установили html { font-size: 18px; }:

*   2rem всегда будет равно 36px, независимо от того, где оно используется в вашем CSS;
*   2em всегда будет равно удвоенному font-size родителя, что не обязательно равно 36px.
```
Быстрый пример, где 2em отличается от 2rem:
```
HTML:
    <p>Есть <strong>важные</strong> проблемы, <span>стоящие</span> перед нами.</p>

CSS:
    html { font-size: 20px; }
    
    p { font-size: 0.8rem; }        /* = 16px */
    
    p span { font-size: 2em; }      /* = 16px * 2 = 32px */
    
    p strong { font-size: 2rem; }   /* = 20px * 2 = 40px */
```

![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-403.jpg)


`<span>` полагается на значение font-size у `<р>`, в то время как `<strong>` полагается на значение font-size у `<html>`.

Если  размер в em/rem изменить, задав его больше единицы,  то шрифт увеличится. Если его задать меньше единицы, то шрифт уменьшится. Т.е. цифра рядом с единицей em является множителем для размера шрифта.


### Какую единицу использовать?

Наверное, лучше всего все-таки начать с **пикселей**: поскольку это абсолютная величина, они не зависят от контекста элемента. Пиксели простые, позволяют установить размер текста, ширину и высоту изображения, толщину границы, координаты положения и др.

**Проценты** и значения **em** могут быть использованы наряду с пикселями, особенно для относительных размеров текста.

@@@ (json)
[
    ["Единица измерения", "Описание", "Пример использования единицы измерени"],
    ["%", "Устанавливает измерение в процентах относительно другого значения, как правило, охватывающего элемента.", "div {width: 50%;}"],
    ["em", "Относительное измерение высоты шрифта в em пространстве. Поскольку единица em эквивалентна размеру данного шрифта, то, если Вы укажите шрифт 12pх, каждый элемент «em» будет 12pх. Таким образом, 2em будет 24pх.", "h1 {letter-spacing: 3em;}"],
    ["px", "Устанавливает измерение в пикселях экрана.", "p {margin: 30px;}"],
    ["vh", "Равен 1% высоты окна просмотра.", "h1 {font-size: 2.1vh;}"],
    ["vw", "Равен 1% ширины окна просмотра.", "h2 {font-size: 2.2vw;}"],
    ["vmin/vmax", "Равен 1vw или 1vh, в зависимости от того, что меньше.", "div {font-size: 5vmin;}"]
]
@@@

## Комментарии в CSS

Комментарии используются для добавления поясняющих заметок или для того, чтобы предотвратить интеграцию части кода в браузер.

Синтаксис коментирования CSS следующий:

```
/* Однострочный комментарий */ 


/* Комментарий 
который содержит 
несколько строк */
```