30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 14 [Output Style](http://leveluptuts.com/tutorials/sass-tutorials/14-output-style)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup
No setup needed today


## 2. Changing output style
By default, Sass outputs css in a nested format. You can change the output style to compressed, compact, or expanded if you'd like.
It's easy to change by just adding a little bit to the command you use to start the Sass watcher.  Let's try changing it to compact. We're also going to use a bit of a shortcut this time - instead of --watch, we're just going to use -w.

```
sass -w scss:css --style compact
```


## Extras
For fun, try out the other styles.  You can also visit (http://web-design-weekly.com/2014/06/15/different-sass-output-styles/) to see an example of each of the styles.