# web-dev-exercises-with-solutions
HTML/CSS/JavaScript/ReactJS practice exercises with solutions
## Exercises for lecture #5 Стилізація шрифтів та тексту



1. В середині exercises створіть піддирексторію lecture-04. В середині lecture-04 створіть файли index.html та README.md




Є кілька способів вказати розмір шрифту, включаючи ключові слова або числові значення для пікселів або ems. Виберіть відповідний метод на основі потреб конкретної веб-сторінки.
Ключові слова

Ключові слова – хороший спосіб встановити розмір шрифтів в Інтернеті. Установивши розмір шрифту для ключового слова в елементі <body>, ви можете встановити відносний розмір шрифту скрізь на сторінці, що дасть вам можливість легко збільшити або зменшити шрифт відповідно на всій сторінці.
Пікселі

Встановлення розміру шрифту в піксельних значеннях (px) є хорошим вибором, коли вам потрібна точність у пікселях. Значення px є статичним. Це незалежний від ОС і кросбраузерний спосіб буквально сказати браузерам відтворювати літери з точною кількістю пікселів у висоту, яку ви вказали. Результати можуть дещо відрізнятися в різних браузерах, оскільки вони можуть використовувати різні алгоритми для досягнення подібного ефекту.

Параметри розміру шрифту також можна використовувати разом. Наприклад, якщо для батьківського елемента встановлено значення 16 пікселів, а для його дочірнього елемента — більше, дочірній елемент відображатиметься на сторінці більшим, ніж батьківський.

Примітка. Визначення розміру шрифту в px недоступне, оскільки користувач не може змінити розмір шрифту в деяких браузерах. Наприклад, користувачі з обмеженим зором можуть забажати встановити розмір шрифту набагато більший за розмір, обраний веб-дизайнером. Уникайте їх використання для розмірів шрифту, якщо ви хочете створити інклюзивний дизайн.
Емс

Використання значення em створює динамічний або обчислений розмір шрифту (історично одиниця em була похідною від ширини великої літери "M" у певному шрифті). Числове значення діє як множник властивості розміру шрифту елемента, для якого воно використовується. Розглянемо цей приклад:

p {
  font-size: 2em;
}

У цьому випадку розмір шрифту елементів <p> буде вдвічі перевищувати обчислений розмір шрифту, успадкований елементами <p>. За розширенням, розмір шрифту 1em дорівнює обчисленому розміру шрифту елемента, на якому він використовується.

Якщо розмір шрифту не було встановлено на жодному з предків <p>, тоді 1em дорівнюватиме розміру шрифту браузера за замовчуванням, який зазвичай становить 16 пікселів. Отже, за замовчуванням 1em еквівалентний 16px, а 2em еквівалентний 32px. Якщо ви встановите розмір шрифту 20 пікселів для елемента <body>, наприклад, тоді 1em для елементів <p> натомість буде еквівалентним 20 пікселям, а 2em буде еквівалентним 40 пікселям.

Щоб обчислити еквівалент em для будь-якого необхідного значення пікселя, ви можете скористатися цією формулою:

em = бажане значення елемента в пікселях / розмір шрифту батьківського елемента в пікселях

Наприклад, припустімо, що розмір шрифту <body> сторінки встановлено на 16 пікселів. Якщо розмір шрифту, який вам потрібен, становить 12 пікселів, тоді вам слід вказати 0,75 em (оскільки 12/16 = 0,75). Так само, якщо вам потрібен розмір шрифту 10 пікселів, тоді вкажіть 0,625 em (10/16 = 0,625); для 22px вкажіть 1,375em (22/16).

em є дуже корисною одиницею в CSS, оскільки вона автоматично адаптує свою довжину до шрифту, який читач вибирає для використання.

Пам’ятайте про один важливий факт: значення em складаються. Візьміть наступний HTML і CSS:

html {
  font-size: 100%;
}
span {
  font-size: 1.6em;
}

html

