30DaysOfSass
============

30 days of Sass tutorials

Check the branches for each day

# Day 8 [Using Lists and @each](http://leveluptuts.com/tutorials/sass-tutorials/8-using-lists-and-each)
How this all works:  If you want to, you can just watch the video linked above at leveluptuts.com. Or, if you're more of a reader than a watcher, I've recapped the video tutorials here, and added a few thoughts of my own. Keep in mind that I kind of named things differently, etc. so if you're trying to watch the video AND do these walkthroughs at the same time, you might get a bit confused. You don't need to grab all the files - the files for each branch are the completed lesson files. So unless you get stuck, you shouldn't need to snag everything, just read the README and follow along.

## 1. Setup
Today we'll be building on the files we used in previous lessons. We'll want to use the same html we used in the first 5 lessons, so I copied the index.html from Day 5 into a new file I called index2.html. We'll also make a couple of other changes. First, change the stylesheet to point at style2.css instead of style.css.  Second, add this list of social links to your header:

```
<ul class="socialLinks">
    <li><a class="twitter" href="#">Twitter</a></li>
    <li><a class="facebook" href="#">Facebook</a></li>
    <li><a class="youtube" href="#">YouTube</a></li>
    <li><a class="rss" href="#">RSS</a></li>
</ul>
```

We also need to add a bit of css to our style2.scss file:
```
ul.socialLinks {
  display:block;
  overflow:hidden;
  li {
    list-style: none;
    a {
      display: block;
      float: left;
      margin-right:5px;
      height: 32px;
      width: 32px;
    }
  }
}
```

I also created an img directory and added an icon for each list item into it. These icons are a little bit, but I was too lazy to photoshop, and for this example we'll just resize with css. Not a best practice, I know. If you wanna resize them properly, feel free. The images are: twitter.png, facebook.png, youtube.png, and rss.png.

## 2. Lists
Let's declare list called icons.
```
$icons: (twitter,facebook,youtube,rss);
```

## 3. @each
Now we're going to use @each to loop through that list and create a ruleset for each icon in the list.
We create a new variable we call $social, and for each item in the list, we create a new ruleset where #{$social} will be replaced with an item in the list.
```
  @each $social in $icons {
    .#{$social} {
      background: url('../img/#{$social}.png') no-repeat;
      background-size:32px;
      text-indent:-999px;
    }
  }
```

Now check out your style2.css file. You can see that Sass generated a ruleset for each icon.
