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

<h3>Phase 1</h3>

<h5>Container Component</h5>
In the application, I needed to have a search bar, a visual list of the to-do items, and a place to type in new tasks. Each of these would be their own component, but they need to be held within one container component. My main component, <strong>TodoApp.jsx</strong> was setup in this format:

<strong>TodoApp.jsx:</strong><br>
```
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
```
The <strong>module.exports = TodoApp;</strong> allows you to inject this component into other files in your application. The main JS file in my app, <strong>app.jsx</strong> is setup in this fashion:
<br>
<strong>app.jsx:</strong>
```
var TodoApp = require('TodoApp');
ReactDOM.render(
  <TodoApp/>,
  document.getElementById('app')
);
```
The first line of code directly above includes the component into this completely separate file. The remainder of the code is required to render the TodoApp into the DOM element with the <strong>ID of 'app'</strong>.

Eventually, the <strong>TodoApp.jsx</strong> file looks like this to include the subcomponents needed to accomplish the tasks.
```
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
```
<small>The prop function explanation</small>


<h5>Lifecycle methods and Changes of State</h5>
Some tidbits about when I am using them - and images of the code itself
componentDidUpdate(), componentWillUpdate

Debugging - React debugging tools

<h3>Phase 2</h3>
Refactoring with Redux
What is redux?
Reducers
Actions
STORE - how it works, how it includes the reducer combination, including Redux tools


<h5>Firebase Auth</h5>
removing local storage and setting up with firebase authentications






















