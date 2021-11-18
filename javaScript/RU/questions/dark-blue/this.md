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
  fruit: {},
  getPrice(price) {
    //shop.fruit > this = shop;
    return { ...this, fruit: price };
  },
}; 
const thisShopFruitPrice = shop.getPrice(5);
``` 
> До точки у нас shop, именно он и есть контекст. 

___ 
Вы можете изменить контекст программы используя встроенные функции javaScript.    

- Возьмем код, `shop.getPrice(5);` но изменим контекст. 
```js 
shop.getPrice.bind(shop.fruit, 5)(); //bind - нужно вызывать; 
shop.getPrice.call(shop.fruit, 2); //call - не нужно вызывать;  
shop.getPrice.apply(shop.fruit, [2]); //apply - не нужно вызывать; 

//https://gist.github.com/Binatik/f17994f2d8f3172fc4321bfe0604cb65
```