<div>
  <span>Outer <span>inner</span> outer</span>
</div>

Якщо припустити, що розмір шрифту веб-переглядача за замовчуванням становить 16 пікселів, слова «зовнішній» відображатимуться з розміром 25,6 пікселів, а слово «внутрішній» — 40,96 пікселів. Це пояснюється тим, що внутрішній розмір шрифту <span> становить 1,6 em, що відповідає розміру шрифту батьківського елемента, який, у свою чергу, відповідає розміру шрифту батьківського елемента. Це часто називають компаундуванням.
Rems

rem значення були винайдені, щоб уникнути проблеми компаундування. значення rem відносяться до кореневого елемента html, а не до батьківського елемента. Іншими словами, це дозволяє вам вказати розмір шрифту у відносний спосіб без впливу на розмір батьківського шрифту, тим самим усуваючи змішування.

CSS нижче майже ідентичний попередньому прикладу. Винятком є лише те, що одиниця змінена на рем.

html {
  font-size: 100%;
}
span {
  font-size: 1.6rem;
}

Then we apply this CSS to the same HTML, which looks like this:
html

<span>Outer <span>inner</span> outer</span>




Одиниці em, rem, ex залежать від розміру шрифта для кожного елемента у документі. 
Одиниця em - просто розмір шрифта. Будь який текст, розмір якого вимірюється в одиницях em, буде залежати від розміру шрифта його пращура. 
Одиниця ex розраховується від довжини строчної літери x. 
Один rem (root em) - це розмір шрифта кореневого елементу у документі. Одиниця rem для всього документу одна й та сама. Наприклад:
p { margin-left: 1rem }
h1 { font-size: 3em; margin-left: 1rem }
1rem = 10px. 
html  {  font-size: 62.5%; }
body  {  font-size: 1.4rem; } /* =14px */
h1      {  font-size: 2.4rem; } /* =24px */



приклад
У наведеному нижче фрагменті ширина <div> встановлена на 10 em. Таким чином, модуль em масштабує ширину <div> до 400 пікселів (10 помножено на 40 пікселів — розмір шрифту батьківського елемента <div> (<body>)).

HTML
<html style="font-size:20px;">
  <body style="font-size:40px;">
	<div>I am a child of the body element.</div>
  </body>
</html>

CSS
div {
  width: 10em;
  border: 2px solid purple;
  background-color: thistle;
}

Однак у наведеному нижче фрагменті ширина <div> встановлена на 10 rem. Таким чином, блок rem масштабує ширину <div> до 200 пікселів (10 помножити на 20 пікселів — розмір шрифту кореневого елемента (<html>)).
HTML
<html style="font-size:20px;">
  <body style="font-size:40px;">
	<div>I am a child of the body element.</div>
  </body>
</html>

CSS
div {
  width: 10rem;
  border: 2px solid purple;
  background-color: thistle;
}

к і em, rem залежить від розміру шрифту, але в цьому випадку завжди розмір шрифту, визначений кореневим елементом документа (:root {…}, для веб-сайтів це елемент html). Таким чином, у всьому вашому коді CSS base 1rem завжди відображатиметься однакового розміру. Але виникає питання: який це буде розмір на практиці?

Щоб відповісти на це питання, давайте коротко поговоримо про доступність (скорочено a11y). Кожен браузер має стандартний розмір шрифту та спосіб, за допомогою якого користувач може його змінити.
знімок екрана параметра Firefox для шрифту за замовчуванням

Це базовий розмір шрифту, який користувачі бачитимуть на вашому веб-сайті, якщо його не змінюватиме ваш CSS. Типовим значенням тут є 16 пікселів, і згідно з цим дослідженням близько 3% користувачів змінюють цей параметр, майже завжди на щось більше, ніж 16. Коли справа доходить до Інтернету, 3% – це чимало мільйонів людей!

Тепер, якщо ви зробите щось подібне…

html {

  font-size: 14px;

  /* 🚫 do not do something like this! */

}


