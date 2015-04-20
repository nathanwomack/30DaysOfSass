30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 20 [Juice - Mixins for Life](http://leveluptuts.com/tutorials/sass-tutorials/29-juice-mixins-life)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup
You'll need to install Juice. If you're using Bower, you can do that from the command line:

```
bower install juice
```

If you're not using Bower, you should check it out. It will make your life considerably easier :) 
If you're not using Bower and you don't want to figure that out right now, you can also clone the Juice repo: 

```
git clone git@github.com:kjbrum/juice.git
```

In style3.scss, you'll also want to import juice. If you used Bower, your import will look like this:

```
@import '/bower_components/juice/dist/juice';
```

If you didn't use bower, just update the path to wherever you placed the _juice.scss file.

IMPORTANT NOTE: You may want to make sure that you add your import line *before* the import for Singularity.  On my project, I started getting errors if it was below the Singularity import.

## 2. What is Juice?
Juice is a collection of mixins designed to make your life easier. To learn more about Juice, visit http://juicynex.us/juice/.

## 3. Juice Breakpoints
Juice has a really nice mixin for breakpoints that even contains some presets. Just as an example, let's set a breakpoint that changes the background color for small screens.
In style3.scss, inside the .main selector, replace the background-color rule with the bp mixin and pass the argument small:

```
  .main {
    @include bp(small) {
      background-color: #333;
      color: lightblue;
    }
  }
```


## 4. Single Side Border Radius
This mixin is pretty useful. It allows you to do a single side border radius in just one line. You can do top, bottom, left or right. Try it out on your .header selector:

```
    .header {
      /* existing css here */
      @include border-top-radius(15px);
    }
```


## 5. Single Transform

There are a number of shortcut mixins for transforms. As an example, let's throw a quick rotate on our left-bar class. This would be handy for throwing a "new" banner across the corner of a tile.
Other available shortcut transform mixins are: rotate, rotateX, rotateY, rotateZ, rotate3d, scale, scaleX, scaleY, scaleZ, scale3d, skew, skewX, skewY, translate, translateX, translateY, translateZ, translate3d
```
.left-bar {
      color:#fff;
      background-color: navy;
      border-radius: 10px;
      padding:10px;
      margin-top:10px;
      @include rotate(-15deg);
    }
```


## 6. Extra
Find out more about Juice at http://juicynex.us/juice/
