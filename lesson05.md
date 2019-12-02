# Lesson 5
## 1. Текст. Стили для форматирования текста.

Свойства CSS для форматирования текста позволяют оформить содержимое страницы, не затрагивая HTML-код. В этом уроке узнаем, какие же параметры можно задать тексту через таблицу стилей

### `text-transform`

Свойство **_text-transform_** стилизует текст. Оно не влияет на базовое содержимое и не должно влиять на содержимое операции копирования и вставки простого текста.

Свойство наследуется.

@@@ (json)
[
    ["property", "comment"],
    ["**none**", "Значение по умолчанию, означает отсутствие эффектов."],
    ["**capitalize**", "Изменяет написание первой буквы каждого слова в элементе, делая её прописной."],
    ["**uppercase**", " Выводит все слова в элементе прописными буквами."],
    ["**lowercase**", "Выводит все слова в элементе строчными буквами."],
    ["**initial**", "Устанавливает значение свойства в значение по умолчанию."],
    ["**inherit**", "Наследует значение свойства от родительского элемента."]
]
@@@

**Синтаксис**

```
    text-transform: none/capitalize/uppercase/lowercase/inherit/initial;
```

### `text-indent`

Свойство **text-indent** позволяет задать отступ(пустое место) первой строки текста. Например, так можно отформатировать абзацы, чтобы лучше визуально отделить их друг от друга. В качестве значения используется цифра, задающая длину в процентах, единицах или пикселях. Отрицательное число превратит отступ в выступ.

**Синтаксис:** 
```
    text-indent: 20px/15%/inherit
```

### `white-space`

Свойство white-space обрабатывает пробелы между словами и переносы строк внутри элемента. Свойство наследуется.

@@@ (json)
[
    ["property", "comment"],
    ["**normal**", "Значение по умолчанию. Между словами вставляется только по одному пробелу, дополнительные пробелы отбрасываются. Текст переносится только в случае необходимости."],
    ["**nowrap**", "Запрещает переносы строк, за исключением применения `<br>`."],
    ["**pre**", "Пробелы в тексте не игнорируются, браузер отображает дополнительные пробелы и переносы строк."],
    ["**pre-wrap**", "Сохраняет пробелы в тексте, делая разрывы строк там, где это необходимо."],
    ["**pre-line**", "Удаляет лишние пробелы, за исключением случаев `<br>`."],
    ["**break-spaces**", "Поведение идентично pre-wrap, за исключением того, что: любая последовательность неудаляемых пробелов всегда занимает место, в том числе в конце строки; возможность переноса строки существует после каждого неудаляемого пробела, в том числе между пробелами."],
    ["**initial**", "Устанавливает значение свойства в значение по умолчанию.."],
    ["**inherit**", "Наследует значение свойства от родительского элемента."]
]
@@@

**Синтаксис**
```
    white-space: normal/nowrap/pre/pre-wrap/pre-line/break-spaces/inherit/initial;
```

### `word-break`

Свойство **_word-break_** указывает, как делать перенос строк внутри слов, которые не помещаются по ширине в заданную область. Свойство наследуется.

@@@ (json)
[
    ["property", "comment"],
    ["**normal**", "Разрыв допускается в пределах слов. Перенос слов не применяется."],
    ["**break-all**", "Разрыв допускается в пределах слов. Перенос слов не применяется."],
    ["**keep-all**", "Запрещает разрывы между парами символов."],
    ["**initial**", "Устанавливает значение свойства в значение по умолчанию."],
    ["**inherit**", "Наследует значение свойства от родительского элемента."]
]
@@@


**Синтаксис**

```
    word-break: normal/break-all/keep-all/inherit/initial;
```

### `word-wrap`

Свойство **_word-wrap_** указывает, переносить или нет длинные слова, которые не помещаются по ширине в заданную область. Свойство наследуется.

**Синтаксис**

```
    word-wrap: normal | break-word
```

