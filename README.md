30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 17 [Using LiveReload](http://leveluptuts.com/tutorials/sass-tutorials/17-using-live-reload)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup

Download and install LiveReload from http://livereload.com  (which my brain is telling me is really liver eload.  just go with it.)


## 2. What is LiveReload?

From the (LiveReload web site)[http://livereload.com]

> LiveReload monitors changes in the file system. As soon as you save a file, it is preprocessed as needed, and the browser is refreshed.
> Even cooler, when you change a CSS file or an image, the browser is updated instantly without reloading the page.

## 3. Getting started with LiveReload

Open the app, and click the + button to add your scss directory to the watcher.
Once you've added the scss directory, click on it.  To the right, you'll see some instructions.  You can either add a script before the '</body>' tag, or you can install the browser extensions.  I chose the (Chrome extension)[https://chrome.google.com/webstore/detail/livereload/jnihajbhpnppcggbcgedagnkighmdlei/related?hl=en] route.
Back in the LiveReload app, if you're using the alpha Windows version, click on the actions+files text and toggle on.  If you're using the Mac version, you might just want to watch the video this lesson - it looks a lot different.

Also, since this is alpha, you'll have to change your html file to point to scss directory instead of css directory for your .css file.  Which is kind of painful, but will hopefully give you an idea of what liveReload will do in future versions.

Now, change something in your scss file - and then check the browser.  Voila! It's already been compiled and refreshed in the browser.  Except it's not very useful yet, since you can't specify output directory in alpha for Windows.

I spent a little bit of time looking around for a suitable alternative. Koala has a nice interface, and does the compile and lets you specify output directory and style, but doesn't have the automagic browser refresh. So, I guess it's either build your own, or wait for LiveReload to come out of alpha. 




## Extras
Find (or build!) a good replacement for LiveReload