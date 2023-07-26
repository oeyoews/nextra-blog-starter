箭头函数确实不支持 `arguments` 对象。在传统的函数定义中，`arguments` 对象是一个类数组对象，包含了函数被调用时传递的所有参数。但是，在箭头函数中，没有自己的 `arguments` 对象。

箭头函数的参数列表是固定的，无法通过 `arguments` 对象访问传递给函数的参数。相反，箭头函数可以通过使用剩余参数语法（`...args`）来接收任意数量的参数，并将它们作为数组访问。

下面是一个示例，展示了箭头函数和传统函数在处理参数上的区别：

```javascript
// 传统函数
function traditionalFunction() {
  console.log(arguments); // 输出函数的参数列表
}

traditionalFunction(1, 2, 3); // 输出 [1, 2, 3]

// 箭头函数
const arrowFunction = (...args) => {
  console.log(args); // 输出函数的参数列表作为数组
};

arrowFunction(1, 2, 3); // 输出 [1, 2, 3]
```

所以，如果你需要在函数中使用 `arguments` 对象来访问参数列表，应该使用传统的函数定义而不是箭头函数。