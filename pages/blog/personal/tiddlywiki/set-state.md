在 JavaScript 中，语法 setState(prevState => [...prevState, name]) 用于通过将新元素添加到数组末尾来更新数组状态。

具体来说，setState 是由 React 的 useState hook 提供的函数，它允许您更新组件的状态。您传入一个新的状态值，React 将自动使用更新后的状态重新渲染组件。

setState 的参数是一个函数，它以先前的状态为参数并返回新状态。在这种情况下，(prevState => [...prevState, name]) 是一个函数，它将先前的状态（一个数组）展开到一个新数组中，然后使用展开运算符将新的 name 值添加到数组末尾。

因此，当此函数传递给 setState 时，它将通过将 name 添加到数组末尾来更新数组状态。然后使用更新后的状态重新渲染组件。

[ref](https://www.bilibili.com/video/BV1Ze4y1u792/?spm_id_from=333.337.search-card.all.click&vd_source=d6afd7eedd9f9c940321c63f0a1539e3)