@@@ (json)
[
    ["property", "comment"],
    ["**normal**", "Строки не переносятся или переносятся в тех местах, где явно задан перенос (например, с помощью `<br>`)."],
    ["**break-word**", "Перенос строк добавляется автоматически, чтобы слово поместилось в заданную ширину блока."]
]
@@@



Пример:

```
HTML:

    <div class="col">
       <p>Cуществительное</p>
       <p>высокопревосходительство</p>
       <p>Одушевленное существительное</p>
       <p>одиннадцатиклассница</p>
       <p>Химическое вещество</p>
       <p>метоксихлордиэтиламинометилбутиламиноакридин</p>
      </div>

CSS:
    .col { 
        background: #f0f0f0; /* Цвет фона */
        width: 230px; /* Ширина блока */
        padding: 10px; /* Поля */
        font-size: 1.5em; /* Размер шрифта */
        word-wrap: break-word; /* Перенос слов */ 
    }
```

###  `word-spacing` , `letter-spacing`

CSS позволяет контролировать промежутки между словами и типографскими символами с помощью свойств word-spacing и letter-spacing.

Свойство **_word-spacing_** определяет интервалы между словами. Можно использовать положительные и отрицательные значения. Свойство наследуется.

Свойство **_letter-spacing_** определяет межбуквенный интервал. Свойство наследуется.

**Синтаксис: **
```
    word-spacing: normal/1px/0.2e/50%/inherit/initial;
```

@@@ (json)
[
    ["property", "comment"],
    ["**normal**", "Дополнительный интервал не применяется. Вычисляет в 0. Значение по умолчанию."],
    ["**размер**", "Задает дополнительный интервал в дополнение к внутреннему интервалу между словами, определенному шрифтом. Значения могут быть отрицательными, но могут быть ограничения, зависящие от реализации."],
    ["**initial**", "Устанавливает значение свойства в значение по умолчанию."],
    ["**inherit**", "Наследует значение свойства от родительского элемента."]
]
@@@


## 2. `Font`. Стили для шрифта

В файле CSS вы можете настроить несколько свойств шрифта: **font-family, font-size, font-style**. Это наиболее часто используемые свойства шрифта.


### `font-family`

Свойство **_font-family_** задает шрифт для элемента.

Может содержать несколько "запасных" названий шрифтов. В случае если первый из списка не установлен на компьютере пользователя, используется второй.

Существует два типа названия шрифтов:

1)  **family-name** - название семьи шрифтов. Например, "times", "courier", "arial"...
2)   **generic-family** - универсальные семейства шрифтов, такое как "serif", "sans-serif", "cursive", "fantasy", "monospace".

**Универсальные семейства шрифтов:**
* **_serif_** — шрифты с засечками (антиквенные), типа Times; 
* **_sans-serif_** — рубленные шрифты (шрифты без засечек или гротески), типичный представитель — Arial;
* **_cursive_** — курсивные шрифты; 
* **_fantasy_** — декоративные шрифты; 
* **_monospace_** — моноширинные шрифты, ширина каждого символа в таком семействе одинакова.

:exclamation: Начните с нужного шрифта и всегда заканчивайте названием семейства, чтобы браузер мог выбрать аналогичный шрифт в семействе, если другие шрифты недоступны.

:point_right: **Примечание**. Разделяйте каждое значение запятой. Если имя шрифта содержит пробел, оно должно быть заключено в кавычки. 


**Синтаксис:**
```
    font-family: <шрифт> [, <шрифт>[, ...]]
```

**Значения:** Любое количество имен шрифтов разделенных запятыми. 

*   serif — шрифты с засечками (антиквенные), типа Times;
*   sans-serif — рубленные шрифты (шрифты без засечек или гротески), типичный представитель Arial;
*   cursive — курсивные шрифты;
*   fantasy — декоративные шрифты;
*   monospace — моноширинные шрифты, ширина каждого символа в таком семействе одинакова (шрифт Courier).


### `font-weight`

Устанавливает насыщенность шрифта. 


