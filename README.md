# react-base

## 创建 react 单页应用

~~~
npx create-react-app react-base 
~~~ 

## cdn

* cdn 中建议使用 crossorigin 属性，可以查看到报错内容

## jsx

> jsx 是 javascript 的语法扩展

* jsx 在花括号中放置 js 代码
* 建议将标签内容放置在括号中，可以避免自动插入分号陷阱
* jsx 也是表达式，可以像正常的表达式一样使用
* 可以通过引号将属性值指定为字符串字面量(添加静态属性)，也可以通过花括号添加 javascript 表达式，对于同一属性不能同时使用这两种符号
* jsx 主要基于 javascript 规则，标签属性使用 camelCase（小驼峰命名）定义属性名称
    1. class -> className   
    ...
* 一个标签中没有子元素，可以使用单标签（ /> 闭合标签），就像 xml 一样

## 绑定事件

> 元素绑定事件时，handle 函数会重新指定 this，所以需要做处理

1. 函数改为箭头函数
    ~~~
    class app extend React.component{
        state: {
            title: 'hello'
        }
        handle = ()=>{
            console.log(this.state.title)
        }
        reader () {
            return <div>
                <butten onClick={this.handle} ></butten>
            </div>
        }
    }
    ~~~

2. 使用闭包
    ~~~
    class app extend React.component{
        state: {
            title: 'hello'
        }
        handle () {
            console.log(this.state.title)
        }
        reader () {
            return <div>
                <butten onClick={() => {this.handle()}} ></butten>
            </div>
        }
    }
    ~~~

3. 绑定并覆盖
    ~~~
    class app extend React.component{
        constructor (props) {
            super(props)
            this.handle = this.handle.bind(this)
        }
        state: {
            title: 'hello'
        }
        handle () {
            console.log(this.state.title)
        }
        reader () {
            return <div>
                <butten onClick={this.handle} ></butten>
            </div>
        }
    }
    ~~~

4. 调用时绑定
    ~~~
    class app extend React.component{
        state: {
            title: 'hello'
        }
        handle () {
            console.log(this.state.title)
        }
        reader () {
            return <div>
                <butten onClick={this.handle.bind(this)} ></butten>
            </div>
        }
    }
    ~~~

    
# react-app

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `yarn start`

Runs the app in the development mode.<br />
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.<br />
You will also see any lint errors in the console.

### `yarn test`

Launches the test runner in the interactive watch mode.<br />
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `yarn build`

Builds the app for production to the `build` folder.<br />
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.<br />
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `yarn eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).

### Code Splitting

This section has moved here: https://facebook.github.io/create-react-app/docs/code-splitting

### Analyzing the Bundle Size

This section has moved here: https://facebook.github.io/create-react-app/docs/analyzing-the-bundle-size

### Making a Progressive Web App

This section has moved here: https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app

### Advanced Configuration

This section has moved here: https://facebook.github.io/create-react-app/docs/advanced-configuration

### Deployment

This section has moved here: https://facebook.github.io/create-react-app/docs/deployment

### `yarn build` fails to minify

This section has moved here: https://facebook.github.io/create-react-app/docs/troubleshooting#npm-run-build-fails-to-minify
