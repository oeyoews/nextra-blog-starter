<$tid2pdf />

```js
// 获取按钮元素
const myButton = document.getElementById('myButton');

// 绑定点击事件
myButton.addEventListener('click', function(event) {
  // 使用 event.objectParam 获取事件相关的信息
  const button = event.target;
  const buttonId = button.id;
  const eventType = event.type;
  const clientX = event.clientX;
  const clientY = event.clientY;
  
  console.log('按钮ID：', buttonId);
  console.log('事件类型：', eventType);
  console.log('鼠标点击位置：', clientX, clientY);
});
```