---
layout: post
title: "Getting Started with LightTable 0.3.x"
date: 2013-03-09 13:17
comments: true
categories: clojure
---

I spend a lot of time in Eclipse and [Vim](http://vim.spf13.com/)  on a daily basis. But, I also like to try new editors, one of which I have been following since they started their Kickstarter campaign... [LightTable](http://www.lighttable.com/). I'm also new to Clojure so I've dabbled with various setups of Counter-clockwise, emacs, and vim for Clojure development.

<!-- more -->
Chris Granger gives an excellent summary of the features and how to exercise them in the latest release [here](http://www.chris-granger.com/2013/02/27/light-table-030-experience/).

To get started with LightTable download the version for your platform at: [LightTable.com](http://www.lighttable.com/). For OSX, the install process was smooth but I have read that for Windows you might encounter a few nits getting running.

Once installed, launch LightTable and as of version 0.3.x you should be greeted with the following:
![sample](/images/posts/LightTable-3.png)

On the left you'll see some navigation bars. I'll go over those briefly.
  
  * Workspace: You can add folders and files which will be persisted between LightTable sessions here. Simply click "add folder" to add an existing Clojure project.
  * Navigate: A fuzzy finder for looking through your workspace files.
  * Clients: Shows running instances to which LightTable is connected. This may be a running Clojure REPL or your web browser via a socket.
  * Command: Summarizes all of the various commands available in the editor. I find myself refering to this constantly as I continue to learn the key bindings.

Basics covered... lets code! We'll get started with Clojure Koans -- small programming puzzles that are a great way to pick up the language.

I'm going to assume you have Java installed. If you don't and are running Windows see: [Installation Instructions](http://www.java.com/en/download/help/windows_manual_download.xml)

Leiningen
--------
1. Download [Leiningen](https://raw.github.com/technomancy/leiningen/stable/bin/lein)
2. Put the downloaded script somewhere on your path. ~/bin is suggested by the documentation.
3. Make it executable with
```
chmod 755 ~/bin/lein
```

If you need more help installing visit the [Leiningen docs](http://leiningen.org/#install) and more specifically if you're running Windows refer to those instructions. Leiningen relies on wget (a command line downloader). You can get wget from [GOW](https://github.com/bmatzelle/gow/wiki)

Clojure Koans
-----------
Get the puzzles either with Git via:
```
git clone git://github.com/functional-koans/clojure-koans.git
```
Or prior to Github shutting down the downloads feature this month [here](https://github.com/functional-koans/clojure-koans/downloads).

Navigate to the directory and hopefully if everything above went swimmingly you should be able to execute:
```
lein deps
lein koan run
```

If all went well, you should see:
```
➜  clojure-koans git:(master) ✗ lein koan run
Starting auto-runner...
Considering /Users/steve/Code/git/clojure-koans/src/koans/01_equalities.clj...

Now meditate upon /Users/steve/Code/git/clojure-koans/src/koans/01_equalities.clj:3
---------------------
Assertion failed!
We shall contemplate truth by testing reality, via equality
(= __ true)
```

The Clojure Koan puzzle is telling you what file you need to edit to proceed to the next text in the output.

LightTable
---------
Switch back to LightTable and click the "Workspace" tab and "Add Folder"

![workspace](/images/posts/Screenshot_3_10_13_10_38_PM.png)

Navigate to the directory you checked out the "clojure-koans" repository to on your local machine.

![project](/images/posts/Screenshot_3_10_13_10_39_PM-2.png)

I like to snap LightTable and iTerm to the left and right of my display while working through the puzzles. In OSX you can do this with [Shiftit](https://github.com/fikovnik/ShiftIt).

![snapped](/images/posts/Fullscreen_3_10_13_10_43_PM-2.png)

This way I can work through each step in the puzzle and see that the test passed successfully on the console at the right side of my display.

Start trying to solve the puzzles! If you really get stuck, the LightTable "Instarepl" is invaluable. To launch it, select the "Command" tab and start typing "inst" in the search bar. Select "Open a clojure instarepl" to launch a new tab with a running REPL.

![repl-launch](/images/posts/LightTable-2.png)

You can then use the new Instarepl tab to help reason out your answers and see the results immediately. For example, the first few puzzles...
![repl-error](/images/posts/Screenshot_3_10_13_10_58_PM.png)
Take note that I'm in the Instarepl tab. You can also toggle "live" evaluation by selecting the "live" button in the top right corner.
Finally, as you type the puzzles in to reason about them, you'll see results immediately. In the above screenshot, I have not solved the puzzle yet, hence the error! As soon as I satisfy the expression...
![repl-success](/images/posts/Screenshot_3_10_13_11_02_PM.png)
Success! But wait, my "koan" terminal on the right of display hasn't passed yet. I can then copy my solution from the Instarepl, insert it into the koan file and save to pass the koan! At first this may not seem useful, but as you progress through the more advanced koans, the REPL will greatly help you figure out Clojure forms and how to solve the problems.
Happy REPL'ing.



Questions?
---------
Feel free to post questions in the comments and I'll try to answer them. By far this is not a complete guide to getting running. Hopefully it consolidates a lot of resources around the web on Clojure and Light Table to get you started.




