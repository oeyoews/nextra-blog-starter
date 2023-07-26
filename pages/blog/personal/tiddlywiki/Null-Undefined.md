- **null**表示一个空值或不存在的对象。当我们将变量初始化为null时，意味着它没有被赋予任何值。null是一个特殊的关键字，用于表示一个空的或无效的对象。例如，如果你有一个指向对象的变量，但是你想要明确地表示该对象为空，你可以将该变量设置为null。

  以下是一个示例：
  ```javascript
  let obj = null;
  console.log(obj); // 输出: null
  ```

- **undefined**表示一个未定义的值。当变量声明但没有被赋值时，它的默认值就是undefined。此外，如果你访问一个对象的属性或函数，而该对象本身未被定义，那么该属性或函数的值也将是undefined。

  以下是一些示例：
  ```javascript
  let x; // 声明一个变量但未赋值
  console.log(x); // 输出: undefined

  let obj; // 声明一个对象变量但未定义
  console.log(obj.property); // 输出: undefined
  ```

* 在总结上述区别时，可以将null视为已定义但空的值，而undefined表示未定义的值。

* null是一个表示“空”的对象，转为数值时为0；undefined是一个表示"此处无定义"的原始值，转为数值时为NaN。