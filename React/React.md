## What is react?

React is a declarative, efficient and flexible JS library for building user interface.

render is to put this jsx component to the page.

individual components and views
components make js functions to make html

~~~JavaScript

const App= function () {
    return <div>Hi!</div>
    <!-- jsx -->
}
~~~

const is ES6, decalre varieble const will never change. It's like var.

JSX is to make code clean and clear.

ReactDOM is to interact with dom.

~~~React
ReactDOM.render(<App />, document.querySelector('.container'));
~~~

It's equal to

~~~React
const App= () => {
    return <div>Hi!</div>;
}

~~~

Seperate Screen into different component.

![component][component]

[component]:https://cl.ly/3u1f0Q0P2D3a/Image%202018-03-27%20at%203.44.19%20PM.png
