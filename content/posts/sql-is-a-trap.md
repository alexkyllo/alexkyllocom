---
title: "SQL is a Trap"
date: 2022-01-03T22:12:48-08:00
draft: true
toc: false
images:
tags: 
  - data-science
  - abstraction
---

Pardon the clickbaity title but I need to get something off my chest. On Data
Twitter I keep seeing claims that SQL is the lingua franca of analytics, and
that everything that can be done in SQL should be, along with pitches for new
frameworks and SaaS tools that allow you to build pipelines, metrics, dashboards
and even visualizations with no code but SQL (and maybe some YAML).

SQL is what programmers call an _external_ domain specific language (DSL). It's
a language someone invented to solve problems in a specific domain: transforming
one or more input relations (tabular datasets) into one output relation.

The trouble with SQL is that it traps you at its level of abstraction. It
doesn't let you reach down a layer and work directly in the language of query
plan operations, which would be a powerful tool for optimizing query
performance. More importantly, it doesn't let you build _up_. 

The notion of _power_ in programming comes from abstractions that let you
express solutions to complex problems in concise terms. How do you take a
complex solution and make it concise? By designing a _language_, a notation
where symbols represent concepts.

In the object-oriented programming (OOP) paradigm you do this by modeling the
problem domain as a graph of entities that send each other commands and
requests. In the functional programming (FP) paradigm you do it by defining the
solution as a mapping from input values via function composition. Either way,
the solution is not really written in the programming language itself, but in
the more concise notation you created and tailored to the problem at hand.

[This tweet](https://twitter.com/tottinge/status/1476013421518888970?s=20) by
Tim Ottinger gets at what I mean:

![](/edsl-tweet.png)

Now if you insist on doing all the work fixating on a specific DSL, you're
surrendering the power to build up a tower of abstraction that reaches the
solution to your problem, over to the tool vendors.