**Синтаксис**
```
    font-weight: bold|bolder|lighter|normal|100|200|300|400|500|600|700|800|900
```

**Значения**

Насыщенность шрифта задаётся с помощью ключевых слов: bold — жирное начертание и normal — нормальное начертание. Также допустимо использовать условные единицы от 100 до 900. Значения bolder и lighter изменяют жирность относительно насыщенности родителя, соответственно, в большую и меньшую сторону.

Вот как числовые значения влияют на насыщенность шрифта.

*   100 — тонкое начертание;
*   200 — сверхсветлое;
*   300 — светлое;
*   400 — нормальное (аналогично normal);
*   500 — среднее;
*   600 — полужирное;
*   700 — жирное (аналогично bold);
*   800 — сверхжирное;
*   900 — тяжёлое.

Учтите, что не все шрифты поддерживают этот набор. Если указанное значение не поддерживается, то браузер приведёт шрифт к ближайшей насыщенности. К примеру, если вы указали 900 и оно не может быть показано, то браузер в действительности применит значение 700 как ближайшее, которое работает корректно.


### `font-style`

Определяет начертание шрифта — **_обычное_**, **_курсивное_** или **_наклонное_**. Когда для текста установлено курсивное или наклонное начертание, браузер обращается к системе для поиска подходящего шрифта. Если заданный шрифт не найден, браузер использует специальный алгоритм для имитации нужного вида текста.

@@@ (json)
[
    ["property", "comment"],
    ["**italic**", "Курсивный шрифт"],
    ["**oblique**", "Наклонный шрифт (все символы с обычным начертанием просто наклоняются вправо)"],
    ["**normal**", "Обычный шрифт"],
    ["**inherit**", "Наследует значение родител"]
]
@@@

**Синтаксис**
```
    p {
        font-style: italic;
    }
```


### `font-size`

Определяет размер шрифта элемента. Размер может быть установлен несколькими способами. 

1. **_В абсолютных размерах_** - xx-small, x-small, small, medium, large, x-large, xx-large- зависит от настроек браузера и операционной системы:
```
    font-size: xx-small; 
    font-size: x-small;
    font-size: small;
    font-size: medium; 
    font-size: large; 
    font-size: x-large; 
    font-size: xx-large;
```
    
2. **_В относительных размерах_** - larger, smaller - по отношению в размеру шрифта родительского элемента
```
    font-size: larger; 
    font-size: smaller;
```

3. **_В значениях длины:_**
```
    font-size: 12px; 
    font-size: 0.8em;
```

4. **_Процентные значения:_**
```
    ont-size: 80%;
```

5. **_Глобальные значения:_**
```
    font-size: inherit; 
    font-size: initial;
```

:exclamation: <значение длины> или <процентное значение> расчитываются по отношению к размеру родительского элемента.


### `line-height`

Межстрочный интервал **line-height** задаётся свойством, в качестве значения которого может указываться:

*   **Процент.** Высчитывается от размера шрифта элемента.
*   **Число.** Определяется как множитель от размера шрифта, который принимается за единицу. Например **line-height: 1.5;** установит полуторный интервал.
*   **Пиксели** или **пункты**. Определяют не переменное, как предыдущие варианты, а постоянное расстояние.

--- 

Давайте рассмотрим на примере, что является размером шрифта и межстрочным интервалом:

![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-font.png)"width: 400px;"


## 3. `vertical-align` - вертикальное выравнивание

Может задаваться только для строчных элементов (картинок, форм), определяется свойством **vertical-align**. С его помощью выравнивается не содержимое, а сами элементы, кроме случая с ячейкой – использование vertical-align выравнивает не её саму, а только расположенный в ней текст. Значения могут быть следующими:


