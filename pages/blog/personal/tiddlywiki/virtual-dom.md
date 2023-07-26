虚拟DOM(Virtual Dom)就是一个JS对象(数组对象)，用来描述真实DOM。相对通过html标签创建的真实DOM，虚拟DOM是保存在客户端内存里的一份JS表述DOM的数组对象。

虚拟DOM更新性能快的原因并不是因为在内存中(理论上任何软件都是运行在内存中)，而是因为虚拟DOM储存的数据格式为JS对象，用JS来操作(生成/查询/对比/更新)JS对象很容易。用JS操作(生成/查询/对比/更新)真实DOM则需要调用Web Action层的API，性能相对就慢。

react运行(更新)步骤，大致为：

* 定义组件数据变量
* 定义组件模板JSX
* 数据与模板结合，生成一份虚拟DOM
* 将虚拟DOM转化为真实DOM
* 将得到的真实DOM挂载到html中(通过真实DOM操作)，用来显示
* 监听变量发生改变，若有改变重新执行第3步(数据与模板结合，生成另外一份新的虚拟DOM)
* 在内存中对比前后两份虚拟DOM，找出差异部分(diff算法)
* 将差异部分转化为真实的DOM
* 将差异化的真实DOM，通过真实DOM操作进行更新

[ref](https://github.com/puxiao/react-hook-tutorial/blob/master/%E9%99%8401%EF%BC%9AReact%E5%9F%BA%E7%A1%80%E7%9F%A5%E8%AF%86.md#%E5%A3%B0%E6%98%8E%E5%BC%8F%E5%BC%80%E5%8F%91-%E6%A6%82%E5%BF%B5%E8%A7%A3%E9%87%8A)