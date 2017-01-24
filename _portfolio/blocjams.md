---
layout: post
title: BlocJams
feature-img: "img/turn_the_music_up.png"
thumbnail-path: "img/blocjams_title.png"
short-description: Spotify Inspired Music Application
---

## Summary
This case study will cover two different phases/builds of BlocJams.  The languages for each phase are listed below:
<ol>
  <li>Phase 1: <strong>HTML, CSS, JS, JQuery & DOM Scripting</strong></li>
  <li>Phase 2: Refactor & Rebuild Phase 1 using <strong>Angular JS Version 1</strong> framework</li>
</ol>

BlocJams is a Spotify inspired music application.  This was the first project assigned to me in the Bloc curriculum.  The second project was to rebuild the same BlocJams from the ground up using AngularJS framework.  The project(s) served as a means to strengthen HTML5, CSS & JS skills, while introducing me to new tools including JQuery, DOM Scripting, AngularJS & many of its associated tools.

## Problem
The goal of this project was to build a web app to play selected music files. The greatest challenge of building this was styling and constructing the application so it could handle an unknown quantity of albums and songs.

{:.center}
![]({{ site.baseurl }}/img/bloc_songlist.png)

<h1><u>Phase 1:</u></h1>
## Solution
The cleanest way to have the app sort through all the content was to create templates for each item and have JS, DOM scripts, and Jquery selectors loop and display the files/information.  HTML & CSS code was able to list the content, but the previously mentioned tools were necessary to sort/select/change and play files.

## Results
By integrating HTML5, CSS, JS, JQuery and more, I was able to construct a fully functional landing page, the album collections, and the page with the music player.

Each page displays a linked logo in the top left, and the collection link in the top-right corner.
<h3>Landing Page</h3>
The landing page has a large photo and some selling points listed across the bottom of the page. The slogan "Turn the music up!" is visible in the center.

{:.center}
![]({{ site.baseurl }}/img/blocjams.jpg)

<h3>Album Collection</h3>
The album collection page will list as many albums as the collection holds.
<h3>Music Player</h3>
This page performs the core of this application. By clicking on the song or the play button itself, the user has full control of the player and album library.
<br><br>

<h1><u>Phase 2:</u></h1>

## Solution
For this version I utilized the AngularJS (Version 1) framework to build the app. Angular allowed me to build this SPA(single-page-app) to reduce transition time when switching around the program. I built the BlocJams module and bootstrapped it to the application. In this context, bootstrapping is initializing the Angular application. The module contained controllers and their injected services which helped display content and control actions taken upon user requests. All of the AngularJS functionality was accessible through directives which were placed into the HTML elements throughout the application. To navigate the application, a <a href="https://github.com/angular-ui/ui-router" target="_blank"><strong>UI-Router</strong></a> module was used. This module is injected into the application, and it uses <em>Providers</em> to configure the application's paths.
## Results
Users interact through the MVC and have full control over the application. They can sort through the full collection of music. A new feature in this Phase is the player-bar as seen in the image below. The high <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/z-index" target="_blank">z-index</a> of the player bar tool allows users to see the song info & status update live regardless of the page that they are on. Angular's Single Page Application ability allow for quicker navigation between application views.


{:.center}
![]({{ site.baseurl }}/img/blocjamsplayerbar.png)


## Project Conclusions
The two portions of BlocJams were great learning tools.  Phase 1 gave me more experience writing Vanilla JS, HTML & CSS, and then refactoring DOM Scripts using JQuery.  Phase 2 Phase 2 helped me to understand when and why a JS Framework makes sense for an application.
<ul>
  <li>For basic DOM manipulations, JQuery & VanillaJS should suffice and seem to be cleaner but offer less capabilities than Angular does...</li>
  <li>AngularJS provides the ability to hook functionality directly into an HTML element, removing the need for query the DOM with a selector. Angular also allows for <strong>two-way data binding</strong>, offering the option of dynamic data in the application.</li>
</ul>
{:.center}
![]({{ site.baseurl }}/img/blocjams_title.png)