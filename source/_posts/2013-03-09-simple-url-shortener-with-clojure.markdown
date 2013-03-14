---
layout: post
title: "Simple URL Shortener with Clojure"
date: 2013-03-09 12:25
comments: true
categories: clojure
---


Tinkering more with Clojure and basic web services.
<!-- more -->
Here’s the entire application code:

``` clojure
(ns startingclojure.app
  (:use [clojure.pprint] [compojure.core] )
  (:require 
    [ring.adapter.jetty :as jetty]
    [ring.util.response :as response]
    ))
 
(defonce counter (atom 999))
(defonce urls (atom {}))
(defn shorten
  [url]
  (let [id (swap! counter inc)
        id (Long/toString id 36)]
    (swap! urls assoc id url)
    id))
 
 
(defn homepage 
  [request] 
  (str @urls))
 
(defn redirect
  [id]
  (response/redirect (@urls id)))
 
(defroutes app
  (GET "/" request (homepage request))
  (GET "/:id" [id] (redirect id)))
```

Fire up the app with
``` clojure
(def server (jetty/run-jetty #’app {:port 8080 :join? false}))
```
And add some urls:
``` clojure
(shorten “http://woot.com”)

(shorten “http://logz.beauhinks.com”)
```
Navigate to http://localhost:8080

Try some of the keys…

Fairly incredible how little code there is to perform a redirect and handle routes. [Thanks to this video!](http://www.youtube.com/watch?feature=player_embedded&v=VVd4ow-ZcX0#!)