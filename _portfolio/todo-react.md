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

<h5>Structure of Todo App - Main includes nav and other to-do subcomponents</h5>
Image of file tree, how to include each component using ES6

<h5>Lifecycle methods</h5>
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






















