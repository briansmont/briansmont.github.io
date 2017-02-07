---
layout: post
title: First Experiences With React
---

<h3>Advantages of React</h3>
I recently decided to built some basic applications with React. If you know basic JS it is relatively straight forward.
A few bullet points:
<ul><strong>React Pros</strong>
    <li>It's easy to see how a component is rendered - it is right in the render function!</li>
    <li>Since each part of an app should be built into its own component, it is incredibly easy to follow functionality. This makes debugging and maintainance pretty simple</li>
    <li>It works with most frameworks. I rebuilt portions of an AngularJS application to render using React with very little issue.</li>
    <li>The Virtual DOM - React knows when to render the view because it is aware of data changes.</li>
    <li>There are many react-addons which offer high versatility - For example, state management: <a href="http://redux.js.org/" target="_blank">redux</a>, or graphing abilities: <a href="http://recharts.org/#/en-US/" target="_blank">recharts</a>.</li>
</ul>
<ul><strong>React Negatives</strong>
    <li>React only serves as the view, although there are compatible tools to simplify state management</li>
    <li>Integrating ReactJS into some MVC frameworks requires additional configuration.</li>
    <li>Writing components isn't as straight forward as plain HTML/CSS, there is a learning curve for the new syntax</li>
</ul>