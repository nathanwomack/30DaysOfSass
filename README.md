30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 1 [Build Your Own Function](http://leveluptuts.com/tutorials/sass-tutorials/11-build-your-own-function)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup
No setup today, you can use the files you have that you created in Day_10.


## 2. Creating a function
We're going to create a super simple function that will return a lightened value of a color.  In style2.scss, we're going to add a function that will take two arguments, background and value. We'll return the sum of those two arguments.
```
@function text-contrast($background, $value) {
  @return ($background + $value);
}
```


## 3. Using the function
Let's try this out on our .one paragraph.
```
.one {
  color: text-contrast(black, 120);
}
```

After the watcher compiles the css, you'll be able to view the change in the browser, and also see that in the Style2.css file, the value is now represented as a hex value:
```
.one {
  color: #787878; }
```

Note: There's already a similar built in function called lighten.  We'll build more useful functions in the next lesson.