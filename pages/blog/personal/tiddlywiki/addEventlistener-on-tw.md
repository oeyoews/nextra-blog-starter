window.addEventListener ==> $tw.wiki.addEventListener

`$tw.wiki.addEventListener` 和 `window.addEventListener` 都是 JavaScript 中添加事件监听器的方法，但它们的使用方式和作用域略有不同。

首先，`$tw.wiki.addEventListener` 是 TiddlyWiki 5 中特有的方法，用于在 wiki 中注册事件监听器，并对事件进行处理。这个方法可以被应用程序或插件调用，以便它们能够根据需要拦截和处理 wiki 中发生的一些事件，例如修改、保存、删除等。它的具体用法类似于标准的 `addEventListener` 方法，但参数不完全相同。

而 `window.addEventListener` 则是浏览器中常用的方法，用于向窗口对象（即 `window` 对象）注册事件监听器。通过在 window 上注册事件监听器，您可以捕捉浏览器的各种事件，如页面加载、鼠标点击、滚动等。这个方法被广泛用于创建交互式 Web 应用程序和网站。

总之，`$tw.wiki.addEventListener` 和 `window.addEventListener` 的主要区别在于它们所作用的范围不同：前者针对的是 TiddlyWiki 5 实例中的事件，后者则是针对整个浏览器窗口的事件。

`$tw.wiki.addEventListener` 和 `window.addEventListener` 的参数也有所不同。

`$tw.wiki.addEventListener` 方法的语法如下：

```javascript
$tw.wiki.addEventListener(type, listener, useCapture);
```

其中：

- `type`：必需。要注册的事件类型，例如 `"change"`、`"keydown"` 等。
- `listener`：必需。要调用的函数或处理程序。这个函数会在事件被触发时执行，并且会接收一个事件对象作为唯一的参数。
- `useCapture`：可选。布尔值，表示是否使用捕获模式。默认值为 `false`。

而 `window.addEventListener` 方法的语法如下：

```javascript
window.addEventListener(type, listener [, options]);
```

其中：

- `type`：必需。要注册的事件类型，例如 `"load"`、`"click"` 等。
- `listener`：必需。要调用的函数或处理程序。这个函数会在事件被触发时执行，并且会接收一个事件对象作为唯一的参数。
- `options`：可选。一个对象，包含以下属性：
  - `capture`：布尔值，表示是否使用捕获模式。默认为 `false`。
  - `once`：布尔值，表示是否只执行一次。默认为 `false`。
  - `passive`：布尔值，表示是否禁止使用事件监听器中的 `preventDefault()` 方法。默认为 `false`。

因此，可以看出 `$tw.wiki.addEventListener` 和 `window.addEventListener` 的参数用法有一些微妙的差别。两者均需要指定事件类型和事件处理程序，但 `window.addEventListener` 还可以传递选项参数。此外，`$tw.wiki.addEventListener` 的作用域是 TiddlyWiki 5 实例，而 `window.addEventListener` 的作用域是整个浏览器窗口。