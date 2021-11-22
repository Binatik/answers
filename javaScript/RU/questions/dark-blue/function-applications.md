# Зачем нужны функции.  
> Часто используется для предотвращения дублирования кода и мостом для передачи результата между областью видимости. 
```js  
Управлять функциями на много проще если владеть правилами. 
```
```js  
function setList() {
  const list = [1, 2, 3, 4, 5];
  const position = 3;
  return list[position - 1];
}
setList(); //вызов функции 

//https://gist.github.com/Binatik/c4628257970f7ceb464d30a47059ea88
``` 
- `return` служит для получения результата и выхода из блока функции.
- - Результат пишется после  `return` 
- - - Вызов функции - это получение `результата` 
___
- `()` - вызов функции, `без скобок` - это переменная которая хранит код функции или ссылку на функцию. 
```js   
//В данном варианте мы храним ссылку на функцию и не вызываем ее.
const functionLink = setList;  
`ƒ setList() {
  const list = [1, 2, 3, 4, 5];
  const position = 3;
  return list[position - 1];
}`
```
###### В этом разделе не рассматривается передача аргументов.