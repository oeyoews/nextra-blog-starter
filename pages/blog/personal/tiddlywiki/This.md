## JavaScript this 关键字

### 面向对象语言中 this 表示当前对象的一个引用。

但在 JavaScript 中 this 不是固定不变的，它会随着执行环境的改变而改变。

在方法中，this 表示该方法所属的对象。
如果单独使用，this 表示全局对象。
在函数中，this 表示全局对象。
在函数中，在严格模式下，this 是未定义的(undefined)。
在事件中，this 表示接收事件的元素。
类似 call() 和 apply() 方法可以将 this 引用到任何对象。

JavaScript中的this关键字是一个指向当前执行上下文的引用，它的值取决于函数的调用方式。this关键字可以用于访问当前对象的属性和方法，也可以用于创建新的对象。

在JavaScript中，this关键字的值取决于函数的调用方式。当函数被作为方法调用时，this关键字会指向调用该方法的对象。例如：

```javascript
var person = {
  firstName: "John",
  lastName : "Doe",
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};

console.log(person.fullName()); // 输出 "John Doe"
```

在这个例子中，我们定义了一个名为person的对象，该对象包含了firstName、lastName和fullName三个属性。fullName属性是一个函数，用于返回person对象的完整姓名。当我们调用person.fullName()方法时，this关键字会指向person对象，因此函数中的this.firstName和this.lastName都会返回person对象的属性值。

当函数不作为对象的方法调用时，this关键字会指向全局对象。例如：

```javascript
function myFunction() {
  return this;
}

console.log(myFunction()); // 输出全局对象
```

在这个例子中，我们定义了一个名为myFunction的函数，该函数没有被任何对象调用。当我们调用myFunction()函数时，this关键字会指向全局对象，因此函数中的this将返回全局对象。

除了作为方法调用和全局调用之外，this关键字还可以用于构造函数和事件处理程序等场景。在构造函数中，this关键字用于创建新的对象。例如：

```javascript
function Person(firstName, lastName) {
  this.firstName = firstName;
  this.lastName = lastName;
  this.fullName = function() {
    return this.firstName + " " + this.lastName;
  }
}

var person = new Person("John", "Doe");
console.log(person.fullName()); // 输出 "John Doe"
```

在这个例子中，我们定义了一个名为Person的构造函数，用于创建具有firstName和lastName属性的Person对象。当我们使用new关键字调用Person构造函数时，this关键字会指向新创建的Person对象，因此函数中的this.firstName和this.lastName都会被设置为新创建的对象的属性值。

总之，JavaScript中的this关键字是一个非常重要的概念，它的值取决于函数的调用方式，可以用于访问当前对象的属性和方法，也可以用于创建新的对象。在不同的场景中，需要根据具体情况来使用this关键字，以确保程序的正确性和可维护性。

在JavaScript中，事件处理程序中的this关键字通常指向触发事件的元素。例如，当用户点击一个按钮时，按钮的click事件处理程序中的this关键字将指向该按钮元素。

举个例子：

```html
<button id="myButton">点击我</button>

<script>
document.getElementById("myButton").addEventListener("click", function() {
  console.log(this); // 输出按钮元素
});
</script>
```

在这个例子中，我们使用addEventListener()方法将一个click事件处理程序绑定到按钮元素上。当用户点击按钮时，该事件处理程序将被触发，此时this关键字将指向按钮元素，因此在函数中输出this将返回按钮元素。

需要注意的是，如果事件处理程序使用箭头函数定义，则this关键字将不指向当前元素，而是指向定义该函数时的执行上下文。例如：

```html
<button id="myButton">点击我</button>

<script>
document.getElementById("myButton").addEventListener("click", () => {
  console.log(this); // 输出全局对象
});
</script>
```

在这个例子中，我们使用箭头函数定义click事件处理程序。由于箭头函数没有自己的this值，因此在事件处理程序中使用箭头函数定义时，this关键字将不指向当前元素，而是指向定义该函数时的执行上下文。在这个例子中，事件处理程序中的this关键字将指向全局对象，因此在函数中输出this将返回全局对象。

如果需要在事件处理程序中访问当前元素，可以使用event.target属性来获取当前触发事件的元素。例如：

```html
<button id="myButton">点击我</button>

<script>
document.getElementById("myButton").addEventListener("click", function(event) {
  console.log(event.target); // 输出按钮元素
});
</script>
```

在这个例子中，我们在click事件处理程序中使用event.target属性来获取当前触发事件的元素，因此在函数中输出event.target将返回按钮元素。

总之，事件处理程序中的this关键字通常指向触发事件的元素，但如果使用箭头函数定义事件处理程序，则this关键字将指向定义该函数时的执行上下文。如果需要在事件处理程序中访问当前元素，可以使用event.target属性来获取当前触发事件的元素。