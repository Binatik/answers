# Замыкание функции.  
> Возвращаемая функция в функции, которая не вызывается в той функции и есть замыкания.
  
Помните о том, что когда мы не вызываем функции, мы передаем ссылку на функцию, некий код функции, как строка. 

```js 
function getLinkFunction() { 
  return function() { 
    //Мы не вызываем анонимную функцию.
  }
} 

const linkFunction = getLinkFunction(); 
``` 
- `linkFunction`  в примере выше содержит ссылку на анонимную функцию.   

- Мы можем сразу начать вызывать анонимную функцию.
```js 
const linkFunction = getLinkFunction()(); //Теперь это результат, который вернет анонимная функция.
``` 

```js 
function getLinksFunction(str) {
  return function () {
    return function (text) {
      return function () {
        return `Все анонимные ${text}, а как бы ${str}.`;
      };
    };
  };
}
``` 
- Можно вызывать не сразу, а по очереди.
```js 
const linkOneFunction = getLinksFunction('замыкаются');
const linkTwoFunction = linkOneFunction();
const linkThreeFunction = linkTwoFunction('функции не вызываются');
const result = linkThreeFunction(); 

//https://gist.github.com/Binatik/847d5973ebb3956797f3c090d2badd71
```