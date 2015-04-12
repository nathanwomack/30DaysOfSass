30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 20 [Creating and Using Symmetrical Grid with Singularity](http://leveluptuts.com/tutorials/sass-tutorials/24-creating-and-using-symmetrical-grid)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup
We're going to modify our html file a little so we have some content to put into the grid:

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

## 2. What is Singularity?
Singularity is a flexible grid system that you can use with Sass.  You can find out more at the [Singularity Wiki](https://github.com/at-import/Singularity/wiki)
Today, we'll be using Singularity to create a basic 960 grid.  It won't be responsive, but it will give you a basic idea of what Singularity can do.

## 3. Setting Up the Grid
In the variables directory, create a new partial called _grid.scss.  We'll add some grid variables to this file. We want 12 columns in our grid, so we will set a $grids variable to 12. 

Singularity helps you build gutters between your columns.  It's important to note that Singularity doesn't add gutters to the far left or the far right of the outside of your grid. We want the gutters for each of our columns to total up to 1/3 of the column width.  If we have a 960px grid, each column will end up being 60px. 1/3 of 60px is 20px, and that's split between the left and right gutter for each column, so our gutters will end up being 10px wide. The math is explained a little better in the link below.

Note: The video tutorials use the Singularity 1.0 syntax.  I've updated this walkthrough to use the Singularity 1.2+ syntax, which is slightly different.  As of the date of this tutorial, both syntaxes will work. https://github.com/at-import/Singularity/wiki/Creating-Grids#symmetric-grids 

 ```
@include add-grid(12);
@include add-gutter(1/3);
 ```
 
 In our index3.scss file, we're going to update our .main selector's width to 960px and add selectors for .left-bar and .content.  We want the left-bar to be 3 columns wide, and start in the first grid position. We want the content div to be 9 columns wide and start in the 4th position.
 
 ```
.main {
    background-color: $background-color;
    margin:0 auto;
    width:960px;
    .header {
      background-color:$h1-background-color;
      color:$h1-color;
      overflow:hidden;
      padding:0 10px;
    }
    .left-bar {
      @include grid-span(3, 1);
    }
    .content {
      @include grid-span(9, 4)
    }
}
 ```
 
 Now when you refresh your html in a browser, you should see two columns of content.
 
 Note: You will probably see a warning in the watcher that lets you know that you'll need Breakpoint for responsive contexts.  This grid isn't responsive, but we'll cover Breakpoints in a future lesson.
 

## 4. Extra
Check out the [Singularity Wiki for more info on Symmetrical Grids](https://github.com/at-import/Singularity/wiki/Creating-Grids#symmetric-grids).  
