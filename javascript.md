# [Конспект «Основы JavaScript»](https://htmlacademy.ru/courses/343/run/17)

### Комментарии

```js
// Однострочные комментарии.

/*
И многострочные.
Они могут отключить сразу несколько строк кода.
*/
```

### Поиск элемента на странице по селектору

```js
document.querySelector('селектор');
```

### Вывод на консоль

```js
console.log('Привет от JavaScript!');
// Выведет: Привет от JavaScript!

console.log(document.querySelector('.page'));
// Выведет в консоль найденный элемент
```

### Переменная

```js
let header = document.querySelector('header');
```

### Убрать у элемента класс

```js
элемент.classList.remove('класс');
```

### Добавить элементу класс

```js
элемент.classList.add('класс');
```

### Метод-переключатель

убирает у элемента указанный класс, если он есть, и добавляет, если этого класса нет

```js
элемент.classList.toggle('класс');
```

### Свойство textContent

Свойство `textContent` хранит в себе текстовое содержимое элемента.

```js
let paragraph = document.querySelector('p');
paragraph.textContent = 'Здесь был Кекс. Мяу!';
```

### Чтение полей ввода

У полей ввода есть особое свойство — `value`. Оно хранит данные, введённые в поле.

```js
let input = document.querySelector('input');
paragraph.textContent = input.value;
```

### Конкатенация

```js
let name = 'Кекс';
paragraph.textContent = 'Вас зовут ' + name + '. Хорошего дня!';
```

### Обработчики событий onclick и onsubmit

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

# [Конспект «Условия и создание элементов»](https://htmlacademy.ru/courses/347/run/15)

### Подключение на страницу скрипты

```html
<body>
	...
  <script src="themes.js"></script>
  <script src="likes.js"></script>
</body>
```

### Числа

```js
let number = 0;

// Полная запись
number = number + 2; // Значение переменной: 2
number = number - 2; // Значение переменной: 0

// Краткая запись
number += 2; // Значение переменной: 2
number -= 2; // Значение переменной: 0

// Увеличение числа на 1
number++; // Значение переменной: 1

// Уменьшение числа на 1
number--; // Значение переменной: 0
```

### Метод classList.contains (проверяет, есть ли у элемента класс)

```js
элемент.classList.contains('класс');
```

### Условная конструкция

```js
if (условие) {
  // Инструкции, которые выполнятся, если условие истинно
} else {
  // Инструкции, которые выполнятся, если условие ложно
}
```

### Метод append

<!--
	??? Что он делает
-->

```js
элемент-родитель.append(добавляемый-элемент);
```

### Метод createElement

```js
document.createElement('имя тега');
```

Чтобы создать новый элемент на странице, к которой подключён скрипт, нужно использовать слово document. Внутри скобок в кавычках указывают элемент, который нужно создать. Например:

```js
// Создаём новый элемент <div> и записываем его в переменную
let newElement = document.createElement('div');
```

Новый элемент будет доступен из скрипта, но в разметке не появится, пока мы не скажем JavaScript, где разместить новый элемент. Для этого можно использовать метод append:

```js
// Находим элемент-родитель
let parent = document.querySelector('.parent');

// Добавляем новый элемент на страницу
parent.append(newElement);
```

### Очищаем поле ввода

```js
let input = document.querySelector('input');
input.value = '';
```

# [Конспект «Коллекции и свойства элементов»](https://htmlacademy.ru/courses/349/run/16)

### Метод querySelectorAll (найти все данные элементы)

```js
// Найдёт все абзацы на странице
let elements = document.querySelectorAll('p');
```

### Коллекция

```js
// Выведет коллекцию в консоль
console.log(elements);

console.log(elements[0]); // Выведет первый элемент коллекции
console.log(elements[1]); // Выведет второй элемент коллекции
```

### Data-атрибуты

В HTML можно создавать свои собственные атрибуты. Имена таких атрибутов начинаются с префикса `data-`, после которого идёт любое выбранное разработчиком слово.

```html
<div data-cat-name="Кекс">
```

Чтобы получить значение data-атрибута в JavaScript, используют свойство `dataset`, после которого указывают имя атрибута без префикса `data-`:

```js
элемент.dataset.имяАтрибутаБезПрефикса
```

Если имя атрибута состояло из нескольких слов и в нём были дефисы, то в JavaScript его записывают в «верблюжьем» стиле (по-английски camelCase): дефисы убирают, а каждое слово, кроме первого, пишут с большой буквы.

```js
let element = document.querySelector('div');
console.log(element.dataset.catName); // Выведет: Кекс
```

### Цикл for of

```js
let elements = document.querySelectorAll('p'); // Находим все абзацы

for (let element of elements) {  // Создаём цикл и переменную
  console.log(element);          // Выводим элементы в консоль
}
```

### Обработчик событий oninput

Обработчик событий `oninput` (в переводе с английского это означает «при вводе») позволяет выполнять инструкции из фигурных скобок каждый раз, когда меняется значение в поле ввода. Изменением считается и добавление, и удаление символов.

```js
// Найдём поле ввода
let textarea = document.querySelector('textarea');

// Добавим обработчик событий
textarea.oninput = function () {
  // Выведем данные из поля ввода
  console.log(textarea.value);
};
```

### Свойство length

```js
let text = 'Я люблю JavaScript';
console.log(text.length); // Выведет: 18

let textarea = document.querySelector('textarea');
console.log(textarea.value); // Выведет: Кекс
console.log(textarea.value.length); // Выведет: 4
```

### Оператор сравнения

```js
console.log(3 > 2); // Вернёт: true
```

### Свойство disabled

```js
let button = document.querySelector('button');

// Блокирует кнопку
button.disabled = true;

// Разблокирует кнопку
button.disabled = false;
```

