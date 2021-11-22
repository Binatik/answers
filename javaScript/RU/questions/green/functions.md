# Какие есть способы объявления функции.  
 
- Функция `Expression` - не имеет `hoisting` и объявляется как переменная. 
```js 
//Вызов функции выше инициализации невозможен; 
const getList = function () {
  return 'Лист';
}; 
``` 

- Функция `Declaration` - применяет `hoisting` и объявляется не как переменная. 
```js 
const status = getStatus(); //Ошибки не будет, применится hoisting. 

function getStatus() {
  return '404';
} 
``` 

- Функция `Стрелка` - не имеет `hoisting` и объявляется как переменная c некоторыми отличиями.  
```js 
const getAuth = () => true; // return в этом случае не используется.

const checkAuth = () => {
  if (getAuth()) return 'Авторизован';
};   