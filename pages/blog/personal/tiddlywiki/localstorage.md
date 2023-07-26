## Several Storage

* local storage
* seeeion storage
* indexeddb
* web sql
* cookies
* etc

<hr>

localStorage 最主要的特点是：

* 在同源的所有标签页和窗口之间共享数据。
* 数据不会过期。它在浏览器重启甚至系统重启后仍然存在。

```html
<textarea
  style="width: 200px; height: 60px"
  id="area"
  placeholder="Write here"
></textarea>
<br />
<button onclick="localStorage.removeItem('area');area.value=''">Clear</button>
```

```js
  area.value = localStorage.getItem("area");
  area.oninput = () => {
    localStorage.setItem("area", area.value);
  };
```