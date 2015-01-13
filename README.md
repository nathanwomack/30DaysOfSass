30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 10 [Built in Functions](http://leveluptuts.com/tutorials/sass-tutorials/10-built-functions)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup
One minor change today, you can use the same files you previously used in Day 9 with this small addition:  add a class of .feature to the div that contains the one, two, three, and four paragraphs:
```
<div class="feature">
  <p class="one">...</p>
  <p class="two">...</p>
  <p class="three">...</p>
  <p class="four">...</p>
</div>
```


## 2. rgba Function
The rgba function accepts two arguments, a color value and an alpha value, and turns it into an rgba value. Let's try it with the background color for .intro in _style.scss.  Our previous color was lightblue + 25, and we'll use an alpha of .3:
```
background-color:rgba(lightblue + 25,.3);
```

After the watcher compiles the css, you'll be able to view the change in the browser, and also see that in the Style2.css file, the value is now represented as an rgba value:
```
background-color: rgba(198, 241, 255, 0.3);
```


## 2. fade-out Function
The fade-out function is similar. It also accepts two arguments, a color value and an alpha value, and turns it into an rgba value. Let's try it with the background color for .intro in _style.scss.  Let's try a new color red, and we'll use an alpha of .5:
```
background-color:fade-out(red,.5);
```

After the watcher compiles the css, you'll be able to view the change in the browser, and also see that in the Style2.css file, the value is now represented as an rgba value:
```
background-color: rgba(255, 0, 0, 0.5);
```

## 3. percentage Function
Percentage is useful for taking pixel units and translating them into percentages for fluid layouts. For example, if a designer gives you a layout that is 1440px wide.  The design has a left sidebar that needs to be 550px, and the main content area should be 890px wide.  You want the layout to be fluid, but still retain the proportions given to you by the designer.  Let's try this out with our .intro and .feature selectors.  In _style.css, add a width to .intro using the percentage function like this:
```
width: percentage(550px/1440px);
float:left;
```

After the watcher compiles the css, you'll be able to view the change in the browser, and also see that in the Style2.css file, the value is now represented as an rgba value:
```
width: 38.19444%;
```

Now try adding a new ruleset for .feature like so:
```
.feature {
  width: percentage(890px/1440px);
  float:right;
}
```

You may need to remove some margins or padding to get them to align properly next to each other, but you get the idea.

## 4. Nesting functions
You can also nest functions.  If you have an aversion to lots of decimal points, you could always wrap your percentage function in a round function:

```
width: round(percentage(550px/1440px));
```

Which produces this:
```
width: 38%;
```

## 5. Extras
[Check out all the internal Sass functions here](http://sass-lang.com/documentation/Sass/Script/Functions.html) and run some experiments of your own!
