30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 20 [Juice - Mixins for Life Part 2](http://leveluptuts.com/tutorials/sass-tutorials/30-juice-mixins-life-part-2)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup
No setup this time, just use the files you used in the last lesson.

## 2. Hoverer
Hoverer is a mixin that lets you pass in the property you want to change on hover, the initial value, and the hover value.  Let's make our left-bar element change background color on hover. Easy!

```
@include hoverer(background-color, navy, hotpink);
```

## 3. Responsive
Juice also has a really easy way to set different values for properties at different breakpoints. We should note that Juice is different than Singularity in that it doesn't consider mobile first.  The arguments in this mixin are:  property, base size value, medium size value, small size value. Let's use it to make our .header background get darker as our screen gets smaller.

```
.header {
    @include responsive(background-color, dodgerblue, navy, black);
}
```


## 4. Centerer, vert-centerer, cover
Centerer will center an element vertically and horizontally. Let's try this on our p elements in our offer elements. 
First, we need to put a position on our offer class, since centerer uses absolute positioning - otherwise they'll all end up stacked in the center of our screen.  Then we'll add centerer to center vertically and horizontally.  We also need to wipe out margin, otherwise it will be a little off center.
```
.offer {
  height:200px;
  background-color:lightblue;
  margin:5px 0;
  overflow:hidden;
  position:relative;
  p {
    color:lighten(lightblue, 10);
    font-weight:bold;
    font-size:1.5em;
    margin:0;
    padding:0;
    @include centerer;
  }
}
```

Centerer-vert does the same thing for vertical centering, and coverer will force an element to cover the entire screen or parent element.


## 5. Extra
There are lots more mixins, helpers and functions that you can learn more about at http://juicynex.us/juice/.  Some are super useful, and some really aren't, but I'd encourage you to go check them all out.
