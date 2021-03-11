#vue生命周期
`beforeCreate:`
- 在实例初始化之后 data Observer和事件配置之前被调用。
- 此时事件已经初始化，只是数据观察和事件机制尚未形成，不能获取DOM节点（没有data，没有el）data和methods都拿不到。

`created:`
- data已经初始化，计算属性、event/watch事件回掉，但 dom树并未挂载。
- 实例已经创建，仍然不能获取DOM节点（有data，没有el）此时可以获取data和methods，可以初始化某些属性值，然后再渲染成视图，异步操作可以放在这里。

`beforeMount:`
- 挂载前被调用，render函数首次被调用生成虚拟DOM。
- 是个过渡阶段，依然获取不到具体的DOM节点，但是vue挂载的根节点已经创建（有data，有el）。

`mounted:`
- 挂载完成，DOM树已经完成，渲染到页面，可进行DOM操作。
- 数据和DOM都已经被渲染出来了，模板渲染成html后调用，通常是初始化页面完成后再对数据和DOM做一些操作，需要操作DOM的方法可以放在这里。

`beforeUpdate:`
- 数据有更新被调用
- 检测到数据更新时，但在DOM更新前执行

`updated:`
- 虚拟DOM重新渲染补丁，以最小DOM开支重新渲染DOM
- 更新结束后执行

`beforeDestroy:`
- 实例销毁之前调用，这里还可以访问实例数据

`destroyed:`
- 组件销毁后调用

参考：[enter link description here](https://www.jianshu.com/p/a56583d56878)
参考：[enter link description here](https://www.jianshu.com/p/410b6099be69)

**第一次页面加载会触发哪些钩子** 
- beforeCreate、created、beforeMount、mounted

**vue中内置的方法 属性和vue生命周期的运行顺序**
- props => methods =>data => computed => watch; 

