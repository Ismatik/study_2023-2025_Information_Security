---
# Front matter
title: "Информационная безопасность. Отчет по лабораторной работе № 2"
subtitle: "Шифры перестановки"
author: "Мухамеджанов Исматулло Иззатуллоевич"
group: NFImd-01-23
institute: RUDN University, Moscow, Russian Federation

# Generic otions
lang: ru-RU
toc-title: "Содержание"

# Bibliography
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

# Pdf output format
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
### Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Misc options
indent: true
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text

---

# Цель работы
Освоить на практике применение шифрование перестановкой [1].

# Указание к работе
Исходные данные.
Маршрутное шифрование
Шифрование с помощью решёток
Таблица Виженера
# Выполнение лабораторной работы
1.	Маршрутное шифрование.

  Данный способ шифрования разработал французский математик Франсуа Виет. Открытый текст записывают в некоторую геометрическую фигуру (обмчно прямоугольник) по некоторому пути, а затем, выписывая символы по другому пути, получают шифртекст. Пусть m и п — целые положительные числа, большие
  Открытый текст разбивается на блоки равной длины, состоящие из яисла символов, равному произведению ти. Если последний блок получится меньше остальных, то в него следует дописать требуемое количество произвольных символов. Составляется таблиqа размерности ти. Блоки вписывается построчно в таблицу. Криптограмма получается выписыванием букв из таблицы в соответствии с некоторым маршрутом. Ключом такой криптограммы является маршрут и числа m и п. Обычно буквьl выписывают по столбцам, которые упорядочивают согласно паролю: внизу таблицы приписывается слово из п неповторяющихся букв и столбцы нумеруются по алфавитному порядку букв пароля.
  
  Рассмотренный способ шифрования (столбцовая перестановка) в годы первой мировой войны использовала легендарная немецкая шпионка Мата Хари.

2.	Шифрование с пoмoщью решеток.

  Данный способ шифрования предложил австрийский криптограф Эдуард Флейснер в ISS1 году. Суть этого способа заключается в следующем. Выбирается натуральное число k > 1, строится квадрат размерности k и построено заполняется числами 1, 2,..., k2. В качестве примера рассмотри квадрат размерности k —— 2.

  Повернем	его по часовой	стрелке	на 900	и присоединим	к исходному квадрату справа.Проделаем	еще	дважды	такую	процедуру	и	припишем	получившиеся квадраты снизу. Получился большой квадрат размерности 2k.

  Далее из большого квадрата вырезаются клетки, содержащие числа от 1 до k2. В каждой клетке должно быть только одно число. Получается своего FOдil решето.	Шифрование	осуществляется	следующим	образом.	Решето накладывается	на чистый	квадрат	2k Х 2k	и в прорези вписываются	буквы
  
  исходного текста по порядку их следования. Когда заполнятся все прорези, решето поворачивается на 900 и вписывание букв продолжается. После третьего поворота все клетки большого квадрата окажутся заполненными. Подобрав подходящий пароль (число букв пароля должно равняться k2 и они не должны повторяться), выпишем буквы по столбцам. Очередность столбцов определяется алфавитным порядком букв пароля.


3.	Шифрование с пoмoщью решеток.
  В 1585 году французский криптограф Блез Виженер опубликовал свой метод шифрования в «Трактате о шифрах». Шифр считался нераскрываемым до 1863 года, когда австриец Фридрих Казиски взломал его.
  Открытый текст разбивается на блоки длины п. Ключ представляет собой Следовательность из п натуральных чисел: m, n2, ... ,  . Дал е в каждом блоке
  первая буква циклически сдвигается вправо по алфавиту на •1 позиций, вторая букІЗа — на m позиций, последняя — на ntt позицFfй. Для лучшего запоминания в качестве ключа можно взять осмысленное слово, а алфавитные номера входящих
  в него букв использовать для осуществления сдвигов. 





![Программа (1)](<Маршрутное шифрование.png>){#fig:1 width=100%}

![Программа (2)](<Шифрование с помощью решёток 1.png>){#fig:2 width=100%}

![Программа (3)](<Шифрование с помощью решёток 2.png>){#fig:3 width=100%}

![Программа (4)](<Шифр Виженера.png>){#fig:4 width=100%} 

<!-- ![Вывод работы программы](images/1.jpg){#fig:5 width=100%}

<!-- ## Контрольные вопросы
1. Как, зная один из текстов (P1 или P2), определить другой, не зная при
этом ключа? -- По формулам: C1 ⊕ C2 ⊕ P1 = P2, C1 ⊕C2 ⊕ P2 = P1.

2. Что будет при повторном использовании ключа при шифровании текста? -- Расшифровка текста.

3. Как реализуется режим шифрования однократного гаммирования одним
ключом двух открытых текстов? -- Ключ применяется к каждому из текстов в отдельности, получаются два различных шифротекста.

4. Перечислите недостатки шифрования одним ключом двух открытых
текстов. -- При наличии минимум двух шифротекстов и хотябы одного открытого текста можно получить другой открытый текст даже не имея ключа.

5. Перечислите преимущества шифрования одним ключом двух открытых
текстов. -- Нет необходимости в хранении двух последовательностей символов ключа. -->

# Выводы
Освоены шифры методом перестановки

# Список литературы
1. Методические материалы курса


