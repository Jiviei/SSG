### **Docusaurus** 

-  Простые ссылки

   -  Gramax оборачивает ссылки в `<>` из-за этого **docusaurus** выбивает ошибку.

   -  Решение:

      удалить `<>`

-  Ссылки типа `[текст ссылки](url)`

   -  Если url пустой, то **docusaurus** выбивает ошибку

   -  Решение:

      Обозначить его как `/` -- в Markdown синтаксис `[текст ссылки]()` ~~эквивалентен~~ `[текст ссылки](/)`

-  Фигурные скобки

   -  Если в фигурных скобка несколько слов, то **docusaurus** выбивает ошибку

   -  Решение:

      экранировать скобки: {несколько слов текста} => \\{несколько слов текста\\}

Скопировал каталог `gramax-board` 

Добавил в `docusaurus.config.js` плагин и элемент в навигации

```
const config = {
...
  plugins: [
    [
      '@docusaurus/plugin-content-docs',
      {
        id: 'gramax-board',
        path: 'gramax-board',
        routeBasePath: 'gramax-board',
      },
    ],
  ],
...
themeConfig:
...
      navbar: {
...
        items: [
...
          {to: '/gramax-board', label: 'Gramax Board', position: 'left'},
...
```
