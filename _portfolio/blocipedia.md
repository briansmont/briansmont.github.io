---
layout: post
title: Blocipedia
feature-img: "img/blocipedia-homepage.png"
thumbnail-path: "img/blocipedia-title.png"
short-description: Wiki Knowledge Sharing
permalink: /portfolio/portfolio/

---

## Summary
Blocipedia is a Ruby on Rails application project assigned in the curriculum. I had previously built another Rails application, but this specific project went more in depth with integrating gem programs and exploring other Rails abilities.

## Problem
Blocipedia is meant to be a community for users to share their knowledge on a wide array of topics. Since the application needs to build user profiles, and then these users have access to create and edit wikis, there are many things to consider. <br>
<ul>For Example:
    <li>Can all members create wikis?</li>
    <li>Who has access to read specific wikis in the application?</li>
    <li><a href="https://en.wikipedia.org/wiki/Create,_read,_update_and_delete" target="_blank">CRUD</a> permissions - Who has them?</li>
    <li>How can someone add a peer to collaborate on their wiki?</li>
</ul>

These are some of the user interface topics to consider when building the application. General functionality also needs to be set up to create the user profiles, wikis, collaborators, and the relationships that connect them.

## Solution
To create users, I installed the <a href="https://github.com/plataformatec/devise" target="_blank">Devise gem</a>. This gem offers the application techniques for authentications, email confirmations, controller filters, and all views associated with creating/editing user information.
<br><br>
Once users have been set up, CRUD (Create/Read/Update/Delete) functionality was next. I generated a wikis controller to handle all of the tasks. The controller is equipped with code to perform all of the tasks which render the views and changes requested by the user.
<br><br>
As far as users having restrictions, I needed to set up roles. I used an <a href="http://edgeapi.rubyonrails.org/classes/ActiveRecord/Enum.html" target="_blank">enum</a>. This attribute enables the application to reference values as integers, such as *:admin = 2*. 
<br>Below you can see the results of calling a user and requesting their role:
```
> user = User.find(1)
  User Load (0.1ms)  SELECT  "users".* FROM "users" WHERE "users"."id" = ? LIMIT 1  [["id", 1]]
=> #<User id: 1, email: "admin@blocipedia.com", role: 2, name: "The Boss">

> user.role
=> "admin"
```
<br>
Once the roles were set up, I used the <a href="https://github.com/elabs/pundit" target="_blank">Pundit gem</a> to help implement a policy scope.  This dictates the roles required for specific controller actions. If a user wants to upgrade to a premium member, they can through the <a href="https://github.com/stripe/stripe-ruby" target="_blank">Stripe gem</a>. Of course, some tasks are reserved only for the administrators.
<br><br>
To create a more unique experience, users also have the ability to privatize their own wikis in the app. Upon creation or editing of their own wiki, they can check off the private box, reserving it for themselves or for those they choose to be collaborators. This feature guarantees that users can protect their postings.

{:.center}
![]({{ site.baseurl }}/img/blocipedia-gem-displays.png)<br><br>
From left to right, you can see the devise sign up for new users, the upgrade account form, as well as the markdown live preview for new & edited wikis.

## Results
Upon opening the application's main page, both existing & new users have options to sign in and then their membership levels determines the rest. <em>Basic</em> members have the ability to read and create <strong>ONLY public wikis, visible to ALL users</strong>. If they choose to upgrade to <em>Premium</em> status, they can create <strong>public & private wikis</strong>, and add other users as collaborators with editing abilities.
## Project Conclusions
This was my second project with Ruby on Rails. The Rails full-stack framework offers many tools that simplify the development process.  ActiveRecord allows you to easily communicate with the database. The routing system provides a clean way to direct or redirect user requests and there seems to be a limitless amount of gem programs available to implement into any application. The framework and these extensive tools made the development process an enjoyable and educational experience.

{:.center}
![]({{ site.baseurl }}/img/blocipedia-title.png)