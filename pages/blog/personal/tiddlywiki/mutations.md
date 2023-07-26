```js
// 要观察的元素
const targetElement = document.getElementById("my-element");

// 创建 MutationObserver 对象
const observer = new MutationObserver((mutations) => {
  console.log("元素变化啦！", mutations);

  // 隐藏按钮
  const button = document.getElementById("my-button");
  button.style.display = "none";
});

// 指定要观察的元素以及要观察的变化类型
observer.observe(targetElement, { childList: true, attributes: true, subtree: true, characterData: true });
```