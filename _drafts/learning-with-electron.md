---
layout: post
title:  "Learning with Electron"
date:   2016-07-10 12:00:00 -0600
categories: jekyll update
---

### Continuous Learning

In the world of software development it often seems like if you aren't learning
something new you're falling behind.
While this isn't entirely true (I'm sure C developers will still have jobs in 20
years) there's something to be said for trying to learn new things throughout
your career regardless of what path you want to take.
In light of this I recently set out to teach myself the basics of JavaScript.
I've been working at [Spiceworks](http://www.spiceworks.com/) for over a year
now which is primarily a web development shop and I still hadn't written more
than 10 lines of JavaScript.
This is largely because I do backend infrastructure work but I decided I should
still be literate in JavaScript to be a more flexible developer.

### Electron

This brings me to [Electron](http://electron.atom.io/).
Electron is the framework which the popular text editor [Atom](http://atom.io)
and the desktop client for [Slack](http://slack.com) are built on.
At its most simple level it ties together Nope and Chromium to be able to run
HTML, JavaScript, and CSS applications as native desktop applications.
It also handles the abstractions of running on Mac, Linux, and Windows so the
developer get's to focus on creating the application and not writing adapters for
all the different OS's.
But that's enough about Electron, here's why I think it would make a great learning
platform.

### Learning

First let me discuss a little bit about how and why I decided to learn JavaScript
by building an app on Electron.
First I wanted to make a desktop client for searching GIFs because it sounded like
a fun thing to do and we use a lot of GIFs in chat at work.
Furthermore Electron is completely JavaScript, CSS, and HTML which are all things
I wanted to get more practice with.
The app I built is called [Gifinater](http://github.com/natesholland/gifinater)
and can be found on my Github.

Now for why Electron can make a great platform for learning JavaScript.
First off everything can be set up to run out of the box.
I started with the [Electron Quick Start](https://github.com/electron/electron-quick-start)
but as a learning tool it could be configured to easily boot up with a skeleton
meant for the students to fill out.
Furthermore since it works across platforms it can still be an effective teaching
tool where student's machines will be heterogenous.
A prebuilt testing framework could also be set up with Jasmine, allowing for
automated testing of the students work or submissions.
