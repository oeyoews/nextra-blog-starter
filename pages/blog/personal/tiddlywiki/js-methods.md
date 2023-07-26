以下是 JavaScript 中需要掌握的高频方法：

1. DOM操作：获取、创建、修改、删除DOM元素
2. 事件处理：绑定、解绑事件、事件冒泡、阻止默认事件
3. 数组操作：遍历、筛选、排序、去重、合并、转换等
4. 字符串处理：截取、拼接、替换、正则匹配等
5. Ajax请求：发送、接收、处理请求结果等
6. 函数操作：声明、调用、参数传递、闭包、高阶函数等
7. 异常处理：try-catch语句、抛出异常等
8. 定时器：setTimeout、setInterval等
9. JSON操作：解析、转换、序列化等
10. 模块化：使用模块化规范、模块的导入和导出等。

1. DOM操作：

获取元素：

```
let element = document.querySelector('#id');
let elements = document.querySelectorAll('.class');
```

创建元素：

```
let element = document.createElement('div');
```

修改元素：

```
element.innerHTML = 'new content';
element.setAttribute('class', 'newClass');
```

删除元素：

```
element.parentNode.removeChild(element);
```

2. 事件处理：

绑定事件：

```
element.addEventListener('click', function(event){
  // 点击事件处理逻辑
});
```

解绑事件：

```
element.removeEventListener('click', function(event){
  // 点击事件处理逻辑
});
```

阻止默认事件：

```
event.preventDefault();
```

3. 数组操作：

遍历数组：

```
let arr = [1, 2, 3];
arr.forEach(function(item){
  console.log(item);
});
```

筛选数组：

```
let arr = [1, 2, 3];
let newArr = arr.filter(function(item){
  return item > 1;
});
```

排序数组：

```
let arr = [3, 1, 2];
arr.sort(function(a, b){
  return a - b;
});
```

去重数组：

```
let arr = [1, 2, 3, 2, 1];
let newArr = Array.from(new Set(arr));
```

4. 字符串处理：

截取字符串：

```
let str = 'hello world';
let newStr = str.slice(0, 5);
```

拼接字符串：

```
let str1 = 'hello';
let str2 = 'world';
let newStr = str1 + ' ' + str2;
```

替换字符串：

```
let str = 'hello world';
let newStr = str.replace('world', 'javascript');
```

正则匹配：

```
let str = 'hello world';
let reg = /world/;
let result = reg.test(str);
```

5. Ajax请求：

发送请求：

```
let xhr = new XMLHttpRequest();
xhr.open('GET', 'url');
xhr.send();
```

接收处理请求结果：

```
xhr.onload = function(){
  console.log(xhr.responseText);
};
```

6. 函数操作：

声明函数：

```
function add(a, b){
  return a + b;
}
```

调用函数：

```
let sum = add(1, 2);
```

参数传递：

```
function modifyObj(obj){
  obj.name = 'new name';
}

let obj = {name: 'old name'};
modifyObj(obj);
console.log(obj.name); // 输出 'new name'
```

闭包：

```
function createCounter(){
  let count = 0;
  return function(){
    count++;
    console.log(count);
  };
}

let counter = createCounter();
counter(); // 输出 1
counter(); // 输出 2
```

高阶函数：

```
function add(a, b){
  return a + b;
}

function calculate(func, a, b){
  return func(a, b);
}

let sum = calculate(add, 1, 2);
```

7. 异常处理：

```
try {
  // 可能出现异常的代码
} catch(error) {
  // 异常处理逻辑
}
```

抛出异常：

```
throw new Error('error message');
```

8. 定时器：

```
let timer = setTimeout(function(){
  console.log('timer');
}, 1000);

clearTimeout(timer);
```

9. JSON操作：

解析JSON：

```
let str = '{"name": "alice", "age": 18}';
let obj = JSON.parse(str);
```

序列化JSON：

```
let obj = {name: 'alice', age: 18};
let str = JSON.stringify(obj);
```

10. 模块化：

导入模块：

```
import {add} from './module';
```

导出模块：

```
export function add(a, b){
  return a + b;
}
```

11. Promise

Promise是一种异步编程的解决方案，它可以用来解决回调地狱的问题，提高代码的可读性和可维护性。

创建Promise对象：

```
let promise = new Promise(function(resolve, reject){
  // 异步操作
  if(/* 操作成功 */){
    resolve(result);
  }else{
    reject(error);
  }
});
```

使用then方法处理Promise：

```
promise.then(function(result){
  // 操作成功的处理逻辑
}, function(error){
  // 操作失败的处理逻辑
});
```

使用catch方法处理Promise：

```
promise.catch(function(error){
  // 操作失败的处理逻辑
});
```

12. async/await

async/await是ES2017中新增的异步编程解决方案，它基于Promise实现，可以进一步简化异步代码的编写。

使用async声明异步函数：

```
async function fetchData(){
  // 异步操作
  return result;
}
```

使用await等待异步操作完成：

```
let result = await fetchData();
```

使用try-catch处理异步操作的异常：

```
try{
  let result = await fetchData();
}catch(error){
  // 异常处理逻辑
}
```

13. ES6中的新特性

ES6是JavaScript中一个重要的版本，它引入了许多新的特性，包括箭头函数、模板字符串、解构赋值、let/const关键字、类、模块化等等。

箭头函数：

```
let add = (a, b) => a + b;
```

模板字符串：

```
let name = 'alice';
let str = `hello ${name}`;
```

解构赋值：

```
let [a, b] = [1, 2];
```

let/const关键字：

```
let name = 'alice';
const PI = 3.14;
```

类：

```
class Person{
  constructor(name){
    this.name = name;
  }

  sayHello(){
    console.log(`hello ${this.name}`);
  }
}

let person = new Person('alice');
person.sayHello();
```

模块化：

```
export function add(a, b){
  return a + b;
}

import {add} from './module';
```

1. 数组的常用方法：`push`、`pop`、`shift`、`unshift`、`slice`、`splice`、`concat`、`join`、`map`、`reduce`、`filter`、`sort`、`reverse` 等。

2. 对象的常用方法：`Object.keys`、`Object.values`、`Object.entries`、`Object.assign`、`JSON.stringify`、`JSON.parse` 等。

3. 字符串的常用方法：`charAt`、`charCodeAt`、`indexOf`、`lastIndexOf`、`substr`、`substring`、`slice`、`split`、`replace`、`match` 等。

4. 函数的常用方法：`bind`、`call`、`apply`、`setTimeout`、`setInterval`、`Promise`、`async/await`、`try/catch` 等。

5. DOM 操作的常用方法：`getElementById`、`querySelector`、`querySelectorAll`、`createElement`、`appendChild`、`removeChild`、`setAttribute`、`getAttribute`、`classList` 等。

6. 事件的常用方法：`addEventListener`、`removeEventListener`、`preventDefault`、`stopPropagation` 等。

7. 正则表达式的常用方法：`test`、`exec`、`match`、`replace`、`search` 等。

8. 数学计算的常用方法：`Math.round`、`Math.ceil`、`Math.floor`、`Math.abs`、`Math.max`、`Math.min`、`Math.random` 等。

以上是 JavaScript 中需要掌握的高频方法，掌握这些方法可以提高编码效率，同时也有助于更好地理解 JavaScript 的语法和运行机制。