body {

  font-size: 14px;

  /* 🚫 this is also bad */

}
… ви порушуєте частину a11y для 3 відсотків людей. Ці люди покладаються на збільшення тексту, а ваш статично оголошений розмір шрифту цьому перешкоджає.

Це не означає, що весь ваш текст має бути >= 16 пікселів. Це просто означає, що люди, яким потрібен більший текст, отримають більший текст. Отже, якщо ваш дизайн використовує 14 пікселів для основного тексту, встановлений користувачем розмір шрифту браузера 20 пікселів (або 125 %) відображатиметься як 125 % × 14 пікселів == 17,5 пікселів.

Щоб це працювало як для вашого дизайну, так і для ваших користувачів, просто використовуйте rem для розмірів шрифту та не встановлюйте базовий розмір шрифту:

html {

  /* do not specify any font size here, at least not in px */

}


body {

  font-size: 0.875rem; /* == 14/16 */

  padding: 2rem; /* 32px */

}
Подивіться на ці чотири кнопки. Вони здаються ідентичними для 97% усіх користувачів (натовп 16 пікселів):
чотири поля в контейнері з розміром шрифту: початковий;

Немає успадкованого контексту розміру шрифту. Зліва направо:

 	використовує px для всього
 	використовує em для розміру шрифту та px для відступу
 	використовує їх для всього
 	використовує rem для всього

На перший погляд усі чотири реалізації здаються еквівалентними. Але подивіться, що станеться, якщо змінити розмір шрифту браузера за замовчуванням на 24 пікселя (150%):
чотири поля в контейнері з розміром шрифту: початковий; і змінений розмір за замовчуванням

Зліва направо:

 	font-size: 24px Це поле взагалі не змінилося, тому що ми замінюємо налаштування за замовчуванням значенням пікселів. Це погано, користувач повинен це контролювати!
 	font-size: 1.5em — краще, шрифт більший, але padding: 12px все ще статичний, тому відступ не масштабується, і дизайнер, ймовірно, буде незадоволений (вони, як правило, так роблять).
 	padding: 0,5em — найкращий! Тепер також ваги для наповнення. 0.5em === 12px, оскільки розмір шрифту в цьому полі 1.5em == 24px
 	але rem здається ідентичним... навіщо турбуватися?

Подивіться, що відбувається, коли вони з’являються в контейнері з указаним розміром шрифту, який вони успадковують:
чотири поля в контейнері з розміром шрифту: початковий; і змінений розмір за замовчуванням

 	перший ще замалий
 	другий завеликий і неправильна підкладка
 	наш попередній переможець ще більший, оскільки підкладка адаптується
 	Те, що використовує rem, можливо, є «правильним» рішенням, оскільки воно масштабується відповідно до розміру шрифту користувача, але не залежить від декларації розміру шрифту батьківського елемента.

Висновок. Використовуйте одиниці виміру, коли ви змінюєте розмір тексту або коли хочете, щоб щось було пропорційним налаштуванням розміру тексту користувача. Деякі люди стверджують, що ви повинні використовувати rem для всього. Інші не погоджуються. На мою думку, остаточної відповіді на це питання немає. Це залежить від вашого дизайну, вашого підходу до a11y і вашого випадку використання. Пам’ятайте про відмінності та — разом із дизайнером — вирішуйте для кожного зі своїх компонентів, як має поводитися масштабування. Будьте послідовними та тестуйте речі з різними налаштуваннями розміру шрифту та рівнями масштабування браузера!



приклад

У наведеному нижче фрагменті ширина <div> встановлена на 20 em. Таким чином, модуль em масштабує ширину <div> до 600 пікселів (20 помножено на 30 пікселів — розмір шрифту батьківського елемента <div> (<main>)).

HTML
<html>
	<body>
    	<main style="font-size:30px; width:400px;">
        	<div>I am a child of the main element.</div>
    	<main>
	</body>
