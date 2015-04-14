30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 20 [Adding Columns at Breakpoints](http://leveluptuts.com/tutorials/sass-tutorials/27-adding-columns-breakpoints)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup
We need to add a little extra html to your index3.html file so we have more content to work with.  Below the content div, add this:
```
 <div class="offers">
    <div class="offer"><p>offer!</p></div>
    <div class="offer"><p>offer!</p></div>
    <div class="offer"><p>offer!</p></div>
</div>
```

Also, let's add some css for those offer divs in style3.scss:
```
.offer {
  height:200px;
  background-color:lightblue;
  margin:5px 0;
  overflow:hidden;
  p {
    color:lighten(lightblue, 10);
    font-weight:bold;
    font-size:1.5em;
    margin:40px;
    text-align:center;
  }
}
```

## 2. Adding Grids at Breakpoints
So in the last lesson, we made a basic responsive grid.  But what if we wanted to totally change things at multiple specific breakpoints? Breakpoint lets us do that.
Breakpoint thinks in terms of mobile first, so our first grid is what the user will see at our smallest size. From there, we increase in screen size, smallest to largest.

In our _grid.scss file, let's replace the add-grids with these. The first, which is our smallest screen size, is a grid of one column.  It's the default. When the screen is at least 768px, we're going to change to two column grid of 3 and 9, and at 1140px we're going to change to a three column grid of 2, 6 and 4.
```
@include add-grid(1);
@include add-grid(3 9 at 768px);
@include add-grid(2 6 4 at 1140px);
```

Since we've updated our grids, we need to update our style3.css as well. We don't really need that 480px breakpoint anymore, so we'll remove that.

At 768px, we want left-bar to take up one column and go in the first position.  The content div will also take up one column, and go in the second position. And let's have the offers div also take up one column and go in the second position, right below the content.

At 1140px, we'll move things around a bit. We'll keep the left-bar and content divs the same, but move the offers div into the 3rd position.

```
@include breakpoint (768px) {
  .left-bar {
    @include grid-span(1, 1);
  }
  .content {
    @include grid-span(1, 2);
  }
  .offers {
    @include grid-span(1, 2);
  }
}
@include breakpoint (1140px) {
  .left-bar {
    @include grid-span(1, 1);
  }
  .content {
    @include grid-span(1, 2);
  }
  .offers {
    @include grid-span(1, 3);
  }
}
```


## 4. Extra
Play around with your breakpoints to determine what looks best - with so many devices at so many sizes, there is no magic number.  
