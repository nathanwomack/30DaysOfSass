30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 20 [Extending Sass and Writing a Compass Config File](http://leveluptuts.com/tutorials/sass-tutorials/21-extending-sass-and-writing-config-file)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup
First of all, if you haven't installed Compass yet, you'll need to do that.
On the command line enter
```
gem install compass
```

It may take a few minutes to install.

We can use the same files that we used in the last lesson, but before we start let's add a couple of things in the root of our project:
* An empty config.rb file
* A fonts directory
* A js directory

## 2. What is Compass?
Compass is a collection of mixins and tools that help us build sites easier. To learn more about Compass, visit http://compass-style.org/

## 3. Building the Config File
In config.rb, let's set up our configuration.  Our project_type is stand_alone. We set the http_path as the root of our project. We list out our directory paths to the scss, css, img, fonts, and js directories. We turn line comments off.  Because we are using .scss files, our preferred syntax is scss. We want the expanded style for our css output, and we set relative_assets to true to indicate that the compass helper functions should generate relative urls from the generated css to assets.  You can find a full list of config options at http://compass-style.org/help/documentation/configuration-reference/

 ```
project_type = :stand_alone
http_path = "/"
sass_dir = "scss"
css_dir = "css"
images_dir = "img"
fonts_dir = "fonts"
javascripts_dir = "js"
line_comments = false
preferred_syntax = :scss
output_style = :expanded
relative_assets = true
 ```
 
## 4. Start Up Compass and Test it Out
 Now that we have Compass installed and configured, we're going to use that as our compiler.  We will no longer use "sass --watch scss:css" to turn on the watcher.
 To test it out, delete all the .css files inside your css directory, then enter this on the command line:
 
 ```
 compass watch
 ```
 You'll see Compass regenerate your css files.  
 
## 5. Extra
Read up more about Compass and it's config options at http://compass-style.org/
