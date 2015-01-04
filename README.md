30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 7 [@import and Parent Reference](http://leveluptuts.com/tutorials/sass-tutorials/7-import-parent-reference)

## 1. Setup
Today we'll be building on the files we used in previous lessons. You'll need to rename your style.scss file to "_style.scss"

## 2. @import
First, we'll import our _style.scss file into our style2.scss file. Using separate files and the @import functionality allows you to organize your stylesheets. You may want to keep all your mixins in one file, or all your variables in another. How you organize is up to you, but @import makes it easier.  Notice that we don't use the underscore or the .scss in the filename when we import. The semi-colon is also important, the watcher will error without it. Here's what you'll add to the top of your style2.scss file:

```
@import "style";
```

When you look at your newly compiled style2.css file, you'll see it now has all the style rules from _style.scss as well. You'll also notice that the watcher did not generate a _style.css file. That's because it has an underscore, and will only be used for imports.

## 3. Parent Reference
Let's make our circle change colors on hover. Rather than create a separate ruleset for hover, we're going to use a shortcut and nest the hover inside our circle class, like this using an ampersand:

```
.circle
  {@include circle(100px,#333);
  &:hover {background:red;}
}
```

