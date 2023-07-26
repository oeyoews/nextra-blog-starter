`clipboard.js` 使用了浏览器自带的复制 API，而不是通过 JavaScript 直接操作剪贴板，可以避免一些安全问题。

在过去，网页通常使用 Flash 或 Java 等插件来实现复制操作，这些插件会通过 JavaScript 直接访问剪贴板，并将剪贴板中的内容复制到网页中。这种方式存在很多安全问题，例如可以通过篡改剪贴板中的内容来攻击用户或窃取用户的敏感信息。

为了解决这些安全问题，浏览器引入了新的复制 API，例如 `document.execCommand('copy')` 和 `navigator.clipboard.writeText()` 等，可以让网页在不直接访问剪贴板的情况下实现复制操作。`clipboard.js` 利用了这些浏览器提供的 API，避免了直接访问剪贴板带来的安全风险。