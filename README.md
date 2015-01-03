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
.circle {display:block}
.triangle {display:block}

.ir {
  font: 0/0 a;
  text-shadow: none;
  color: transparent;
}
```

And most importantly, let's restart our sass watcher. This time, let's tell it to watch all files in the scss directory and output them to the css directory:

```
sass --watch scss:css
```

## 2. Creating the circle mixin
Let's create a new mixin called circle that accepts a size argument and a color argument. We won't worry about setting defaults this time, but you can if you want to. What this mixin is doing is creating a circle by creating a border radius that is half the size of the height and width.


```
@mixin circle($size,$color) {
  -webkit-border-radius: $width/2;
  -moz-border-radius: $width/2;
  border-radius: $width/2;
  height:$width;
  width:$width;
  background-color:$color;
}
```

## 3. Use the circle mixin
Add the circle mixin to the .circle anchor. Pass in the width and color that you want your circle to be.

```
.circle {display:block; @include circle(100px,#333)}
```

## 4.  Creating the triangle mixin
Now let's create the triangle mixin. We want to make it flexible, so let's give it size, direction and color arguments. By setting the borders to half the size we want, and setting the borders on two sides transparent, the borders will form a nice little triangle.

```
@mixin triangle($size,$direction,$color) {
  @if $direction == 'up' {
    width:0;
    height:0;
    border-left:$size/2 solid transparent;
    border-right:$size/2 solid transparent;
    border-bottom:$size/2 solid $color;
  } @elseif $direction == 'down' {
    width:0;
    height:0;
    border-left:$size/2 solid transparent;
    border-right:$size/2 solid transparent;
    border-top:$size/2 solid $color;
  } @elseif $direction == 'right' {
    width:0;
    height:0;
    border-top:$size/2 solid transparent;
    border-bottom:$size/2 solid transparent;
    border-left:$size/2 solid $color;
  } @elseif $direction == 'left' {
    width:0;
    height:0;
    border-top:$size/2 solid transparent;
    border-bottom:$size/2 solid transparent;
    border-right:$size/2 solid $color;
  }
}
```

## 5. Use the triangle mixin
Add the triangle mixin to the .triangle anchor. Pass in the size, direction and color that you want your triangle to have.

```
.triangle {display:block; @include triangle(100px,'up',#333)}
```

## 6. Extras - during setup, we did some repeating. How could you use Sass to avoid repetition in your scss file and extra classes in your html?  hint: what can you do with .ir?