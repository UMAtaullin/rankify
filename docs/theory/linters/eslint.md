npm install -D eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin

### Разбор конфигурации ESLint

```json
{
	"root": true,
	"parser": "@typescript-eslint/parser",
	"plugins": [
		"@typescript-eslint"
	],
	"rules": {
		"semi": "off",
		"@typescript-eslint/semi": [
			"warn"
		],
		"@typescript-eslint/no-empty-interface": [
			"error",
			{
				"allowSingleExtends": true
			}
		]
	},
	"extends": [
		"eslint:recommended",
		"plugin:@typescript-eslint/eslint-recommended",
		"plugin:@typescript-eslint/recommended"
	]
}
```

#### Пояснение параметров

1. **`root`**: Указывает, что это корневая конфигурация ESLint. Это предотвращает поиск конфигураций в родительских директориях.

2. **`parser`**: Указывает парсер, который будет использоваться для анализа кода. Здесь используется `@typescript-eslint/parser`, который позволяет ESLint понимать синтаксис TypeScript.

3. **`plugins`**: Указывает плагины, которые будут использоваться. В данном случае это плагин для TypeScript.

4. **`rules`**: Определяет правила линтинга:
   - **`semi`**: Отключает проверку на наличие точек с запятой в конце строк.
   - **`@typescript-eslint/semi`**: Включает предупреждение для точек с запятой (если они отсутствуют).
   - **`@typescript-eslint/no-empty-interface`**: Запрещает создание пустых интерфейсов, за исключением случаев, когда они наследуются от других интерфейсов.

5. **`extends`**: Указывает базовые конфигурации, от которых наследуется данная конфигурация:
   - **`eslint:recommended`**: Включает рекомендуемые правила ESLint.
   - **`plugin:@typescript-eslint/eslint-recommended`** и **`plugin:@typescript-eslint/recommended`**: Включают рекомендуемые правила для TypeScript.

### Нужны ли точки с запятой в коде TypeScript?

Ответ на вопрос о необходимости точек с запятой в TypeScript зависит от ваших предпочтений и стиля кодирования:

- **С точки зрения синтаксиса TypeScript**: Точки с запятой не являются обязательными, так как JavaScript (и, следовательно, TypeScript) поддерживает автоматическую вставку точек с запятой (ASI). Однако это может привести к неожиданным ошибкам в некоторых случаях.
  
- **С точки зрения стиля кодирования**: Многие разработчики предпочитают использовать точки с запятой для повышения читаемости и предотвращения потенциальных проблем, связанных с ASI. Это также может быть частью ваших правил линтинга.

В вашей конфигурации указано, что правило `semi` отключено, а `@typescript-eslint/semi` настроено на предупреждение. Это означает, что вы можете писать код без точек с запятой, но если вы их не используете, ESLint будет выдавать предупреждения.

### Заключение

Конфигурация ESLint позволяет настроить линтинг кода на TypeScript в соответствии с вашими предпочтениями. Использование или отсутствие точек с запятой — это вопрос стиля и предпочтений команды разработчиков.

Citations:
[1] https://bestcode.su/frontend/ispolzovanie-eslint-i-prettier-v-proekte-typescript/
[2] https://dzen.ru/a/YvVYg1jINGLkOgtz
[3] https://gitverse.ru/blog/articles/development/344-eslint-kak-uluchshit-kachestvo-koda-javascript-i-typescript
[4] https://tproger.ru/translations/setting-up-eslint-and-prettier
[5] https://www.youtube.com/watch?v=MvnTwjAjhic
[6] https://dzen.ru/a/Y5jzAPuekSzUldIU