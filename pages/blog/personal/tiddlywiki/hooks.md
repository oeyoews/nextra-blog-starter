@[toc]

useState 被称为 React Hooks 中的一员，是因为它是 React 16.8 版本中推出的其中一种钩子函数。React Hooks 提供了一种全新的编写 React 组件的方式，它可以使代码更加简洁、易于理解和维护。在使用 Hooks 的过程中，开发者可以直接在函数组件中使用状态（useState）、效应（useEffect）和上下文（useContext），而无需再编写类组件。这种方式大大降低了 React 开发的学习成本，同时也可以提高代码的可读性和可维护性。

之前，React 组件通常只能使用类组件来管理状态。类组件虽然功能强大，但它往往需要在类中定义许多方法，并且容易产生问题，导致代码复杂难以维护。Hooks 是 React 团队为了解决这些问题而推出的一种新的解决方案。Hooks 可以将组件逻辑拆分为可复用的代码段，并且让代码更易于测试和重构。而 useState 则是最基本、也是最常用的一个 Hook，它被广泛地应用于 React 函数式组件中，用于管理组件内部的状态。

总之，通过 Hooks，React 提供了一种更加优雅、灵活的编写组件的方式，而 useState 则是 React Hooks 中最基本和常见的一种 Hook。

除了 `useState`，React Hooks 还提供了其他常用的钩子函数，包括 `useEffect` 和 `useContext`。

## useEffect

有些组件需要在挂载、卸载或更新时执行一些副作用操作（比如调用接口请求数据或者修改 DOM）。`useEffect` 就是用来管理这些副作用的钩子函数。它在每次渲染后都会执行，并且可以返回一个清除副作用的函数，以避免内存泄漏。

使用方式：

```jsx
import React, { useEffect } from 'react';

function MyComponent() {
  useEffect(() => {
    // 执行副作用操作
    return () => {
      // 清除副作用操作
    };
  }, [/* 依赖项列表 */]);

  return <div>...</div>;
}
```

在这个例子中，我们通过 `useEffect` 来执行一些副作用操作。可以在钩子函数中进行接口调用、DOM 操作等非纯函数的操作。在副作用函数中返回另一个函数，它将在下一次渲染之前运行，以便清理任何不再需要的资源。`useEffect` 的第二个参数是一个数组，它用于指定哪些变量发生改变时需要重新执行副作用函数。如果数组为空，那么它只会在挂载和卸载后执行一次。如果没有传递第二个参数，则每次渲染后都会执行副作用函数。

## useContext

`useContext` 允许在组件树中跨层级传递数据而不必一级一级地手动传递 props。它是一个接收 React 上下文对象（通过 `React.createContext()` 创建）并返回当前上下文值的钩子函数。

使用方式：

```jsx
import React, { useContext } from 'react';

const MyContext = React.createContext(/* 默认值 */);

function MyComponent() {
  const value = useContext(MyContext);
  return <div>{value}</div>;
}
```

在这个例子中，我们创建了一个上下文对象 `MyContext`，并在组件中调用 `useContext` 来获取当前上下文的值。如果没有找到上下文提供者（即该组件的父组件未提供该上下文），则默认值将被返回。在使用这种方式时，需要保证上下文提供者和依赖于上下文的消费者组件处于同一个组件树中，才能使用上下文来进行数据交换。