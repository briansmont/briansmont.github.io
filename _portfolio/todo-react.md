---
layout: post
title: ToDo With React & Redux
feature-img: "img/turn_the_music_up.png"
thumbnail-path: "img/blocjams_title.png"
short-description: Functional To-do list, wired with Firebase
---

## Summary
A to do application is a common project for learning <a href="https://facebook.github.io/react/" target="_blank">React</a>. React is a JS library which helps build efficient and fast UIs. React is component based, and every component has the ability to manage its own state. Each component is written in JS, which allows the ability to pass data throughout the application without changing anything in the DOM.
<br>
There were two phases of the To-Do project:
<ol>
  <li>Phase 1: Build react components which could manage state and store data in <a href="http://www.w3schools.com/html/html5_webstorage.asp" target="_blank">local storage</a></li>
  <li>Phase 2: Implement <a href="http://redux.js.org/" target="_blank">Redux</a>, a state container which comes with some really cool tools</li>
</ol>


My favorite aspect of React is that you can separate parts of your application into <a href="https://facebook.github.io/react/docs/react-component.html" target="_blank">components</a>. These components allow you to split your UI into separate reusable pieces. You can render a component which itself renders subcomponents. <br>
You simply need to include the main component in your application file, and have it render into the DOM element you are targeting on the HTML file.
<!--formatting of building a module, render, React.component, module.export etc-->
<!--Include image of index.html file & app.jsx-->
<!--Talk about jsx rendering-->
<!--babel so jsx can be read-->

<h2>Phase 1</h2>

<h4>Container Component</h4>
In the application, I needed to have a search bar, a visual list of the to-do items, and a place to type in new tasks. Each of these would be their own component, but they need to be held within one container component. My main component, <strong>TodoApp.jsx</strong> was setup in this format:

<strong>TodoApp.jsx:</strong><br>
~~~
var React = require('react');
var TodoApp = React.createClass({
  render: function() {
    return (
      <div>
        <p>Other components will be in this area!</p>
      </div>
    );
  }
});
module.exports = TodoApp; 
~~~
The <strong>module.exports = TodoApp;</strong> allows you to inject this component into other files in your application. The main JS file in my app, <strong>app.jsx</strong> is setup in this fashion:
<br>
<strong>app.jsx:</strong>
~~~
var TodoApp = require('TodoApp');
ReactDOM.render(
  <TodoApp/>,
  document.getElementById('app')
);
~~~
The first line of code directly above includes the component into this completely separate file. The remainder of the code is required to render the TodoApp into the DOM element with the <strong>ID of 'app'</strong>.

Eventually, the <strong>TodoApp.jsx</strong> file looks like this to include the subcomponents needed to accomplish the tasks.
~~~
var React = require('react');
var TodoApp = React.createClass({
  render: function() {
    return (
      <div>
        <TodoSearch onSearch={this.handleSearch}/>
        <TodoList todos={filteredTodos} onToggle={this.handleToggle}/>
        <AddTodo onNewTodo={this.handleAddTodo}/>
        </div>
      </div>
    );
  }
});
module.exports = TodoApp; 
~~~
<small>Within the subcomponents, events such as "onSearch" take place. When those functions are triggered, they have access to functions in TodoApp through the props...</small>

<h4>Props</h4>
Props (Properties) have the ability to pass data between components. In the code above, <strong>handleSearch, handleToggle, and handleAddTodo</strong> are all functions within the TodoApp, the container component. This container component interacts with its <i>child components</i> through props.
<br>
In the <strong>AddTodo component</strong>, when a user triggers the onNewTodo function, it will call the <strong>TodoApp component</strong> function of <strong>handleAddTodo</strong>.
The child components will trigger changes in the parent/container component, which changes the <strong>state</strong> of the application.
<h4>State</h4>
In my application, when a user onNewTodo, it triggers the parent component's handleAddTodo. This will <strong>change the state of the application</strong>
<br>
<strong>AddTodo.jsx</strong>: call:
~~~
this.props.onNewTodo(todoText)
~~~
Triggers:
~~~
<AddTodo onNewTodo={this.handleAddTodo}/>
~~~
<strong>Within TodoApp.jsx</strong>:
~~~
handleAddTodo: function(text) {
this.setState({
  todos: [
    ...this.state.todos, 
    {
      id: uuid(),
      text: text,
      completed: false,
      createdAt: moment().unix(),
      completedAt: undefined,
    }
  ],
})
~~~
Above, we call <strong>this.setState()</strong> to change the state of the application.
There are a variety of <strong><a href="https://facebook.github.io/react/docs/react-component.html" target="_blank">Lifecycle Methods</a> that are available with React to help you manage state at different points.
<ul>Here are a few I used frequently in this app:
  <li>componentWillUpdate()</li>
  <li>componentDidUpdate()</li>
  <li>setState()</li>
  <li>getState()</li>
</ul>There are many more that are available in the link directly above

<h4>Local Storage</h4>
At this point my components all work well together. When something happens in a component, it is passed up through the parent and back down to all of the children with the render functions. The problem is when you refresh the page all of your To-Do tasks will disappear. As a temporary solution I set up an API tool which saved the tasks to a browser's local storage.
<br>
<strong>TodoApp.jsx:</strong>
~~~
componentDidUpdate: function() {
  TodoAPI.setTodos(this.state.todos);
}
~~~
<strong>TodoAPI.jsx:</strong>
~~~
setTodos: function(todos) {
  if ($.isArray(todos)) {
    localStorage.setItem('todos', JSON.stringify(todos));
    return todos;
  }
},
~~~


The code directly above sets the todos into local storage
<small>Similar functions in the TodoAPI can filter todos for search-text or completion status, as well as get the stored todos to display in the application.


<!--<h2>Phase 2</h2>-->
<!--Refactoring with Redux-->
<!--What is redux?-->
<!--Reducers-->
<!--Actions-->
<!--STORE - how it works, how it includes the reducer combination, including Redux tools-->


<!--<h5>Firebase Auth</h5>-->
<!--removing local storage and setting up with firebase authentications-->






















