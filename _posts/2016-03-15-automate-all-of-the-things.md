---
layout: post
title:  "Automate all of the things"
date:   2016-03-15 10:56:30 -0600
categories: jekyll update
---

# Automate all of the things

Automation is a common topic of conversation amongst developers these days.
Whether they be automated cars or automated CI/CD projects large automation
projects are a run topic to talk about and garner a lot of attention.
The thing that is a bit less sexy and therefore get less attention is the automation
of all of the small everyday tasks we perform throughout the day.

At [Spiceworks](http://www.spiceworks.com/) we have releases for Community every
Tuesday and Thursday.
Every time we have either a Dev Lead or a QA Lead running the release, meaning
they make sure all the tickets going into the release are reviewed and tested as
well as performing some basic smoke testing on the app in staging before we deploy
to production.
This process ends up taking up a good amount of our time because Community is an
older legacy app and takes a while to deploy and run the tests and so on.
Part of our process is to always tag our releases with the timestamp of when
they are released.
