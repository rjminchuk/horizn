# Horizn

###### A landscape focused strategy for blogging. 

Horizn's focus is to make the web's digital publication format more paletable to users of all device sizes. Showing your visitors what they need to see, when they need to see it, regardless of what kind of device they are on, or what orientation they are holding it in. Horizn is the default layout for [ghk](https://github.com/rjminchuk/ghk), an _in the works_ blogging utility.

###### Features

Horizn is less of a framework, and more of a strategy for handling different device types. With the provided layout below, a visitor will see a number of different things based on their device and it's orientation. Since Horizn was developed with blogging in mind, it can represent two states, a visitor reading an article, or not reading an article. The underlying style system relies heavily on the state of a hidden checkbox to determine the view the user will get back. When the visitor is reading an article, the input is checked.

###### The Moving Parts

- leadin | A nice place for an author photo, and the name of your blog
- timeline | Where your blog feed goes
- sheet | Where your blog article goes

###### But what shows and when?

That's a realy good question. What shows is only the most important content for the scale and orientation of your device. There are 5 different scenarios that have been coded for (covering 12 posibile device sizes, orientations, and states).

|                    | *ARTICLE OPEN*                                     | *ARTICLE CLOSED*                         |
|:------------------ |:-------------------------------------------------- |:---------------------------------------- |
| **LANDSCAPE**      |                                                    |                                          |
| Handheld / Mobile  | 2 col(s): leadin over timeline next to the Article | 2 col(s): leadin next to timeline        |
| Medium / Tablet    | 2 col(s): leadin over timeline next to the Article | 2 col(s): leadin next to timeline        |
| Large / Desktop    | 3 col(s): leadin, timeline, then Article           | 2 col(s): leadin next to timeline        |
| **PORTRAIT**       |                                                    |                                          |
| Handheld / Mobile  | 1 col(s): Article only                             | 1 col(s): colapsed, leadin over timeline |
| Medium / Tablet    | 2 col(s): leadin over timeline next to the Article | 2 col(s): leadin next to timeline        |
| Large / Pro tablet | 2 col(s): leadin over timeline next to the Article | 2 col(s): leadin next to timeline        |

###### A working example

[richminchuk.io](https://richminchukio11win.azurewebsites.net) is the dev site for my `personal bloging` utility called [GHK](https://github.com/rjminchuk/ghk).

###### The minimum layout 

```html
<!DOCTYPE html>
<html>
   <head>
      <link rel="stylesheet" href="/css/horizn.css">
   </head>
   <body>
      <input type="checkbox" id="horizn-article-open">
      <div class="horizn-container">
         <div class='horizn-leadin'>
            <!-- <h1>site name</h1> -->
         </div>
         <div class='horizn-timeline'>
            <!-- <label for="horizn-article-open"><h3>2017.12.15</h3></label>
                 <p>Unit Testing on MacOS /&nbsp;Windows</p>
                 <label for="horizn-article-open"><h3>2017.04.09</h3></label>
                 <p>Creating a dotnet core NuGet&nbsp;Package</p> -->
         </div>
         <div class='horizn-sheet'>
            <!-- <p><label for="horizn-article-open">close</label></p>
                 <h2>Article Title</h2>
                 <p>Article body.</p> -->
         </div>
      </div>
   </body>
</html>
```

# todo
- fix `pack.md` with readable instructions.