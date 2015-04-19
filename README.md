30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 20 [Selector Functions and Sass 3.4](http://leveluptuts.com/tutorials/sass-tutorials/28-selector-functions-sass-34)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup
If you've been following along via my writeups, you already have Sass 3.4 installed.  But if you're not sure, type this into the command line to see which version of Sass you have: 
```
sass --v
```

## 2. Selector-append

Selector-append allows you to create a new selector by appending a suffix to a list of selectors.  Depending on how you name things, this could be useful for applying styles to groups of similar elements.

In style3.scss, try this:
```
#{selector-append(('.btn','.header'),'-link')} {
  text-decoration: underline;
  text-transform: uppercase;
}
```
In your output, you'll see:
```
.btn-link, .header-link {
  text-decoration: underline;
  text-transform: uppercase;
}
```

## 3. Selector-nest

Selector-nest is similar, but it allows you to create a new nested selector:

```
#{selector-nest('.btn, .header', '.link')}{
  color:red;
}
```

Output:
```
.btn .link, .header .link {
  color: red;
}   
```

If your output doesn't look right on this one, check where you've got your quotes. The list of selectors you want to nest outside '.link' goes in one set quotes, and the class you want to nest inside them goes in the next set of quotes.


## 4. Selector-unify

Selector-unify returns a selector that matches only elements matched by both selectors.

```
#{selector-unify('.btn, .header', '.link')}{
  color:red;
}
```

Output:
```
.btn.link, .header.link {
  color: red;
}
```

## 5. Extra
Find out more about selector functions at http://sass-lang.com/documentation/file.SASS_CHANGELOG.html#selector_functions 
