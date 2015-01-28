30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 15 [For Loops](http://leveluptuts.com/tutorials/sass-tutorials/15-loops)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup
Minor setup today. We're going to add some more classes to our paragraphs. Please note that this is a horrible way to name classes, we're just doing it this way to show you the concept around for loops.
```
<p class="one">...</p>
<p class="two">...</p>
<p class="three">...</p>
<p class="four">...</p>
```


## 2. Using For Loops
In this lesson, we'll be using for loops to increment the margins of our four paragraphs.
For loops work pretty much the same way they do everywhere else - it's just a different syntax. We're going to use one to create our selectors and add incremental margin to those selectors. 

```
@for $i from 1 through 4 {
  .par-#{$i} {
    margin:10px * $i;
  }
}
```

You can see in your .css file that the output looks something like this, with $i replaced by the numbers 1-4 and the math done on the margins:
```
.par-1 {
  margin: 10px;
}

.par-2 {
  margin: 20px;
}

.par-3 {
  margin: 30px;
}

.par-4 {
  margin: 40px;
}
```


## Extras
Think of a better way to use for loops than naming your paragraphs like this.  :P