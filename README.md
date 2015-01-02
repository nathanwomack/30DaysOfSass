30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 2: [The Basics of Variables in Sass](http://leveluptuts.com/tutorials/sass-tutorials/2-basics-variables-sass)

## 1. Setup
Create a basic html file named index.html.  Throw some typical html elements in there.

Create an empty directory named scss, and an empty file named style.scss inside it.

##2. Start sass watcher
On the command line, use this command:

```
sass --watch scss/style.scss:css/style.css
```

This command tells the sass watcher to watch the file before the colon, and output the file after the colon.

##3.  Add some CSS
Add some rules to style.scss.  The watcher will create style.css.  Make sure to include style.css into your html file.
Play around and watch it change as you save your changes to the .scss file.  Make sure you repeat a few colors, etc. in your rules so that you can see
how variables work in the next step.

##4. Create some variables for color
At the top of your .scss file, create a variable called $primary and assign it a color value.

```
$primary:#137bee
```

Then in your rules, replace the hex value of your color with $primary.

```
h1 {background-color:$primary}
```

Save your .scss file. The watcher will compile your changes into the .css file. Test it in the browser.  You can also view the .css file and see the changes in the compiled file.
If you are using WebStorm, remember you may have to sync the file to see the change in the .css file.

##5. Variables and math!
Create a padding variable set to 5px

```
$padding:5px
```

For your h1, set your rule to have the padding be equal to $padding.
For your h2, set your rule to have the padding be equal to $padding - 2px.

```
h1 {padding:$padding}
h2 {padding:$padding - 2px}
```

Save and compile, and look at your new .css file and your html in the browser. Notice that the compiled CSS file now has padding set at 3px - it did the math!
This also works with percentages.

##6. Changing color value with variables!
You can also use math to darken and lighten colors!
Create a new variable called $secondary, and set the value to $primary - 100.

```
$secondary:$primary - 100;
```

Set the background-color of your h2 to $secondary

```
h2 {background-color:$secondary}
```

Voila! Your h2 is now a darker shade of your h1.

Tips to play around with:

1. Subtracting makes colors darker, adding makes colors lighter.

2. Make sure that you have spaces before and after your + or -. If you don't have spaces, you'll get an error.

3. Try to name your variables for what they do, not for the values you give them.  For example, if you name your variable $blue, and your company updates all their colors to green, your variable name isn't going to make sense anymore. That's why it's a good idea to use names like $primary or $info or $warning that explain the purpose rather than the color.