@@@ (json)
[
    ["property", "comment"],
    ["**baseline**", "задаётся свойству по умолчанию и выравнивает базовую линию элемента по базовой линии родителя. Если у родителя её нет, то выравнивание происходит по нижней границе."],
    ["**top** и **bottom**", "Если задано первое значение, то верхний край элемента будет совпадать с верхним краем самого высокого элемента строки. Можно сказать, что **top** — это выравнивание по верхнему краю. Второе свойство выполняет противоположную функцию — совмещает нижний край оформляемого элемента с нижней частью элемента, расположенного в строке ниже всех, то есть происходит выравнивание по нижнему краю."],
    ["**text-top** и **text-bottom**", "От предыдущих свойств отличаются тем, что выравнивание происходит по самым нижним и верхним текстовым элементам, а не любым."],
    ["**sub** и **super**", "Аналоги HTML-тегов **<sub>** и **<sup>**. Первое свойство делает элемент подстрочным, второе — надстрочным. Шрифт текста при этом не меняется."],
    ["**middle**", "Выравнивание по центру относительно элемента-родителя."]
]
@@@

Также с помощью **vertical-align** можно переместить элемент вверх или вниз, указав значение в пикселях, единицах или процентах. Положительная цифра переместит его вверх, отрицательная — вниз.

## 4. `text-align` - Выравнивание текста в CSS

В таких программах, как, например, Microsoft Word вы наверняка встречали инструменты выравнивания текста по горизонтали. Выровнять текст можно по левому или по правому краю, по центру или по ширине. То же самое есть и в CSS – выравнивание текста производится с помощью свойства **text-align** и соответствующих значений, которые показаны в таблице:

@@@ (json)
[
    ["property", "comment"],
    ["**left**", "По левому краю"],
    ["**right**", "По правому  краю"],
    ["**center**", "По центру страницы/блока"],
    ["**justify**", "По ширине страницы/блока"],
    ["**start**", "Выравнивание текста по тому краю, с которого он начинается (то есть текст, идущий слева направо, выравнивается по левому краю)"],
    ["**end**", "Выравнивание текста по противоположному краю (то есть текст, идущий слева направо, выравнивается по правому краю)"]
]
@@@

.

**Синтаксис:**
```
    p {
        text-align: left;
    }
```
:exclamation: Значения **start** и **end** не поддерживаются некоторыми браузерами, включая Internet Explorer, поэтому, если нет острой необходимости в их применении, рекомендуем использовать значения **left** и **right**.



## 5. `background`. Фон.

Фон на веб-странице — это очень важно, поэтому для него предусмотрено немало свойств. Все они начинаются словом «Background». В переводе с английского «Background» и означает «Фон». О правилах оформления фона через CSS и пойдёт речь в статье.


### `background-color`

Мы уже говорили о свойстве **color**, которое позволяет задать цвет переднего плана элемента, то есть букв текста. **background-color** устанавливает задний фон любого HTML-элемента: таблицы, абзаца, списка и т. д.

Например, цвет фона всей страницы можно настроить так:
```
body { background: #EEFFCB; }
```

### `background-image`

Устанавливает в качестве фона картинку. Если изображение подобрано правильно, то страница на его фоне будет выглядеть гораздо красивее, чем на фоне одноцветном.

Например, картинка background.png хранится в той же папке, что и веб-страница, и вы хотите установить её как фон параграфам этого HTML-документа. Код будет таким:
```
    p { background-image: url(background.png); }
```
Для одного и того же веб-элемента можно установить несколько фоновых рисунков. Для этого достаточно перечислить их все в свойстве **background-image** через запятую:
```
    body { background-image: url(”image/background01.png”), url(”image/background02.png”), url(”image/background03.png”), url(”image/background04.png”); }
```
Очевидно, что без определённого позиционирования выбранные рисунки при отображении будут накладываться друг на друга, причём первое из перечисленных будет самым верхним, последнее — под всеми, задним фоном.


### `background-repeat`

По умолчанию фоновое изображение, если его размер меньше размера элемента, будет заполнять объект полностью, повторяясь с левого верхнего к правому нижнему углу.

![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-bgi.png)"width: 400px;"

Бывают ситуации, когда такое заполнение неприемлемо. Как раз для них и существует свойство **background-repeat**, которому можно указать следующие значения:


