30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 2: [Nesting Your Sass](http://leveluptuts.com/tutorials/sass-tutorials/3-nesting-your-sass)

## 1. Setup
 You can continue with the files you used in Day 2, with a couple of minor modifiations. (see branch Day_2)
 
 Inside the content div, add a second h2, add a class to the first p, and add an anchor around the first word in the paragraph.
 
 ```
     ...
     <div class="content">
     <h2>this is another h2</h2>
     <p class="paragraph1"><a href="#">Dragée</a>
     ...
 ```

 
 Start up sass from the command line:
 
 ```
 sass --watch scss/style.scss:css/style.css
 ```

## 2. Nesting
Instead of creating new rules for specific elements and classes inside of the content div, you can nest those rules right inside of the rule for the content class. This organizes things nicely.

```
.content {
  width:60%;
  margin:$margin;
  padding:$padding;
  h2 {
    background-color:$secondary + 50;
  }
  .paragraph1 {
    color:$primary;
    a {
      font-size:16pt;
      font-weight:bold;
      color:magenta;
    }
  }
}
```