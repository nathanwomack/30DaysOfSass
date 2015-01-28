30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 13 [Build Your Own Function Part 3: Total Automation with lists](http://leveluptuts.com/tutorials/sass-tutorials/13-build-your-own-function-part-3-total-automation-lists)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup
One minor change today - you can delete the ruleset you create in style2.scss for the .one class.  You won't be needing it after we automate today.


## 2. Updating our @each to use the text-contrast function
Today we're going to use our text-contrast function inside our @each loop.
First, I updated the list.  I decided to go with some different reds today.  Feel free to use other colors if you'd like.
Second, I updated the color rule to use our text-contrast function.
Note: if you're text-contrast function isn't compiling properly, make sure that your function is higher up in the code than the place that you are calling it.

```
@each $p in (
  one: red + 100,
  two: red + 50,
  three: red - 50,
  four: red - 100
) {
  .#{nth($p,1)} {
    background:#{nth($p,2)};
    @include border-radius(10px);
    padding:10px;
    color:text-contrast(nth($p,2));
  }
}
```


## Extras
For fun, try out other colors. 