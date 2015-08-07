---
layout: post
title: "Old School Tools"
date: 2013-06-29 23:40
comments: true
categories: [programming]
---

Lately I've been working on learning [UNIX](https://en.wikipedia.org/wiki/Unix), so I'm challenging myself to write this post in [GNU emacs](https://en.wikipedia.org/wiki/Emacs) inside a [GNU screen](https://en.wikipedia.org/wiki/GNU_Screen) terminal session. I even spent a few hours earlier browsing the internet in [Lynx][] and putting together simple [Perl](https://en.wikipedia.org/wiki/Perl) scripts and running them from [bash][]. 
[Lynx]: https://en.wikipedia.org/wiki/Lynx_(web_browser)
[bash]: https://en.wikipedia.org/wiki/Bash_(Unix_shell)  

In 2013 these feel like stone tools, having been invented before the internet existed and PCs became commonplace. But the truth is, they are extremely efficient and powerful in skilled hands (not mine... yet!). And the rise of cloud computing is breathing new life into them, because these cloud machines almost always run free UNIX-based operating systems. In order to set up and deploy code to a virtual machine instance on a cloud host such as Amazon Elastic Cloud Compute (EC2), you have to SSH (secure shell) into it, upon which you will be presented with a bash shell prompt. As such, UNIX tools work with plain text and keyboard shortcuts; because they had to work on old school mainframe terminal systems, they don't assume that the user has a mouse, or sometimes even arrow keys for navigation. So they make it possible to edit text files and run commands with lightning speed, if you know the commands and shortcuts.

So even though there are many slick, modern, feature-packed Interactive Development Environments (IDEs) available to programmers today, more often than not a developer building software for an internet startup will set up their dev environment on a cloud-hosted virtual machine, so they can SSH in from anywhere to write, test, and deploy their app entirely in the cloud.

If have an Apple computer, you're also running a UNIX OS under the hood--Mac OS X is based on [BSD](https://en.wikipedia.org/wiki/BSD). So you can try UNIX at home, you just need to open up the "Terminal" app and that will bring up a command line prompt. Most of the tools have help pages that explain how to use them and can be accessed by simply typing `man` and the name of the program. This tutorial from Zed Shaw will also help get you started: [Learn the Command Line the Hard Way](http://cli.learncodethehardway.org/book/).  It's frustrating and slow to start, but once you get the muscle memory down, working from the terminal is  much faster than dragging around windows and clicking on buttons with your mouse. Plus, after some practice, you will start to feel like a hacker!