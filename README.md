30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 20 [Installing Singularity Grid System](http://leveluptuts.com/tutorials/sass-tutorials/23-installing-singularity-grid-system)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup
You'll need to install Singularity.  It's another Ruby gem, so get to your command line and run:
```
gem install singularitygs
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

## 2. What is Singularity?
Singularity is a flexible grid system that you can use with Sass.  You can find out more at the [Singularity Wiki](https://github.com/at-import/Singularity/wiki)

## 3. Updating the Config File
In config.rb, at the top of the document, we need to require the singularity gem that we just installed.

 ```
require 'singularitygs'
 ```
 After you modify the config file, you'll need to restart Compass on the command line:
 
```
compass watch
```
 
## 4. Using Singularity
To use the Singularity mixins, you'll need to import it into your scss file.  In your style3.scss file, add this at the top of the file:
```
@import 'singularitygs';
```

 
## 5. Extra
Check out the [Singularity Wiki](https://github.com/at-import/Singularity/wiki).  Next lesson we'll use it to create a basic grid.
