30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 20 [@Content - Better Media Queries in Sass](http://leveluptuts.com/tutorials/sass-tutorials/20-content-better-media-queries-sass)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup

Our files are getting a bit muddy, so let's start over today. We're going to create a new html file in the project root, index3.html:
```
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title>Sass!</title>
    <link rel="stylesheet" href="css/style3.css">
</head>
<body>
    <div class="main">
        <div class="header">
            <h1>RWD is a must!</h1>
        </div>
        <div class="content">
            <p>In today's world of multiple devices, incorporating RWD is a must.</p>
        </div>
    </div>
</body>
</html>
```

And let's create a new  empty style3.scss file in the scss directory.

## 2. What is @content?
@content allows you to use a mixin that wraps a block of content.  It's useful for things like media queries for responsive design. To learn more about media queries, [visit this article on Google's developer portal](https://developers.google.com/web/fundamentals/layouts/rwd-fundamentals/use-media-queries?hl=en)

## 3. Creating the mixin
In style3.scss, let's create a mixin that contains a media query for phones with a screen smaller than 480px. Inside the media query, we're going to add @content.  The @content will allow you to wrap your mixin around a block of code.

 ```
@mixin phone {
  @media only screen and (max-width:480px) {
    @content;
  }
}
 ```
 
 Let's use it now to make our mobile screen look different than our desktop screen.  For desktop, we only want our content to fill 80% of the screen, but on mobile, we want our content to fill the screen.  We also want to add just a bit of margin to the text content on the mobile.
 
 ```
body {
  margin:0;
  padding:0;
  font-family: Arial, Helvetica, sans-serif;
  .main {
    margin:0 auto;
    width:80%;
    .header {
      background-color:darkslateblue;
      color:#fff;
      overflow:hidden;
      padding:0 10px;
    }
  }
  @include phone {
    .main {
      width:100%;
    }
    .content {
      margin:10px;
    }
  }
}
 ```
 
 Now when we compile, you'll see this new output.  You can see that the css we wrote inside the @phone include is now wrapped in the media query that the @content was wrapped in. Pretty cool, huh?  You can test out your css in the browser to see that your desktop view is different than your mobile view by reducing your browser size to less than 480px.
 
 ```
body {
  margin: 0;
  padding: 0;
  font-family: Arial, Helvetica, sans-serif; }
  body .main {
    margin: 0 auto;
    width: 80%; }
    body .main .header {
      background-color: darkslateblue;
      color: #fff;
      overflow: hidden;
      padding: 0 10px; }
  @media only screen and (max-width: 480px) {
    body .main {
      width: 100%; }
    body .content {
      margin: 10px; } }
 ```
 
 
## 4. A note about scope
 Variable scope is at the level of the css you are calling the mixin, not from within the mixin itself.  That means you can't use any variables that you define inside the mixin.  They must be defined outside the mixin where you are calling it.
 
 For example, if you did this and defined the color variable in your mixin:
 ```
 @mixin phone($color:red) {
   @media only screen and (max-width:480px) {
     @content;
   }
 }
 ```
 And then tried to use that variable in the sass you are passing into @content like this:
 ```
   @include phone {
     .main {
       width:100%;
     }
     .content {
       margin:10px;
       color:$color;
     }
   }
 ```
 You'll get a sass compiler error - Undefined variable: "$color"
 Instead of defining it inside the mixin, you need to define it outside with the sass that is using the mixin.
 
## 5. Extra
 
 Experiment with variable scope, and read up on media queries if you aren't familiar with them.
 
 