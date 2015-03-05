30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 19 [Placeholder Selectors](http://leveluptuts.com/tutorials/sass-tutorials/19-placeholder-selectors)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup

No setup needed today, you can use the same files you've used in previous lessons.

## 2. What's a Placeholder Selector?
A placeholder selector is a way for you to write selectors that you can reuse in other selectors. If they are not used via @extend, they won't produce any output when compiled. This makes them a nice choice for situations where you are writing a framework or something and you want to offer choices that your users can use if they choose to, but won't add to the css filesize if they don't.

## 3. Creating a Placeholder Selector
In _style.scss, let's create a placeholder selector that would apply a border and some padding to paragraph elements. Placeholder selectors look a lot like regular selectors, but they don't use the . or # like classes and ids.  Instead, we use a % sign to indicate it as a placeholder selector.

 ```
%border p {
  border:1px solid white;
  padding:5px;
}
 ```
 
 When you run the compiler, notice that there is no new output produced in the .css file. That's because we've created the placeholder selector, but we haven't used it yet.
 Let's use it now by extending the .feature selector:
 
 ```
 .feature {
     @extend .intro;
     width: round(percentage(890px/1440px));
     float:right;
     @extend %border;
   }
 ```
 
 Now when we compile, you'll see this new output, and you'll see the border applied when you refresh your html page in the browser:
 
 ```
 .content .feature p {
   border: 1px solid white;
   padding: 5px; }
 ```
 
 
## 4. So how is this different from a mixin?
 There are a couple of ways that placeholder selectors are different than mixins. 
 
 First, placeholder selectors can't be passed a variable - that makes mixins the way to go if you need something to be context specific or variable based.
 
 Secondly, the output is different.  The CSS output for placeholder selectors is more concise.
 
 Here's a mixin included in two selectors, and the output it produces:
 
 ```
 @mixin border {
   border:1px solid white;
 }
 p {
   @include border;
 }
 span {
   @include border;
 }
 ```
 
 ```
 p {
   border:1px solid white;
 }
 span {
   border:1px solid white;
 }
 ```
 
 Here's what the output looks like using placeholder selectors:
 
  ```
  %border {
    border:1px solid white;
  }
  p {
    @extend %border;
  }
  span {
    @extend %border;
  }
  ```
  
  ```
  p, span {
    border:1px solid white;
  }
  ```
 
 So, a good rule of thumb would be: unless you need to pass variables (for example, if you wanted to pass border color), use placeholder selectors instead of mixins and you'll have smaller css files.
 
 