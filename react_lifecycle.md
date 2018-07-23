### react 生命周期 总的可以分为  三个阶段 首先是 初始化阶段 -> 更新 -> 销毁

- 初始化阶段 触发的钩子函数
1. getDefaultProps()
> 设置默认的props， 也可以使用的DefaultProps设置组件的默认属性
2. getInitialState()
> 在使用es6的class语法时是没有这个钩子函数的，也可以直接在constructor中定义this.state 此时可以访问this.props
3. componentWillMount()
> 只在组件初始化是调用 以后组件更新不调用 整个生命周期只调用一次，此时可以修改state
4. render()
> react最重要的步骤 创建虚拟dom进行diff算法比较 更新dom树  此时不可修改state
5. componentDidMount()
> 组件渲染之后调用 可以通过this.getDOMNode()获取和操作dom节点 只调用一次

- 更新阶段 触发的钩子函数
6. componentWillReceiveProps(nextProps)
> 组件初始化时不掉用，组件接受新的props时调用
7. shouldComponentUpdate(nextProps, next.state)
react 性能优化非常重要的一环 组件接受新的state或者props时调用 我们可以设置在此对比前后两个props和state是否相同，如果相同则返回false 阻止更新
8. componentWillUpdate(nextProps,nextState)
组件初始化时不调用，只有在组件将要更新时才调用 此时可以修改state
9. render()
> 组件渲染
10. componentDidUpdate()
> 组建初始化时不调用，组件更新完成后调用，此时可以获取dom节点
- 销毁
> 组建将要销毁时调用  一些监听器和组件定时器需要在此时清除
