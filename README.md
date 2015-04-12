30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 20 [Responsive Grids with Breakpoint](http://leveluptuts.com/tutorials/sass-tutorials/26-responsive-grids-breakpoint)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup
First of all, we need to install Breakpoint.  On your command line, run:
```
gem install breakpoint
```

Also, the five columns we had in the last lesson is a bit much. So we're going back to the html we had in lesson 24.
```
<body>
    <div class="main">
        <div class="header">
            <h1>Singularity is Sweet!</h1>
        </div>
        <div class="left-bar">
            <p>Jelly beans donut cotton candy tootsie roll. Cupcake croissant chocolate bar jujubes. </p>
        </div>
        <div class="content">
            <p>Jelly beans donut cotton candy tootsie roll. Cupcake croissant chocolate bar jujubes. Jelly beans sweet liquorice oat cake halvah. Cookie cake soufflé tiramisu. Powder lemon drops sweet roll cake biscuit gingerbread dessert. Carrot cake lemon drops pie sweet sweet roll chocolate cake.</p>
            <p>Topping ice cream dessert danish chocolate cake jelly beans cotton candy pastry gingerbread. Cake gingerbread apple pie apple pie tart tart gummi bears. Cotton candy oat cake jelly gummies pie. Cookie chocolate bar sweet chocolate cake icing macaroon donut fruitcake macaroon. Carrot cake jelly beans biscuit gummies. Soufflé cheesecake jujubes. Croissant sweet roll cake dragée jujubes cheesecake jelly tiramisu. Jelly bonbon caramels brownie croissant apple pie dessert.</p>
        </div>
    </div>
</body>
```
You can also remove classes one through five in your style3.scss file if you want to clean it up, and you should switch main's width back to 80%:
```
.main {
width: 80%;
```

And finally, we're going to modify our add-grid in the _grid.scss file back to what we had before:
```
@include add-grid(3 9);
```

## 2. Using Breakpoint
In the last two lessons, we used Singularity to build a grid. Unfortunately - it wasn't responsive. We need Breakpoint for that!

First, we need to add Breakpoint to the top of our config.rb file:
```
require 'breakpoint'
```
Next, we need to import Breakpoint at the top of our style3.css file:
```
@import 'breakpoint';
```

Remember you'll need to restart Compass with a ```compass watch``` command.  Notice that this time, you won't get any warnings about Breakpoint.

## 3. Setting Breakpoints
Right now, with no CSS for the left-bar and content areas, they lay out pretty decent when you shrink down to a mobile screen size - one stacking on top of the other nicely. Mobile first! We want to move them side by side when the screen gets larger. Basically, we're going to say "at a certain screen size, add these items to the grid." In your style3.scss file, use breakpoint to add your classes to the grid at 480px:
```
@include breakpoint (480px) {
  .left-bar {
    @include grid-span(1, 1);
  }
  .content {
    @include grid-span(1, 2);
  }
}
```

## 4. Extra
Play around with your breakpoint to determine what looks best - with so many devices at so many sizes, there is no magic number.  
