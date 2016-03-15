---
layout: post
title:  "Automate all of the things"
date:   2016-03-15 10:56:30 -0600
categories: jekyll update
---

# Automate All Of The Things

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
Tagging allows us to have frozen snapshots of what code is deployed when but it
does add another manual step in the process of releasing our code.
Here's where automating all of the things comes in.

Automating something as simple as creating a tag might seem silly.
It only takes a few minutes to run a couple commands to ensure that the current
release branch contains the head of master and the sha is correct.
However there are still manual errors that can occur and furthermore
Dev Lead hours are not cheap and we would rather not waste them.
We've had people accidentally tag master (safe but wasted time), or tag the wrong
sha (potentially dangerous).

Therefore we decided to automate the process of tagging a release.
This took about an hour to hammer out and we had to tweak a few things after our
first test run.
Here are a few of the main take-aways I got from automating this small process.

* Not only does this save me time, it ends up saving time for every Dev and QA Lead
in the company.
* Small automation projects take a small amount of time and can be fit into small
blocks of time that would otherwise be wasted.
* By automating a process it allows us to hand the process off to less experienced devs.

One of the major wins of this project is it took almost no time to automate but
it is going to save us time across the company and free up some extra time for
our leads who are often strapped for time.
I would encourage anyone who has an extra 30 minutes between meetings to try
and automate a small task you or someone you work with does every day.
Not only will it help you be more productive in the long run, but it also makes
friends because you are saving other people time.

For reference here is the automation script:
<script src="https://gist.github.com/natesholland/dccc1cd42787a72c863d.js"></script>
