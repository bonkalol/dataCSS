# QSTemplate
----------

<a href="https://github.com/bonkalol/QSTemplate">Grunt</a> или <a href="https://github.com/bonkalol/QSTemplate-gulp">Gulp</a> версия

## Logo will be soon

QSTempalate это шаблон для быстрого старта проекта. Состоит он из 3ех мощных инструментов 
front-end разработки.

## Установка

	git clone https://github.com/bonkalol/QSTemplate-gulp .
	npm install

## Haчало работы

	gulp start

## Баги, пожелания

	https://github.com/bonkalol/QSTemplate-gulp/issues

## Пожертвования

	Yandex Money 410011314798585


## Jade

Node шаблонизатор, который тут используется как HTML препроцессор, jade позволяет ускорять написание HTML кода,
а так же разбивать его на некоторые отдельные части, с которыми куда удобнее работать, чем с одним файлом в 800 строк
кода, но это не все возможности Jade, более подробно вы можете ознакомиться с ним прочитав 
<a href="http://jade-lang.com/reference/" title="Jade Lang Page"> Language Reference </a> на сайте <a href="http://jade-lang.com" title="Jade Lang Page"> Jade-lang. </a>

## SCSS + Autoprefixer

SASS - CSS Препроцессор, который позволяет расширить CSS, дает возможность использовать Циклы и Условия,
а так же переменные и многое другое. Ознакомиться можно здесь => <a href="http://sass-lang.com/">sass-lang.com</a>.

## Gulp

Система сборки. Gulp комплирует файлы, собирает из множества файлов один файл, минифицирует код/изображения,
сам создаст вам спрайт, сам заметить изменения в файле и перекомпилирует его, а так же многое другое, к тому же он намного быстрее чем <a href="http://gruntjs.com/">Grunt</a>. Более подробно о Gulp
можно прочитать на <a href="http://gulpjs.com/">gulpjs.com/</a>.

## Основные feature

### Продуманная архитекрута проекта

<img src="http://blinnikovbogdan.ru/QSTemplate/images/template-tree.png" alt="Tempalte Tree" style="max-width: 100%"/>

Dev папка - в ней находятся всевозможные исходиники, будь то изображения / scss / jade файлы

----------

Dev -> scss

<img src="http://blinnikovbogdan.ru/QSTemplate/images/scss-tree.png" alt="SCSS tree" style="max-width: 100%"/>

Тут хочу подробно остановиться на 2ух файлах, это base.scss и config.scss

<strong style="font-size: 1.2em">Config.scss</strong>

<img src="http://blinnikovbogdan.ru/QSTemplate/images/config.png" alt="SCSS tree" style="max-width: 100%"/>

В Файле config.scss лежат основные конфиги проекта, в нем мы можем определить, нужен ли нам
reset.css, repsonsive ( включение, выключение media queries) ли сайт, использовать ли свойство
box-sizing: border-box, сглаживать ли шрифты, а так же базовый шрифт и его размер.

Эти данные в последствии используются в коде, для включения/отключения некоторых функций.

<img src="http://blinnikovbogdan.ru/QSTemplate/images/responsive-scss.png" alt="repsonsive scss screenshot" style="max-width: 100%">

Например как в этом пример. Мы видим, что если условие выполняется, то тогда media queries брекпоинты работают. Если в config.scss
поменять значение на false, то работать они соответсвенно не будут.

<strong style="font-size: 1.2em">Base.scss</strong>

В папке base лежат все базовые стили, файл base.scss , предназначен для базовой стилизации тегов.

<strong style="font-size: 1.2em">About sass</strong>

По задумке для каждой страницы должен создаваться отдельный .scss файл и помещаться в project/pages/

В папке meta/ хранятся файлы с миксинами, тихими классами и переменными.

В папке cosmetic/ файл CSS анимации (animation.scss), файл отвечающий за респонсив (responsive.scss) и файл отвечающие за различные эффекты.

<strong style="font-size: 1.2em">Немного о cosmetic.scss</strong>

Этот файл предназначен для добавления на страницу визуальных эффектов, например, 3d трансорфмаций который будут дальше использоваться для многих элементов, стили этого файла должны работать по принципу "Progressive enhancement", т.е. прогрессивное улучшение, допустим вы разрабатываете сайт для
устаревших браузеров которые не поддерживают свойства box-shadow / border-radius , класс, к которому будет применяться этот стиль, стоит выписать сюда и добавить к нему свойство box-shadow.

<strong style="font-size: 1.2em">Немного о project/</strong>

В папке project лежат .scss файлы страниц, а так же иногда я создаю папку project/items/ и в неё кладу различные блоки которые повторяются на страницах, допустим навигация. Так же тут есть файл class.lib в котором лежат часто используемые классы.

