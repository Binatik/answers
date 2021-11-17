# Что такое контекст и как им управлять. 
> Контекст есть только у объектов, но обратите внимания, что все окружение javaScript  построены на них. 
- Изначально контекст, например в функции - это глобальный объект `window` 

```js 
const windowthis = this; 
//Window {window: Window, self: Window, document: document, name: '', location: Location, …} 
``` 
- Контекстом можно считать ключ, который идет до точки.   

```js 
const shop = {
  vegetable: {},
  fruit: {},
  getPrice(price) {
    //shop.fruit > this = shop;
    return { ...this, fruit: price };
  },
}; 
``` 
> До точки у нас shop, именно он и есть контекст. 

___ 
Вы можете изменить контекст программы используя встроенные функции javaScript.   
`bind()` `apply()` `call()` 
Возьмем код, что выше, но изменим контекст. 
```js 
{ ...this.getPrice.bind(this.fruit), fruit: price}; 

//https://gist.github.com/Binatik/f17994f2d8f3172fc4321bfe0604cb65
```