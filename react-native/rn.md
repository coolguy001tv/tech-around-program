title: 开发周边的技术
speaker: 丁丁
url: https://github.com/coolguy001tv/tech-around-program
transition: zoomin
files: /css/common.css
theme: dark
date: 2016/03/16
[slide]
# React与ReactNative开发
-----------

* JSX {:&.rollIn}
* 数据流
* 生命周期
* layout
* 我们目前的工程



[slide]
# JSX
-------------

* non-jsx
```
React.createElement('div',{className:"divider"},
    "Label Text",
    React.createElement('hr')
);
```    
* jsx
```
<div className="divider">
    Label Text<hr />
</div>
```
[note]
* 事件绑定 
* 与HTML的主要区别  
[/note]

[slide]
# 数据流
## 单项数据流
----------
* props
* state
    * 是否是从父级通过 props 传入的？如果是，可能不是 state 。
    * 是否会随着时间改变？如果不是，可能不是 state 。
    * 能根据组件中其它 state 数据或者 props 计算出来吗？如果是，就不是 state 

[note]
props引发的问题（嵌套）
[/note]



[slide]
# 生命周期1
--------

* getDefaultProps
* getInitialState
* componentWillMount
* render
* componentDidMount

[note]
getDefaultProps 和 getInitialState 在ES6已经通过其他方式来实现
[/note]

[slide]
# 生命周期2
--------

* componentWillReceiveProps
* shouldComponentUpdate
* componentWillUpdate
* render
* componentDidUpdate




[slide]
# flex
-------------
flexDirection 默认是*column*  
[阮一峰-flex布局](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)


[slide]
# 实例讲解
-----------
![登录](/image/login.png)
[note]
    * 右侧的小叉
    * 显示密码
    * 下拉上滑
    * btn的enable状态
[/note]

[slide]
# 参考资料
----------
[react中文文档](http://reactjs.cn/react/docs/thinking-in-react.html)