----------

Jade

<img src="http://blinnikovbogdan.ru/QSTemplate/images/jade-tree.png" alt="jade-tree" style="max-width: 100%">

В папке jade уже созданы папка layouts / meta / partials, в папке layouts лежат базовые layouts проекта. В папке meta есть 2 файла
mixin.jade, в котором хранятся миксины, например, такие

<img src="http://blinnikovbogdan.ru/QSTemplate/images/jade-mixins.png" alt="" style="max-width: 100%">

и variables.jade , в котором хранятся переменные. Страницы проекта по задумке создаются в корневом каталоге папки jade. Примером может служить файл index.jade. Папка partials предназначена для отдельных элементов страницы, которые дублируются на других страницах, например, навигация по сайту, хедер, футер или сайдбар.

Так же в релизе 1.1 была добавлена Svg библиотека для svg миксинов. Основная идея библиотеки заключается в том, чтобы вставлять svg изображения
тегом svg и при этом оставлять наш код читаемым, хочу заметить, что такой подход я рекомендую если с html кодом, в дальнейшем, никто из других
разработчиков не будет, а работа будет осуществляться только через jade препроцессор.

Т.е. я предлагаю вместо

<img src="http://blinnikovbogdan.ru/QSTemplate/images/jade-svg.png" alt="" style="max-width: 100%">

Использовать это

<img src="http://blinnikovbogdan.ru/QSTemplate/images/jade-svg-mixin.png" alt="" style="max-width: 100%">

Хороший пример как это использовать можно посмотреть <a href="https://github.com/bonkalol/blinnikov-jade-sass/">здесь</a>.
Сам <a href="https://github.com/bonkalol/blinnikov-jade-sass/blob/master/dev/jade/meta/svg.jade">svg-library</a> и как он используется
<a href="https://github.com/bonkalol/blinnikov-jade-sass/blob/master/dev/jade/index.jade">здесь</a>.


----------

Production

<img src="http://blinnikovbogdan.ru/QSTemplate/images/production-tree.png" alt="" style="max-width: 100%">

Ну тут я думаю все понятно, CSS / JS / Images , точнее их production версии, то есть scss скомпилированный в CSS, ужатый и собранный в один файл JS
Jade скомпилированный в HTML, и минифицированные картинки.

### Немного о gulpfile.js

В gulp включены следующие таски

	// load tasks
	gulp = require('gulp'),
	sass = require('gulp-ruby-sass'),
	jade = require('gulp-jade'),
	watch = require('gulp-watch'),
	autoprefixer = require('gulp-autoprefixer'),
	copy = require('gulp-copy'),
	concat = require('gulp-concat'),
	uglify = require('gulp-uglifyjs'),
	jshint = require('gulp-jshint'),
	stylish = require('jshint-stylish'),
	imagemin = require('gulp-imagemin'),
	pngquant = require('imagemin-pngquant'),
	spritesmith = require('gulp.spritesmith'),
	colors = require('colors'),
	browserSync = require('browser-sync'),
	reload = browserSync.reload;

----------

### gulp start

Gulp старт запустит browserSync и gulp watch.

### Concat

Js Concat , сначала подключается jquery, потом third-party скрипты, а потом только наш main.js
в котором находится написанный нами код

<img src="http://blinnikovbogdan.ru/QSTemplate/images/gulp-concat.png" alt="" style="max-width: 100%;">

### SASS Таск

В Sass таск уже интегрирован CSS Autoprefixer. Вы можете выставить браузеры под какие надо добавлять префиксы и забыть про то, что такое префиксы.
Так же можно изменить стиль исходного CSS.

<img src="http://blinnikovbogdan.ru/QSTemplate/images/gulp-sass.png" alt="" style="max-width: 100%">

### Sprite

Будут браться все .png файлы из dev/img/sprite/ , собираться в один файл production/img/sprite.png и создавать на основе dev/scss/project/_sprite.scss

----------

### Release 1.2.0

- Добавлен browserSync
- Добавлена нормальная обработка jade/sass ошибок
- При сейве js файлов теперь вызывается jshint и сканит все файлы
- В базовые конфиги добавлены некоторые переменные

### Release 1.1.0

- Добавлена зависимость gulp.spritesmith в devDepend , теперь после npm install вам не придется писать npm install gulp.spritesmith.
- Багфиксинг gulpfile.js.
- Добавлена svg.lib.jade для хранения миксинов svg файлов.

----------

Readme created 02.11.2014 : 20-47
По всем вопросам: <a href="http://blinnikovbogdan.ru/#social">Связывайтесь со мной</a> или пишите мне <a href="mailto:bonkalol@list.ru?subject=QSTemplate">bonkalol@list.ru</a>