@@@ (json)
[
    ["property", "comment"],
    ["**repeat**", "Задано по умолчанию. Результат вы видели на рисунке выше."],
    ["**repeat-x**", "Картинка будет повторяться только слева направо, по горизонтали. По вертикали не будет, так что заполнит только первый слой."],
    ["**repeat-y**", "Рисунок будет повторяться по вертикали, но не по горизонтали, то есть идти вдоль левой границы страницы."],
    ["**no-repeat**"], "Фон не будет повторяться вообще."
]
@@@

![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-bgr.png)"width: 500px; float: left;"
![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-bgry.png)"width: 500px;"
![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-bgrnr.png)"width: 400px;"

### `background-position`

Позволяет задать позицию фоновому изображению, ведь не всегда нужно, чтобы оно отображалось с левого верхнего угла окна браузера. Для позиционирования достаточно указать два значения через пробел: координату по оси X (горизонтальное позиционирование) и координату по оси Y (позиционирование вертикальное). Задавать их можно в любых единицах длины, но для абсолютных значений рекомендуется использовать пиксели (**px**), а для относительных — проценты (**%**).
```
    background-position: 200px 350px;
```

Также картинку можно позиционировать зарезервированными словами.

@@@ (json)
[
    ["property", "comment"],
    ["**left**, **center** и **right**", "Для горизонтального расположения используются слова  (по левому краю, по центру и по правому краю соответственно)"],
    [" **top**, **center** и **bottom**", "позиционирование сверху, по центру и снизу.."]
]
@@@


### `background-attachment`

Определяет, будет ли фоновая картинка прокручиваться вместе с содержимым страницы или будет оставаться неподвижной. Значения могут быть такими:

@@@ (json)
[
    ["property", "comment"],
    ["**fixed**", "фон зафиксирован"],
    ["**scroll**", "фон разблокирован (прокручивается)"],
    ["**local**", "рисунок прокручивается только с содержимым элемента, но дальше, если элемент уже закончился, не идёт."]
]
@@@


**_Если изображений несколько_**, для них можно указать правила, перечислив их в одном свойстве background-attachment через запятую:
```
    background-attachment: fixed, scroll, local;
```

### `background-clip`

Определяет, как фоновое изображение или цвет фона будут выводиться относительно границ элемента.
![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-bgclip.png)"width: 800px;"


@@@ (json)
[
    ["property", "comment"],
    ["**content-box**", "фон отображается только под содержимым."],
    ["**border-box**", "выводится и под контентом, и под границами"],
    ["**padding-box**", "отображается внутри границ."]
]
@@@


### `background-origin`

То же, что и **background-clip**, с такими же значениями, только задаёт положение относительно границ не текущего элемента, а элемента-родителя.


### `background-size`

Свойство указывает браузеру размеры фонового изображения. Вы можете задать их в любых единицах длины (через пробел указывается сначала ширина, потом высота картинки). Если прописано только одно значение, то оно определит ширину, высота при этом останется исходной, то есть такой, как в файле изображения. Чтобы указать только высоту, а ширину оставить оригинальной, свойству **background-size** нужно задать значения auto размер (например, background-size: auto 300px).

В правиле можно использовать ещё два значения.

@@@ (json)
[
    ["property", "comment"],
    ["**cover**", "Масштабирует фон по размерам блока с сохранением исходных пропорций картинки, то есть рисунок не растянется и не станет слишком узким."],
    ["**contain**", "Помещает изображение внутрь блока, сохраняет пропорции."]
]
@@@


### `background`

Позволяет объединить значения перечисленных свойств в одной строке:
```
    background: url("background.jpg") center center / 100px 100px no-repeat content-box;
```

