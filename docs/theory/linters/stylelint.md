### Установка и настройка Stylelint

Stylelint — это мощный инструмент для линтинга CSS, SCSS и других стилей, который помогает поддерживать единый стиль кода и избегать ошибок. Вот пошаговая инструкция по его установке и настройке согласно лучшим практикам.

#### 1. Установка Stylelint

Для начала установите Stylelint как разработческую зависимость в вашем проекте:

```bash
npm install -D stylelint
```

Если вы работаете с SCSS или другими препроцессорами, вам могут понадобиться дополнительные пакеты:

```bash
npm install -D stylelint-config-standard stylelint-scss
```

- **`stylelint`**: основной линтер для стилей.
- **`stylelint-config-standard`**: стандартная конфигурация правил.
- **`stylelint-scss`**: плагин для поддержки SCSS.

#### 2. Создание конфигурационного файла

Создайте файл конфигурации для Stylelint. Это может быть `.stylelintrc.json`, `.stylelintrc.js`, или вы можете добавить настройки в `package.json`. Пример конфигурации в `.stylelintrc.json`:

```json
{
  "extends": "stylelint-config-standard",
  "rules": {
    "indentation": 2,
    "string-quotes": "single",
    "color-no-invalid-hex": true,
    "max-line-length": 80,
    "no-empty-source": true
  }
}
```

#### 3. Настройка скриптов в `package.json`

Добавьте скрипты для запуска Stylelint в вашем `package.json`:

```json
"scripts": {
  "lint:css": "stylelint '**/*.css'",
  "lint:scss": "stylelint '**/*.scss'",
  "lint:fix": "stylelint '**/*.css' --fix"
}
```

Теперь вы сможете запускать линтер с помощью команд:

```bash
npm run lint:css
npm run lint:scss
npm run lint:fix
```

#### 4. Интеграция с редактором кода

Для удобства разработки рекомендуется установить плагин Stylelint для вашего редактора кода (например, VSCode). После установки плагина настройте его, чтобы он работал с вашими файлами стилей.

В настройках VSCode добавьте следующие строки в `settings.json`:

```json
"css.validate": false,
"scss.validate": false,
"stylelint.validate": ["css", "scss"]
```

Это отключит встроенную проверку CSS и SCSS в VSCode и позволит использовать только Stylelint.

#### 5. Дополнительные плагины

В зависимости от ваших потребностей, вы можете установить дополнительные плагины для расширения функциональности Stylelint. Например:

- **`stylelint-order`**: для проверки порядка свойств в CSS.
- **`stylelint-prettier`**: интеграция с Prettier для форматирования кода.
- **`stylelint-config-prettier`**: отключает правила, конфликтующие с Prettier.

Установка дополнительных плагинов:

```bash
npm install -D stylelint-order stylelint-prettier stylelint-config-prettier
```

#### Заключение

Stylelint — это мощный инструмент для поддержания качества кода в проектах на CSS и SCSS. Следуя этим шагам, вы сможете установить и настроить его согласно лучшим практикам, что поможет вам избежать ошибок и поддерживать единый стиль кода в вашем проекте.

Citations:
[1] https://habr.com/ru/sandbox/175284/
[2] https://dopustim.gitbook.io/lintbook/docs/stylelint
[3] https://www.youtube.com/watch?v=_9RcU11mLc4
[4] https://kovtunos.pro/ru/code/stylelint-configuration/
[5] https://rutube.ru/video/680569d32582347e377acadf8aed4f43/
[6] https://bzvyagintsev.ru/blog/stylelint/
[7] https://dzen.ru/a/Z1mIr9iQ3kxhk-AI