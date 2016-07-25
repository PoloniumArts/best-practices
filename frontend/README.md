# Frontend

Рекомендации Frontend-разработчикам.

## Инструменты

### Сборщики проектов (Task Runner)

Менеджеры задач очень сильно облегчаются выполнение рутинной работы при создание проекта. Сейчас можно выделить два наиболее известных менеджера:
* [Gulp](http://gulpjs.com/)
* [Grunt](http://gulpjs.com/)

В новых проектах рекомендуется использовать Gulp, т.к. данный момент ведется активная разработка проекта, написано достаточное количество плагинов под задачи для популярных инструментов. Плюс сам процесс сборки проекта Gulp'ом примерно в 2,5 раза быстрее Grunt'a.

### Шаблонизаторы

Шаблонизаторы — это именно то средство, которое предоставляет вам возможность написания разметки совершенно по новому, с целым рядом преимуществ по сравнению с обычным HTML.

* [Jade](http://jade-lang.com/)
* [Pug](https://github.com/pugjs/pug)

Pug это вторая версия Jade, котрый изменил навазние из-за того что Jade является зарегистрированной торговой маркой. Так как проект новый, то остальные могут быть проблемы совместимости с другими инстументами и некоторым функционалом.
На текущий момент в проектах рекомендуется использовать Jade, как более стабильную версию и поддерживаемую версию. В дальнейшем возможен переход на Pug.

### Препроцессоры

* [Stylus](http://learnboost.github.com/stylus/)
* [Less](http://lesscss.org/)
* [Sass](http://sass-lang.com/)

В проектах рекомендуется использовать Stylus, как один самых развивающихся и гибких препроцессоров.

### Тестирование

* End-to-end tests ([Protractor](https://github.com/angular/protractor))
* Unit tests ([karma](https://karma-runner.github.io/))

### Язык программирования

На текущий момент существует несколько высокоуровневых языков программирования, которые компилируются в JavaScript

* [ECMAScript 6](http://es6-features.org/)
* [CoffeeScript](http://coffeescript.org/)
* [TypeScript](https://www.typescriptlang.org/)

В проектах рекомендуется использовать ECMAScript 6, как следующую версию стандарта JavaScript, поддержка которого обязательна для всех актуальных версий браузеров.

## Генераторы

Для облегчение сборки всех этих замечательных инстументов в одном проекте можно использовать сервис [yeoman](http://yeoman.io/).
В качестве базового каркаса проекта с ангуляром можно воспльзоваться вот этим [генератором](https://github.com/swiip/generator-gulp-angular#readme)
Для статических сайтов подойдет [generator-yeogurt](https://github.com/larsonjj/generator-yeogurt)

# Coding guides

## JavaScript coding guide

Это краткие рекомендации по написанию JS кода. Полный набор можно посмотреть тут [AngularJS style guide](https://github.com/johnpapa/angular-styleguide).


### Соглашения об именовании

- Везде (свойства и методы) используйте `camelCase`, за исключением:
  * В имена классов и конструкторов должен использоваться `PascalCase`
  * Константы должны быть все в UPPERCASE, например `var MY_CONSTANT = 0;`
- Имена файлов всегда должны быть в `kebab-case` (строчными словами, разделенными `-`).

### Правила написание кода

- Используйте одинарные ковычки `'` для строк
- Поряд подключения зависимостей: от основных файлов (фреймоворки, внешние библиотеки) к более конкретным (модули проекта)
- Используйте префикс `_` для имен внутренних переменных
- Всегда используйте строгие проверки равенства: `===` и `!==` вместо `==` or `!=` чтобы избежать ошибок сравнения (смотрите [JavaScipt equality table](https://dorey.github.io/JavaScript-Equality-Table/))
- Используйте `[]` вместо `Array`


## CSS coding guide

### Соглашения об именовании

- В CSS все должно быть названо в `kebab-case` (строчными словами, разделенными `-`).
- Имена файлов всегда должны быть в `kebab-case`
- Следуйте методологии [BEM](https://en.bem.info/tools/bem/bem-naming/)

### Правила написание кода

- Используйте одинарные ковычки `'` для строк
- Следите за областью видимости своих стилей:
  * Разделяйте **глобальные** стили (например *фреймворков*) и стили **модулей**
  * Глобальный стили должны быть расположены в `main/theme/*` или `main/helpers.styl` (никогда в модулях)
  * Избегайте использования более общих селекторы, чем это необходимо (всегда использовать классы!)

### Ошибки

- Никога не используйте слово `!important`.
- Никогда не используйте **inline** стили в html, даже *для отдадки* (потому что когда нибудь это да окажется в вашем коммите)
- Не следует использовать префиксы для разных браузеров: с этим справится ([autoprefixer](https://github.com/postcss/autoprefixer))

## HTML coding guide

### Соглашения об именовании

- Все должно быть названо в `kebab-case` (строчными словами, разделенными `-`): тэги, атрибуты, IDs, и т.д
- Не нужно испозовать `data-` префикс для angular директив, не стесняйстесь использовать собственные элементы ((да, на данный момент это не будет совместимо с W3C валидатором ))
- Имена файлов всегда должны быть в `kebab-case`

### Правила написание кода

- Используйте HTML5 doctype: `<!doctype html>`
- Используйте HTML семантику в соответствии с ее назначением
- Используйте двойные кавычки `"` вокруг значений атрибутов
- Используйте новую строку для каждого блока, списка или строки таблицы
- Разделяйте струтктуру (HTML) от презентации (CSS) и от поведения (JavaScript):
  * Не используйте встроенные стили CSS или JavaScript
- атрибут `type` для stylesheets и script тэгов могут быть опущены
- Используте валидный HTML по возможности

### Ошибки

- **Блочный** тэги не могут быть вложены в **inline** тэги: например `<div>` не должен быть внутри `<span>`