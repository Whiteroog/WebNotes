# [Конспект «Основы JavaScript»](https://htmlacademy.ru/courses/343/run/17)

Подключают скрипт обычно в самом конце страницы, перед закрывающим тегом `</body>`.

```html
<script src="адрес_файла">
	...
</script>
```

Комментарии

```js
// Однострочные комментарии.

/*
И многострочные.
Они могут отключить сразу несколько строк кода.
*/
```

Поиск элемента на странице по селектору

```js
document.querySelector('селектор');
```

Вывод в консоль

```js
console.log('Привет от JavaScript!');
// Выведет: Привет от JavaScript!

console.log(document.querySelector('.page'));
// Выведет в консоль найденный элемент
```

Переменная

```js
let header = document.querySelector('header');
```

Убрать у элемента класс

```js
элемент.classList.remove('класс');
```

Добавить элементу класс

```js
элемент.classList.add('класс');
```

Метод-переключатель, убирает у элемента указанный класс, если он есть, и добавляет, если этого класса нет

```js
элемент.classList.toggle('класс');
```

Чтение полей ввода

```js
let input = document.querySelector('input');
paragraph.textContent = input.value;
```

Конкатенация

```js
let name = 'Кекс';
paragraph.textContent = 'Вас зовут ' + name + '. Хорошего дня!';
```

Обработчики событий onclick и onsubmit

```js
let button = document.querySelector('button');
button.onclick = function() {
  console.log('Кнопка нажата!');
};

let form = document.querySelector('form');
form.onsubmit = function() {
  console.log('Форма отправлена!');
};
```

