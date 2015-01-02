30DaysOfSass
============

30 days of Sass tutorials


# Day 1: [How to install Sass](http://leveluptuts.com/tutorials/sass-tutorials/1-how-install-sass)

## Install Ruby
 Check to see if you have Ruby installed by opening up a command line and typing `ruby -v`.  If you don't have it, [install it](http://rubyinstaller.org/).

## Install Gems
 Check to see if you have gem installed by typing in `gem -v`.  If you don't have it, [install it](https://rubygems.org/pages/download)

## Install Sass
 Install sass with this command line `gem install sass` - this may take a few minutes. Don't panic.

## Getting started

### Create style.scss
 Create a new file called style.scss.  This is the document you'll be editing.

### Tell Sass to watch the new file
 Tell sass to watch for a new scss file that you are naming style.scss with this command line:
 ```sass --watch style.scss:style.css```
 This will also create a new file called style.css, which is the compiled version of your style.scss file that will be readable by browsers.
 Sass is now watching your style.scss file, and will automatically compile and update style.css with your changes each time you save your .scss file.

### Try your first compiles
 Create a new rule in style.scss and save the document. Watch your command line window and see Sass compile it into style.css.
 You should now see that style.css has been updated with the rule you created in the .scss file.  If you are in WebStorm and don't see it, right click on the file
 and choose 'Synchronize', then you should be able to see it.





