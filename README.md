30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 20 [Asymmetric Grids with Singularity](http://leveluptuts.com/tutorials/sass-tutorials/25-asymmetric-grids)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup
We're going to modify our html file a little. We're going to remove the first div containing text, and duplicate the second one so that we have five of them. Then we're going to add a unique class to each one. In this case, the class names are one, two, three, four, and five.

```
<body>
    <div class="main">
        <div class="header">
            <h1>Singularity is Sweet!</h1>
        </div>
        <div class="one">
            <p>Jelly beans donut cotton candy tootsie roll. Cupcake croissant chocolate bar jujubes. Jelly beans sweet liquorice oat cake halvah. Cookie cake soufflé tiramisu. Powder lemon drops sweet roll cake biscuit gingerbread dessert. Carrot cake lemon drops pie sweet sweet roll chocolate cake.</p>
            <p>Topping ice cream dessert danish chocolate cake jelly beans cotton candy pastry gingerbread. Cake gingerbread apple pie apple pie tart tart gummi bears. Cotton candy oat cake jelly gummies pie. Cookie chocolate bar sweet chocolate cake icing macaroon donut fruitcake macaroon. Carrot cake jelly beans biscuit gummies. Soufflé cheesecake jujubes. Croissant sweet roll cake dragée jujubes cheesecake jelly tiramisu. Jelly bonbon caramels brownie croissant apple pie dessert.</p>
        </div>
        <div class="two">
            <p>Jelly beans donut cotton candy tootsie roll. Cupcake croissant chocolate bar jujubes. Jelly beans sweet liquorice oat cake halvah. Cookie cake soufflé tiramisu. Powder lemon drops sweet roll cake biscuit gingerbread dessert. Carrot cake lemon drops pie sweet sweet roll chocolate cake.</p>
            <p>Topping ice cream dessert danish chocolate cake jelly beans cotton candy pastry gingerbread. Cake gingerbread apple pie apple pie tart tart gummi bears. Cotton candy oat cake jelly gummies pie. Cookie chocolate bar sweet chocolate cake icing macaroon donut fruitcake macaroon. Carrot cake jelly beans biscuit gummies. Soufflé cheesecake jujubes. Croissant sweet roll cake dragée jujubes cheesecake jelly tiramisu. Jelly bonbon caramels brownie croissant apple pie dessert.</p>
        </div>
        <div class="three">
            <p>Jelly beans donut cotton candy tootsie roll. Cupcake croissant chocolate bar jujubes. Jelly beans sweet liquorice oat cake halvah. Cookie cake soufflé tiramisu. Powder lemon drops sweet roll cake biscuit gingerbread dessert. Carrot cake lemon drops pie sweet sweet roll chocolate cake.</p>
            <p>Topping ice cream dessert danish chocolate cake jelly beans cotton candy pastry gingerbread. Cake gingerbread apple pie apple pie tart tart gummi bears. Cotton candy oat cake jelly gummies pie. Cookie chocolate bar sweet chocolate cake icing macaroon donut fruitcake macaroon. Carrot cake jelly beans biscuit gummies. Soufflé cheesecake jujubes. Croissant sweet roll cake dragée jujubes cheesecake jelly tiramisu. Jelly bonbon caramels brownie croissant apple pie dessert.</p>
        </div>
        <div class="four">
            <p>Jelly beans donut cotton candy tootsie roll. Cupcake croissant chocolate bar jujubes. Jelly beans sweet liquorice oat cake halvah. Cookie cake soufflé tiramisu. Powder lemon drops sweet roll cake biscuit gingerbread dessert. Carrot cake lemon drops pie sweet sweet roll chocolate cake.</p>
            <p>Topping ice cream dessert danish chocolate cake jelly beans cotton candy pastry gingerbread. Cake gingerbread apple pie apple pie tart tart gummi bears. Cotton candy oat cake jelly gummies pie. Cookie chocolate bar sweet chocolate cake icing macaroon donut fruitcake macaroon. Carrot cake jelly beans biscuit gummies. Soufflé cheesecake jujubes. Croissant sweet roll cake dragée jujubes cheesecake jelly tiramisu. Jelly bonbon caramels brownie croissant apple pie dessert.</p>
        </div>
        <div class="five">
            <p>Jelly beans donut cotton candy tootsie roll. Cupcake croissant chocolate bar jujubes. Jelly beans sweet liquorice oat cake halvah. Cookie cake soufflé tiramisu. Powder lemon drops sweet roll cake biscuit gingerbread dessert. Carrot cake lemon drops pie sweet sweet roll chocolate cake.</p>
            <p>Topping ice cream dessert danish chocolate cake jelly beans cotton candy pastry gingerbread. Cake gingerbread apple pie apple pie tart tart gummi bears. Cotton candy oat cake jelly gummies pie. Cookie chocolate bar sweet chocolate cake icing macaroon donut fruitcake macaroon. Carrot cake jelly beans biscuit gummies. Soufflé cheesecake jujubes. Croissant sweet roll cake dragée jujubes cheesecake jelly tiramisu. Jelly bonbon caramels brownie croissant apple pie dessert.</p>
        </div>
    </div>
</body>
```

## 2. Why Asymmetrical Grids?
In the last lesson, we built a 12 column grid, but we really only had two elements - one that spanned 3 columns and one that spanned 9.  So what was the point of setting up all 12 columns? In this lesson, we'll learn how to use Asymmetrical Grids so that we aren't creating columns we don't really need.

## 3. Setting Up the Grid
In your _grid.scss file, we're going to modify the add-grid. This time, we're going to do five columns. The first is 1 grid wide, the second is 2 grids wide, and so on.  

Note: The video tutorials use the Singularity 1.0 syntax.  I've updated this walkthrough to use the Singularity 1.2+ syntax, which is slightly different.  As of the date of this tutorial, both syntaxes will work. 

 ```
@include add-grid(1 2 3 4 5);
 ```
 
 In our index3.scss file, we're going to update our .main selector's width to 1440px and add selectors for our one through five classes. 
 The grid-span takes two numbers.  The first is the number of columns wide, the second is which position it should start at.
 
 ```
.main {
    background-color: $background-color;
    margin:0 auto;
    width:1440px;
    .header {
      background-color:$h1-background-color;
      color:$h1-color;
      overflow:hidden;
      padding:0 10px;
    }
    .one {
      @include grid-span(1, 1);
    }
    .two {
      @include grid-span(1, 2);
    }
    .three {
      @include grid-span(1, 3);
    }
    .four {
      @include grid-span(1, 4);
    }
    .five {
      @include grid-span(1, 5);
    }
  }
 ```
 
 Now when you refresh your html in a browser, you should see five columns of content, and they should get wider as they go across.  
 
 Note: You will probably see a warning in the watcher that lets you know that you'll need Breakpoint for responsive contexts.  This grid isn't responsive, but we'll cover Breakpoints in a future lesson.
 

## 4. Extra
Check out the [Singularity Wiki for more info on Asymmetrical Grids](https://github.com/at-import/Singularity/wiki/Creating-Grids#asymmetric-grids).  
