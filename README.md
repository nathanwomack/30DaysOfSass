30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 9 [Nth Function in Lists](http://leveluptuts.com/tutorials/sass-tutorials/9-nth-function-lists)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup
Easy setup today - in index2.html from last lesson, make sure you have 4 paragraph elements in the div that has class="feature" - you can also remove the "feature" class on that div.  Each paragraph should have a class that represents its number:
```
<p class="one">...</p>
<p class="two">...</p>
<p class="three">...</p>
<p class="four">...</p>
```

## 2. Using Nth Function
Today we're going to add a progressively lighter background color to each of the paragraphs in the feature div.

We start with an @each directive again.  This time, instead of defining our list first like we did last time, we're going to define a map we're calling inside the @each.  A map is kind of like a list, but it contains key:value pairs.
A map can be used anywhere a list can (like in an @each directive) - when used by a list function, a map is treated as a list of pairs.

We're going to loop through the pairs in the map with #each and use nth to write our selectors.  Nth lets us get an item from a specific position in a list - remember the map is a list of pairs - essentially a list of lists.
So, for each map item, we're going to create a ruleset that uses the first value in the pair (one, two, three, or four) as the class name, and uses the second value in the pair (black, black + 40, etc.) as the value for the background color.

```
@each $p in (
  one: black,
  two: black + 40,
  three: black + 80,
  four:black + 120
) {
  .#{nth($p,1)} {
    background:#{nth($p,2)};
    @include border-radius(10px);
    padding:10px;
    color:#fff;
  }
}
```

Notice anything weird??  *Sass indexes start at 1, not zero.*  So if you wanted to grab the 3rd item in list z, your sass would be:

```
$z: (one,two,three);
nth($z,3)
```


## 3. Extras
Find out more about [lists](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#lists) and [maps](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#maps) in Sass.