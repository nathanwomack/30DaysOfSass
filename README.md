30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 4: [Using Mixins](http://leveluptuts.com/tutorials/sass-tutorials/4-using-mixins)

## 1. Setup
 You can continue with the files you used in Day 3, with a couple of minor modifications. (see branch Day_3)
 
 Add a div around the first paragraph that has a class of intro.
 
 ```
 <div class="intro">
   <p class="paragraph1">
   ...
   </p>
 </div>
```

You'll also want to give the intro class a background color, and add a hover state to your link with a background color as well.  Notice that we're using the nesting technique we learned in the last lesson.

```
.content {
  ...
  .intro {
    background-color:lightblue + 25;
    .paragraph1 {
      color:$primary;
      a {
        font-size:16pt;
        font-weight:bold;
        color:magenta;
      }
      a:hover {
        background:lightblue;
      }
    }
  }
}
```

 Start up sass from the command line:
 
 ```
 sass --watch scss/style.scss:css/style.css
 ```

## 2. What are mixins for, anyway?
Mixins are kind of like variables for bigger chunks of css, plus they can accept arguments. You can use mixins for things that you don't want to have to do over and over and over, like border-radius.

## 3. Writing a mixin
In this example, we'll create a mixin for those pesky border-radii. We'll name it border-radius. We'll pass it an argument we'll call $radius, and we'll give $radius a default value of 20px. Inside the mixin, we'll use $radius for the values.

```
@mixin border-radius($radius: 20px) {
  border-radius: $radius;
  -moz-border-radius: $radius;
  -webkit-border-radius: $radius;
}
```

## 4. Using a mixin with defaults
We can use that mixin in the rule for our .info selector by using @include followed by the name of the mixin:

```
...
.intro {
    @include border-radius;
    padding:10px;
...

## 5. Passing an argument to a mixin to override the defaults
We can also pass the mixin an argument, similar to the way we pass an argument in javascript, to change the defaults. Here we'll override that 20px radius with a 10px radius.

```
...
.intro {
    @include border-radius(10px);
    padding:10px;
...
```

```