30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 12 [Build Your Own Function Part 2: If/Else](http://leveluptuts.com/tutorials/sass-tutorials/12-build-your-own-function-part-2-if-else)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup
No setup today, you can use the files you have that you created in Day_11.


## 2. Updating the text-contrast Function
We're going to modify our text-contrast function we wrote in the last lesson. Eventually, we're going to use some if/else logic so that it will create a nice contrast based on how light or dark the background is. First, let's update what we did last time to use that built in lighten function we mentioned in the note at the end of the last lesson.  It only needs one argument, so we're going to drop the value argument, use the lighten function,and update the rule for our .one class so it only passes one argument.

```
@function text-contrast($background) {
  @return lighten($background,70);
}
.one {
  color: text-contrast(black);
}
```


## 3. Using if/else
Now we're going change our text-contrast function using the built in lightness function, which tells us the lightness percentage of a color, and use if logic to determine whether we should lighten or darken the text color accordingly.
```
@function text-contrast($background) {
  @if lightness($background) < 50% {
    @return lighten($background,70%);
  } @else {
    @return darken($background,70%);
  }
}
```

To test it out, change the css for the .one selector to be white instead of black.  Remember, we've got css for that in a couple of places.  Here:
```
.one {
  color: text-contrast(white);
}
```
and here in that @each loop we wrote a while back:
```
@each $p in (
  one: white,
```

## Extras
For fun, try out other colors.  Next lesson we'll incorporate this into our @each loop to make it even more useful.