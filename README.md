30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 20 [Installing and Using Sass Globbing](http://leveluptuts.com/tutorials/sass-tutorials/22-installing-and-using-sass-globbing)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup
You'll need to install Globbing.  It's another Ruby gem, so get to your command line and run:
```
gem install sass-globbing
```
We're also going to create a new directory inside the scss directory called variables.
In it, we'll create a scss partial called _colors.scss, where we'll place some color variables
```
$background-color: #fff;
$text-color: #333;
$link-color: #137bee;
$h1-color: #fff;
$h1-background-color: #137bee;
```
And one called _typography.scss, where we'll place some variables for text
```
$body-text-size: 14px;
$body-text-font: Arial, Helvetica, san-serif;
$h1-text-size: 20px;
```
We'll be using our index3.html and style3.scss files we used in the last lesson as well.

## 2. What is Globbing?
Sass globbing allows you to import many sass or scss files in a single import statement.

## 3. Updating the Config File
In config.rb, at the top of the document, we need to require the sass-globbing extension that we just installed.

 ```
require 'sass-globbing'
 ```
 After you modify the config file, you'll need to restart Compass on the command line:
 
```
compass watch
```
 
## 4. Globbing
Normally, we'd use an @import to import our _colors.scss partial, and we'd have to do another one for our _typography.scss partial. With globbing, we can import them all at once. Inside our style3.scss, we're going to import all the partials in our variables folder at the top of the file.
```
@import 'variables/*.*';
```
Note: In the video tutorial, it suggests using ```'variables/*'```, but that won't work on a Windows machine.  Use the ```*.*``` workaround if you are on Windows.

Now update your sass to use the new variables you've imported:
```
font-family: $body-text-font;
  font-size: $body-text-size;
  color: $text-color;
  .main {
    background-color: $background-color;
    margin:0 auto;
    width:80%;
    .header {
      background-color:$h1-background-color;
      color:$h1-color;
      overflow:hidden;
      padding:0 10px;
    }
  }
```

You've successfully imported all the scss files inside the variables directory.  But what if you had directories inside that directory, and you wanted to import all the files in those directories too? Let's create a brand directory inside the variables directory, and move the _colors.scss file inside of that. 

Now you'll need to update your import to reflect that you want to import not only the files inside the variables directory, but also the files inside any directories inside the variables directory,

```
@import 'variables/**/*.*';
```

 
## 5. Extra
If you're using node-sass, check out https://www.npmjs.com/package/grunt-sass-globbing 
