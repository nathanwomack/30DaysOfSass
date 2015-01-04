30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 5: [Selector Inheritance (@extend)](http://leveluptuts.com/tutorials/sass-tutorials/5-selector-inheritance)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup
 You can continue with the files you used in Day 4, with a couple of minor modifications. (see branch Day_4)
 
 Add a div around the second paragraph that has a class of feature, and add the paragraph1 class to the second paragraph.  I know, we named our classes poorly. We should do better next time. 
 
 ```
 <div class="feature">
   <p class="paragraph1">
   ...
   </p>
 </div>
```

## 2. Using @extend for Selector Inheritance
Have you ever had a selector where you wanted all of the declarations for a rule you wrote for another selector, plus maybe one or two more? The @extend functionality of Sass helps you do that.

Let's give the feature class all of the declarations from the intro class, plus add a border.  Remember to nest .feature inside of content, just like you did for .intro.

```
.feature {
    @extend .intro;
    border:1px solid lightblue - 100;
  }
```

Now look at your compiled .css file.  See what that did there?  Everywhere there was a ruleset for .intro, it also added in .feature. You just saved a lotta typing.  You're getting rather clever. :)