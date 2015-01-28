30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 16 [While Loops](http://leveluptuts.com/tutorials/sass-tutorials/16-while-loops)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup
Minor setup today. Just comment out that for loop we created in the previous lesson.
Tip: if you're using WebStorm, the quickest way to comment out a block of code is to highlight it and hit CTRL+/
Note that when you comment out something in the .scss file, it just doesn't process anything.  You won't get commented out css in your .css file - it just won't even output.
```
//@for $i from 1 through 4 {
//  .par-#{$i} {
//    margin:10px * $i;
//  }
//}
```


## 2. Using For Loops
We're going to do the same thing we did the last lesson, except this time we're going to use a while loop instead of a for loop.  First, we have to define the variable $i. We'll set it to 1.  Then we set the while condition ($i < 5), and we also need to manually increment $i as well.

```
$i : 1;
@while $i < 5 {
  .par-#{$i} {
    margin: 10px * $i;
  }
  $i : $i + 1;
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

##2 Another example
This time, let's replace that @each loop.  Comment out the @each we wrote before.
```
//@each $p in (
//  one: red + 100,
//  two: red + 50,
//  three: red - 50,
//  four: red - 100
//) {
//  .#{nth($p,1)} {
//    background:#{nth($p,2)};
//    @include border-radius(10px);
//    padding:10px;
//    color:text-contrast(nth($p,2));
//  }
//}
```

Let's add to the existing while loop we created. 
We're going to add another variable for background, we'll call it a horrible name like parbg. In our while loop, we'll set our background color to parbg.
We'll also set our color using the text-contrast function we wrote, and parbg for the color argument.
Finally, we'll lighten parbg so that it's a little bit lighter next time through the loop.

```
$i : 1;
$parbg : darkred;
@while $i < 5 {
  .par-#{$i} {
    margin: 10px * $i;
    background-color:$parbg;
    color:text-contrast($parbg);
    $parbg : lighten($parbg, 20%);
    @include border-radius(10px);
    padding:10px;
  }
  $i : $i + 1;
}
```

## Extras
Think of a better way to use for loops than naming your paragraphs like this.  :P