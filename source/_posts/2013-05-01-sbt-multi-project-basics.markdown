---
layout: post
title: "SBT Multi-Project Basics"
date: 2013-05-01 20:36
comments: true
categories: [Scala, Play!, SBT]
---

I've grown very fond of [lieningen](https://github.com/technomancy/leiningen) for managing dependencies and builds with Java and Clojure projects.
However, I'm currently working with some projects that rely on SBT for their build system.. namely the [Play! Framework](http://www.playframework.com/).
<!-- more -->


The project I'm working with is a vanilla Play! build with a number of submodules to break out functionality into reusable submodules. Let's get started with Play! as an example since it bundles [SBT](http://www.scala-sbt.org/)


