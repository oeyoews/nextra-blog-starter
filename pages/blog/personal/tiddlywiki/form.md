HTML中的`<form>`元素用于创建一个包含交互式表单的区域，用户可以在该表单中输入数据并将其提交给服务器进行处理。`<form>`元素是HTML中最重要的表单元素之一，它允许用户与网页进行交互，发送数据并执行各种操作。

以下是`<form>`元素的一般结构：

```html
<form action="处理表单的URL" method="提交方法">
  <!-- 表单内容 -->
</form>
```

`<form>`元素有两个重要的属性：

- `action`：指定表单数据提交的URL。当用户提交表单时，数据将被发送到该URL进行处理。这通常是服务器端脚本的URL，可以在该脚本中对表单数据进行处理、验证或保存。例如，`action="process-form.php"`将表单数据提交到名为"process-form.php"的服务器端脚本进行处理。

- `method`：指定提交表单数据的HTTP方法。常见的方法有"GET"和"POST"。"GET"方法将表单数据附加在URL的末尾并发送给服务器。这对于请求数据或执行查询非常有用。"POST"方法将表单数据作为HTTP请求的一部分发送给服务器，并且不会在URL中可见。这对于提交敏感或较大量的数据更为常见。

`<form>`元素内可以包含各种表单元素，例如输入字段、复选框、单选按钮、文本区域等。这些表单元素将用于收集用户输入的数据。

以下是一个包含常见表单元素的示例：

```html
<form action="process-form.php" method="POST">
  <label for="name">姓名：</label>
  <input type="text" id="name" name="name" required>

  <label for="email">邮箱：</label>
  <input type="email" id="email" name="email" required>

  <label for="message">留言：</label>
  <textarea id="message" name="message" rows="4" cols="50"></textarea>

  <input type="submit" value="提交">
</form>
```

在这个示例中，当用户点击提交按钮时，表单数据将被发送到"process-form.php"进行处理。表单包含了一个文本输入字段（姓名）、电子邮件输入字段、一个文本区域（留言）以及一个提交按钮。