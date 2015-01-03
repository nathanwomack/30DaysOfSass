30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 6: [Creating Configurable Shapes Using Mixins](http://leveluptuts.com/tutorials/sass-tutorials/6-creating-configurable-shapes-using-mixins)

## 1. Setup
Today we've got a new index.html file. Replace your current index.html with this:

 
 ```
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title>SASS is Nice</title>
    <link rel="stylesheet" href="css/style2.css">
</head>
<body>
    <header>
        <h1>Making Shapes</h1>
    </header>
    <div class="content">
        <a class="circle ir" href="#">Circle</a>
        <a class="triangle ir" href="#">Triangle</a>
    </div>
</body>
</html>
```

And you'll notice we're using a new stylesheet, so you'll want to create style2.scss with this. What's that weird font declaration on the ir (image replacement) class?  It's shorthand for setting font size to 0, line height to 0, and assigning a non-existent font named "a". Basically, the text in elements with this class won't display in the browser.

```
.circle {display:block; background:#333}
.triangle {display:block}

.ir {
  font: 0/0 a;
  text-shadow: none;
  color: transparent;
}

.clearfix:before, .clearfix:after {content:""; display:table}
.clearfix:after {clear:both}
.clearfix {zoom:1}
```

And most importantly, let's restart our sass watcher. This time, let's tell it to watch all files in the scss directory and output them to the css directory:

```
sass --watch scss:css
```