</html>

CSS
div {
  width: 20em;
  border: 2px solid blue;
  background-color: lightsteelblue;
}


However, in the snippet below, <div>'s width is set to 20%. Therefore, the percentage unit will scale the <div>'s width to 80px (20% multiplied by 400px—the width of <div>'s parent (<main>)).

Однак у наведеному нижче фрагменті ширина <div> встановлена на 20%. Таким чином, одиниця відсотка масштабує ширину <div> до 80 пікселів (20% помножено на 400 пікселів — ширина батьківського елемента <div> (<main>)).
HTML
<html>
	<body>
    	<main style="font-size:30px; width:400px;">
        	<div>I am a child of the main element.</div>
    	<main>
	</body>
</html>

CSS
div {
  width: 20%;
  border: 2px solid blue;
  background-color: lightsteelblue;
}

Одиницею, яка досить часто використовується в CSS, є %. Здебільшого він інтерпретується як процентні частки тієї самої властивості в батьківському елементі. Отже, значення width: 66,66% зробить елемент шириною на дві третини його батьківського елемента, але значення font-size: 150% збільшить поточний розмір шрифту на 50%. Є кілька дивних винятків, наприклад, padding-top: 50% стосується не батьківської прокладки, а її ширини. Перегляньте цю статтю про злі частини CSS, щоб дізнатися більше... Крім того, не використовуйте їх неправильно 🙏
Відступ: сюрприз-вікторина!

Давайте перевіримо, чи зможете ви відповісти на цю вікторину:

*, *:before, *:after {

  box-sizing: border-box;

  /* If this means nothing to you, read here:

 	https://www.paulirish.com/2012/box-sizing-border-box-ftw/ */

}


body {

  font-size: 0.75rem;

}


header {

  max-width: 50rem;

  margin: auto;

}


.logo {

  width: 25%;

}

<!DOCTYPE html>

<html>

  <head>

   …

  </head>


  <body>

	<header>

  	<img class="logo" src="…" alt="…" />


  	<p>Utility Muffin Research Kitchen™️</p>

	</header>

  </body>

</html>

Наскільки широким буде логотип у px для більшості користувачів на великому екрані?
 	Наскільки широким буде логотип у пікселях для більшості користувачів телефону з шириною екрана 380 пікселів?
 	Наскільки великим буде текст у <p> під логотипом, у пікселях, для більшості користувачів?

Answers (click to reveal):

1. the logo will be 200px wide, one fourth the width of 50rem, which is 12.5rem × 16px = 200px

2. 95px. The header will use 100% of the viewport witdth, so 25% × 380px = 95px

3. 12px — because 0.75rem == 0.75 × the default font size, which is 16px: 16 * 0.75 == 12  	Наскільки великим буде текст у <p> під логотипом, у пікселях, для більшості користувачів?



1. Відредагуйте файл index.html

```html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- змініть title на: Моя домашня сторінка -->
    <title>Document</title>

	<link rel="shortcut icon" href="/favicon.ico" type="image/x-icon">

</head>
<body>

</body>
</html>

```

/* All rules below have the same resultant line height */

/* number/unitless */
div {
  line-height: 1.2;
  font-size: 10pt;
}

/* length */
div {
  line-height: 1.2em;
  font-size: 10pt;
}

/* percentage */
div {
  line-height: 120%;
  font-size: 10pt;
}

/* font shorthand */
div {
  font:
  10pt/1.2 Georgia,
  "Bitstream Charter",
  serif;
}

Для блочних елементів line-height визначає мінімальну довжину рядка. 
Для вбудованих елементів (<img>) властивість line-height ігнорується. 
Для рядкових елементів line-height задає довжину, що використовується для розрахунку довжини рядка блоку.
line-height: <множник> | <розмір> | <відсотки> | normal

Ви можете застосувати CSS до списку HTML, щоб змінити форму маркера, застосувати зображення чи емодзі як маркер. 

Для цього вам потрібно використовувати властивості типу списку та псевдоелемента CSS.

Приклад 1: як стилізувати елементи списку колами

<!DOCTYPE html>
<html>
<head>
  <title> Unordered List </title>
<style>
ul {
    list-style-type: circle;
}
</style>
</head>
<body>

<ul>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
    <li>Item 4</li>
    <li>Item 5</li>
</ul>

</body>
</html>

Output

example-style-list-items-with-circles
Example 2: How to style list items with squares

<!DOCTYPE html>
<html>
<head>
  <title> Unordered List </title>
<style>
ul {
    list-style-type: square;
}
</style>
</head>
<body>

<ul>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
    <li>Item 4</li>
    <li>Item 5</li>
</ul>

</body>
</html>

  
2. В середині exercises створіть піддирексторію lecture-02. В середині lecture-02 створіть файли index.html та README.md

**Результатом повинна стати така структура:**
```
├── exercises
│   ├── index.html
│   ├── lecture-01
│   │   ├── index.html
│   │   └── README.md
│   ├── lecture-02
│   │   ├── index.html
│   │   └── README.md
│   └── README.md
├── index.html
├── LICENSE
└── README.md

```

3. Відредагуйте файл exercises/lecture-02/index.html

```html 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- змініть title на: Моя домашня сторінка -->
    <title>Document</title>
</head>
<body>
    
    <!-- Введіть свій код під цим рядком-->
    <!-- Додайте заголовок першого рівня: Ласкаво просимо до мого сайту! -->
	<h1>Ласкаво просимо до мого сайту!</h1>
    
    <!-- Додайте підзаголовок другого оівня під назвою Про програмування -->

    <h2>About Programming</h2>
    
	<!-- Додайте підзаголовок третього рівня під назвою Про HTML -->

    <h3>About HTML</h3>

   <!-- Додайте підзаголовок третього рівня під назвою Про CSS -->

    <h3>About CSS</h3>
   
</body>
</html>

```

4. Весь текст у браузері відображатиметься в одному рядку, доки він не досягне межі вікна браузера. 

```html
<body>

Весь текст у браузері відображатиметься в одному рядку, доки він не досягне межі вікна браузера. 

<!-- додати розрив рядків для наступних 3-х речень -->

This is regular text.
This is another line after line break.
This is another line after line break.

<!-- форматувати наступні 3 речення як параграфи -->

This is a first paragraph. You can add any kind of text here. 
This is a second paragraph. This is some sample text. 
This is another paragraph. You can add multiple lines of text in this paragraph.

<p>This is a first paragraph. You can add any kind of text here. </p>
<p>This is a second paragraph. This is some sample text. </p>
<p>This is another paragraph. You can add multiple lines of text in this paragraph. </p>

</body>
```
### Рішення:
```html
<body>

Весь текст у браузері відображатиметься в одному рядку, доки він не досягне межі вікна браузера. 

<!-- додати розрив рядків для наступних 3-х речень -->

This is regular text.<br/>
This is another line after line break.<br/>
This is another line after line break.<br/>

<!-- форматувати наступні 3 речення як параграфи -->
<p>This is a first paragraph. You can add any kind of text here. </p>
<p>This is a second paragraph. This is some sample text. </p>
<p>This is another paragraph. You can add multiple lines of text in this paragraph. </p>

</body>
```

5. Змінити <зміни_мене> на відповідні <теги> HTML

```html

	<!-- Тут має бути розділ сторінки, що містить посилання на інші сторінки або частини сторінок.  -->
	<change_me>
		<!-- Тут має бути елемент списку елементів, де порядок елементів не важливий -->
		<change_me>
 			<!-- Елементи списку є дочірніми вузлами списку елементів. -->
  			<change_me>
  				<!-- Елемент з обов’язковим атрибутом href, що задає URl-адресу веб-сторінки: -->
  				<change_me href="/">Home</change_me>
	  			<change_me><a href="/events">Current Events</a></change_me>
 			</change_me>
 		</change_me>
	</change_me>

	<!-- Тут має бути розділ сторінки, що містить посилання на інші сторінки або частини сторінок.  -->
	<nav>
		<!-- Тут має бути елемент списку елементів ul, де порядок елементів не важливий -->
	 	<ul>
			<!-- Елементи списку li є дочірніми вузлами ul. -->
	  		<li>
				<!-- Елемент з обов’язковим атрибутом href, що задає URl-адресу веб-сторінки: -->
	 			<a href="/">Home</a>
	  		</li>
	  		<li><a href="/events">Current Events</a></li>
	 	</ul>
	</nav>

	<!-- Тут має бути елемент заголовка що обгортає елемент заголовка 1 та парвграф. -->
	<change_me>
		 <change_me>Welcome to...</change_me>
		 <change_me>Це елемент заголовка 1</change_me>
	</change_me>

	<change_me>
	   <!-- Це початок короткого абзацу. Він має деякі  вкладені теги, щоб підкреслити/виділити частину тексту. Наприклад: -->
	   <change_me>Це жирний текст.</change_me>
	   І, що ще цікавіше:
	   <change_me>Це курсив!</change_me>
	</change_me>

	<!-- Це розділ, що є базовим контейнером для елементів основного потоку. -->
	<change_me>
		<change_me>Це підзаголовок, укладений у теги "h3".</change_me>

   		<change_me>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quam optio expedita provident ratione itaque numquam, dolorem, at consequuntur laborum excepturi magnam culpa impedit obcaecati enim dolor totam. Assumenda, vel impedit?</change_me>
   
		<!-- Наступний тег використовують для визначення рядкових елементів у документі -->
		<p>Частка тексту <change_me style="color:#ff0000">червоного</change_me> кольору.</p>
		
		
   		<!-- Тут має бути горизонтальна лінія  -->
    	<change_me />
   
	    <change_me>
	   		Зменшує розмір шрифта на одиницю по відношенню до розміру звичайного тексту.
	   	</change_me>

   		<!-- Цей тег використовується для виділення цитат всередині документа. Тег має атрибут cite -->
		<change_me cite="https://www.ukrlib.com.ua/books/printit.php?tid=1052">Но зла Юнона, суча дочка, Розкудкудакалась, як квочка, — Енея не любила — страх; Давно уже вона хотіла, Його щоб душка полетіла К чортам і щоб і дух не пах.
		</change_me>

		<!-- Цей тег використовується для виділення коротких цитат.  -->
		<change_me>Розкудкудакалась, як квочка, — Енея не любила — страх</change_me>

		<!-- Цей тег маркує текст как цитату чи примітку на інший матеріал.  -->
		<p>ІВАН КОТЛЯРЕВСЬКИЙ <change_me>ЕНЕЇДА</change_me></p>

   		<!-- Цей тег дозволяє зберегти оригінальне форматування.  -->
		<change_me>
		       Но зла Юнона, суча дочка,
		       Розкудкудакалась, як квочка, —
		       Енея не любила — страх;
		       Давно уже вона хотіла,
		       Його щоб душка полетіла
		       К чортам і щоб і дух не пах.
		</change_me>
	</change_me>
	<!-- Це розділ, що є нижнім колонтитулом для його найближчого предка або кореневого елемента. -->
	<change_me>
	    <!-- container -->
	    <div>
		    <!-- Замінити символ © посиланням на сутність -->
		    <p>© 2024 All rights reserved.</p>
	    </div>
	</change_me>

```
### Рішення:
Змінити <зміни_мене> на відповідні <теги> HTML

```html

	<!-- Тут має бути розділ сторінки, що містить посилання на інші сторінки або частини сторінок.  -->
	<nav>
		<!-- Тут має бути елемент списку елементів ul, де порядок елементів не важливий -->
	 	<ul>
			<!-- Елементи списку li є дочірніми вузлами ul. -->
	  		<li>
				<!-- Елемент з обов’язковим атрибутом href, що задає URl-адресу веб-сторінки: -->
	 			<a href="/">Home</a>
	  		</li>
	  		<li><a href="/events">Current Events</a></li>
	 	</ul>
	</nav>

	<!-- Тут має бути елемент заголовка що обгортає елемент заголовка 1 та парвграф. -->
	<header>
		 <p>Welcome to...</p>
		 <h1>Це елемент заголовка 1</h1>
	</header>

	<p>
	   <!-- Це початок короткого абзацу. Він має деякі  вкладені теги, щоб підкреслити/виділити частину тексту. Наприклад: -->
	   <strong>Це жирний текст.</strong>
	   І, що ще цікавіше:
	   <em>Це курсив!</em>
	</p>

	<!-- Це розділ, що є базовим контейнером для елементів основного потоку. -->
	<div>
		<h3>Це підзаголовок, укладений у теги "h3".</h3>

   		<div>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quam optio expedita provident ratione itaque numquam, dolorem, at consequuntur laborum excepturi magnam culpa impedit obcaecati enim dolor totam. Assumenda, vel impedit?</div>
   
		<!-- Наступний тег використовують для визначення рядкових елементів у документі -->
		<p>Частка тексту <span style="color:#ff0000">червоного</span> кольору.</p>

   		<!-- Тут має бути горизонтальна лінія  -->
    	<hr />
   
	    <small>
	   		Зменшує розмір шрифта на одиницю по відношенню до розміру звичайного тексту.
	   	</small>

   		<!-- Цей тег використовується для виділення цитат всередині документа. Тег має атрибут cite -->
		<blockquote cite="https://www.ukrlib.com.ua/books/printit.php?tid=1052">Но зла Юнона, суча дочка, Розкудкудакалась, як квочка, — Енея не любила — страх; Давно уже вона хотіла, Його щоб душка полетіла К чортам і щоб і дух не пах.
		</blockquote>

		<!-- Цей тег використовується для виділення коротких цитат.  -->
		<q>Розкудкудакалась, як квочка, — Енея не любила — страх</q>

		<!-- Цей тег маркує текст как цитату чи примітку на інший матеріал.  -->
	
		<p>ІВАН КОТЛЯРЕВСЬКИЙ <cite>ЕНЕЇДА</cite></p>

   		<!-- Цей тег дозволяє зберегти оригінальне форматування.  -->
	
	  	<pre>
	       Но зла Юнона, суча дочка,
	       Розкудкудакалась, як квочка, —
	       Енея не любила — страх;
	       Давно уже вона хотіла,
	       Його щоб душка полетіла
	       К чортам і щоб і дух не пах.
	   	</pre>
	</div>

	<!-- Це розділ, що є нижнім колонтитулом для його найближчого предка або кореневого елемента. -->
    <footer>
       <!-- container -->
       <div>
       <!-- Замінити символ © посиланням на сутність -->
         <p>&copy; 2024 All rights reserved.</p>
       </div>
    </footer>

```

6. Створіть на https://github.com мінімальний сайт, що складається з 4 сторінок:

	1. Головна - index.html
	2. Про нас - about.html
	3. Каталог - catalog.html
	4. Контакти - contact.html

Кожна сторінка повинна мати такі розділи

	- nav
	- header
	- footer

- Розділ nav повинен містити відносні посилання нв сторінки сайта, наприклад <a href="/">Home</a>
- Розділ header повинен містити тег загодовку 1-го ріаня.
- Розділ footer повинен містити абсолютеі посилання нв зовнішні сторінки, наприклад: <a href="https://www.google.com">Google</a>, та відкривати відповідний документ у новому вікні.

Завантажте створений сайт у власний репозиторій персонального сайту. 

## LICENSE
This repository follows the [MIT License](https://github.com/janusnic/web-dev-exercises-with-solutions/tree/main/LICENSE).

