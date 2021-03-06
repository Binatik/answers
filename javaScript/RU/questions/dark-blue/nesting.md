# Что такое область видимости. 
Это уровень абстракций для которых будут доступны переменные/данные.
___
> Отвечает за видимость переменных как `{блок{блок}}`  

Допустим у нас есть 5 уровней вложенности. 
```js   
//Первая вложенность - глобальная. 

{ 2 Вложенность.
  { 3 Вложенность.
    { 4 Вложенность.
      { 5 Вложенность.
      }
    }
  }
}
``` 
###### Представим что в примере выше, числа - это инициализированные переменные. 
Мы будем двигаться в порядке очереди вверх начиная с пятой вложенности. 
 
```js  
Пятая вложенность позволяет получить такие переменные(5,4,3,2,1)
``` 
```js  
Четвертая вложенность позволяет получить такие переменные(4,3,2,1) и получить ошибку переменных(5)
``` 
```js  
Третья вложенность позволяет получить такие переменные(3,2,1) и получить ошибку переменных(5,4)
``` 
```js  
Вторая вложенность позволяет получить такие переменные(2,1) и получить ошибку переменных(5,4,3)
``` 
```js  
Первая вложенность позволяет получить такие переменные(1) и получить ошибку переменных(5,4,3,2)
```

```js 
const globalVar = 'Это глобальная переменная. Про localVarTwo и localVar она не знает.';
{
  const localVar = 'Это локальная переменная. Про localVarTwo она не знает.';
  {
    const localVarTwo =
      'Это локальная переменная еще ниже. localVar и globalVar для нее виден.';
  }
}   

//https://gist.github.com/Binatik/e8584180fe49a3e7e6679a7fdca94a07
``` 
- Когда мы погружаемся через `{local}` - мы можем представить для удобства - предыдущая на уровне выше `{global}`. 

> Локальную переменную в отличии от глобальной нельзя получить в глобальной области.