В примере между свойствами **background-position** и **background-size** стоит слеш (**/**), которым их значения друг от друга необходимо отделять, дабы не запутывать браузер.


## 6. Прозрачность -  `opacity` 

Определяет уровень прозрачности элемента веб-страницы. При частичной или полной прозрачности через элемент проступает фоновый рисунок или другие элементы, расположенные ниже полупрозрачного объекта

**_Значение по умолчанию_**: 1

**_Синтаксис:_**
```
    opacity: <число>
```

В качестве значения выступает число из диапазона [0.0; 1.0]. Значение 0 соответствует полной прозрачности элемента, 1, наоборот — его непрозрачности. Дробные числа вида 0.6 устанавливают полупрозрачность. Допускается писать числа без нуля впереди, вида opacity: .6.


## 7. Градиенты

Градиент – плавный переход от одного заданного цвета к другому. Бывают линейные и радиальные градиенты. Чтобы работать с градиентом нужно задать два цвета и точки перехода. В CSS градиенты используются для фона (являются значениями для background-image или background).


### `linear-gradient()` - Линейный градиент

**Линейный градиент** создается с помощью двух и более цветов, для которых задано направление, или **линия градиента**.

Если направление не указано, используется значение по умолчанию — **сверху-вниз**.

Цвета градиента по умолчанию распределяются равномерно в направлении, перпендикулярном линии градиента.


```
background: linear-gradient (угол / сторона или угол наклона с помощью ключевого слова (пары ключевых слов), первый цвет, второй цвет и т.д.);
```


**Направление градиента** может быть задано двумя способами:


*   **с помощью угла наклона** в градусах `deg`, значение которого определяет угол наклона линии внутри элемента.

```
    div {
        height: 200px;
        background: linear-gradient(45deg, #EECFBA, #C5DDE8);
    }
```



*   **с помощью ключевых слов** `to top`, `to right`, `to bottom`, `to left`, которые соответствуют углу градиента, равному `0deg`, `90deg`, `180deg` и `270deg` соответственно.

```
    div {
        height: 200px;
        background: linear-gradient(to right, #F6EFD2, #CEAD78);
    }
```

Если направление задано парой ключевых слов, например, `to top left`, то начальная точка градиента будет расположена в противоположном направлении, в данном случае справа внизу.

```
    div {
        height: 200px;
        background: linear-gradient(to top left, powderblue, pink);
    }
```

 Для чёткого распределения цветных полос каждый последующий цвет нужно начинать с точки остановки предыдущего цвета:


```
    div {
        height: 200px;
        background: linear-gradient(to right, #FFDDD6 20%, #FFF9ED 20%, #FFF9ED 80%, #DBDBDB 80%);
    }

```



### `radial-gradient()` - Радиальный градиент 

**Радиальный градиент** отличается от линейного тем, что цвета выходят из одной точки (центра градиента) и равномерно распределяются наружу, рисуя форму круга или эллипса.


```
    background: radial-gradient(форма градиента / размер / позиция центра, первый цвет, второй цвет и т.д.);
```


CSS

**Форма градиента** определяется ключевыми словами `circle` или `ellipse`. Если форма не задана, по умолчанию радиальный градиент принимает форму эллипса.


```
    div {
        height: 200px;
        background: radial-gradient(white, #FFA9A1);
    }
```


**Позиция центра** задаётся с помощью ключевых слов, используемых в свойстве `background-position`, с добавлением приставки `at`. Если позиция центра не задана, используется значение по умолчанию `at center`.


```
    div {
        height: 200px;
        background: radial-gradient(at top, #FEFFFF, #A7CECC);
    }
```

### Как можно использовать градиент?

В добавление к линейному и радиальному градиентам существует повтор градиента, который задается с помощью функций `repeating-linear-gradient()` и `repeating-radial-gradient()` соответственно. Фон из повторяющихся градиентов выглядит неаккуратно, поэтому рекомендуется начинать следующий цвет с точки остановки предыдущего, создавая таким образом полосатые узоры.


```
div {
    height: 200px;
    background: repeating-linear-gradient(45deg, #606dbc, #606dbc 10px, #465298 10px, #465298 20px);
}

div {
    height: 200px;
    background: repeating-radial-gradient(circle, #B9ECFE, #B9ECFE 10px, #82DDFF 10px, #82DDFF 20px);
}
```

За счёт комбинации градиента и изображения можно создавать интересные эффекты. 


```
    div {
      height: 453px;
      background: linear-gradient(45deg, rgba(103, 0, 31, .8), rgba(34, 101, 163, .5)), url(https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-bgrnr.png); 
      background-size: cover;
    }
```



## 8. `text-shadow` - тень текста

Добавляет тень к тексту, а также устанавливает её параметры: цвет тени, смещение относительно надписи и радиус размытия.
```
h1 {
    text-shadow: 3px 5px 6px #6C9;
}
```

![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-textshadow.png)"width: 650px;"


Как видно, мы указали целых четыре значения через пробел. Пройдемся по порядку:

*   **3px** – первое значение отвечает за смещение тени по оси X (вправо, влево). Положительным значением тень сдвигается вправо, а отрицательным – влево.
*   **5px** – второе значение отвечает за смещение тени по оси Y (вниз, вверх). Положительным значением тень сдвигается вниз, а отрицательным – вверх.
*   **6px** – третье значение отвечает за радиус размытия тени. Этот параметр указывать необязательно. По умолчанию размытие равняется 0 пикселей, что делает тень четкой и неразмытой.
*   **#6c9** – четвертое значение отвечает за цвет тени. Этот параметр указывать необязательно. По умолчанию цвет тени устанавливается такой же, как у текста, к которому применяется стиль.


## 9. `box-shadow` - тень елемента
![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-boxshadow.png)"width: 350px;"

Добавляет тень к элементу. Допускается использовать несколько теней, указывая их параметры через запятую, при наложении теней первая тень в списке будет выше, последняя ниже. Если для элемента задается радиус скругления через свойство [border-radius](https://webref.ru/css/border-radius), то тень также получится с закруглёнными уголками. Добавление тени увеличивает ширину элемента, поэтому возможно появление горизонтальной полосы прокрутки в браузере.

**Синтаксис:**

```
    box-shadow: inset 4px 4px 8px 5px #333;
```

Рассмотрим по порядку, за что отвечает каждый параметр (слева направо):


*   Ключевое слово **inset**: параметр, который необязательно указывать; рисует тень внутри элемента.
*   **4px - Сдвиг по оси X**: указывает степень смещения тени по горизонтали относительно элемента. Положительное значение означает сдвиг вправо, отрицательное — влево. Значение <strong><code>0</code></strong> означает, что тень без сдвига.
*   **4px - Сдвиг по оси Y**: указывает степень смещения тени по вертикали. Положительное значение означает сдвиг вниз, отрицательное — вверх. Значение <strong><code>0</code></strong> — это тень без сдвига.
*   **8px - Радиус размытия**: это степень размытия тени. Чем больше значение, тем более размыта тень. Если параметр не указан, используется значение по умолчанию — <strong><code>0</code></strong>. В таком случае тень будет идеально четкой.
*   **5px - Расширение**: необязательный параметр, отвечающий за растяжение тени по обеим осям; чем больше значение, тем больше растяжение. Расширение работает только при наличии предыдущего параметра. Значение по умолчанию — <strong><code>0</code></strong>.
*   **#333 Цвет тени**: с этим параметром всё понятно — он задает цвет тени элемента. Цвет по умолчанию — черный.

Данное свойство может принимать несколько групп значений (делать несколько теней одновременно). Для этого понадобится перечислить эти группы параметров через запятую. Например:

```
box-shadow: 15px 15px 20px #8b0163, inset 15px 15px 20px #630046;

box-shadow: -20px 20px 0 -17px #eee,
            20px -20px 0 -17px #eee,
            20px 20px 0 -20px #592385,
            0 0 0 2px #592385;
```


## :house: HomeWork

**1.Первый уровень (“”)**

**2.Второй уровень(“”)**

**3.Третий уровень(“”)**
