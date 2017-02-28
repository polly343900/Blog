- webpack-dev-server报的```Module build failed: SyntaxError: Unexpected token (5:12)```
  - 在webpack.config.js里loader加上
    ```js
        query: {
                presets: ['es2015', 'react']
            }
    ```
  - 此外，dev依赖要加上"babel-preset-es2015"和"babel-preset-react"
- _react2.default.render is not a function
  - 原因render已经是ReactDOM的方法了，把react-dom也要引入进来
- [es5,es6写法的问题](http://blog.kdchang.cc/2016/04/04/react-react-native-es5-es6-cheat-sheet/)
- jsx vs html
  - 标签属性是驼峰形式的 比如maxlength，jsx是maxLength
  - 标签要封闭，比如html可以是```<input>```,但是jsx一定要是```<input />```
  - 属性名字是基于DOM的，比如class在jsx里要写成className
- jsx只能return一个元素，原因是return只能return 一个语句
- ```{" "}```是为了在这两中间插个空格

  ```js
    <a href="javascript:;">google</a>{" "}
    <a href="javascript:;">facebook</a>
  ```
  
- 动态渲染HTML 使用```dangerouslySetInnerHTML```
- 当渲染组件的时候处理的都是虚拟DOM。如果想处理真实的DOM可以借助于refs和findDOMNode。
- ajax是放在componentWillMount里还是componentDidMount里
  - 对于client渲染，放在哪都可以。对于server端渲染，由于server端和client端都会调用componentWillMount，因此放在componentDidMount里比较好。 
  - https://github.com/shiningjason1989/react-quick-tutorial/issues/10 
