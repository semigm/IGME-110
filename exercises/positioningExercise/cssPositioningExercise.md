# CSS Positioning Exercise

## Overview & Goals
Today you're going to put into practice some of the CSS box model and positioning information in today's readings.  In class, I'll walk through the process of adding each of the necessary style rules. When you're done, you should have something that looks like this:

![Example Layout](sample.png)

## Setting Up Files and Folders
Download the [cssPositioning.zip](cssPositioning.zip) file from GitHub, and unzip the archive.

You should now have a cssPositioning folder with three files in it: a layout.html file with the basic structure and content for the page you need to create, the photo that's included on the page, and a layout.css file in which you'll put the necessary CSS rules.

## Changing the HTML Content
Don't. :) Your goal is to replicate what you see in the screen shot!

## Adding a Google Font
At the beginning of your layout.css file, add the following line to load the Open Sans font from [Google Fonts](https://fonts.google.com/). 

```css
@import url('https://fonts.googleapis.com/css?family=Open+Sans');
```

## Adding Borders to Help With Positioning
When I'm working on a CSS layout, I usually put 1-pixel solid borders around all of the elements I want to position; this lets me see what happens when as I adjust padding (which is inside the border), margin (which is outside the border), size, and position. I find when I'm working with a new layout that the borders are very helpful as guides. Rather than adding the border to each element individually, I set one rule at the start of the stylesheet that impacts all of the elements I plan on positioning. In this case, I've got several elements that I want to position: header, footer, article, and aside. (The article and aside elements are considered "semantic" HTML, something you'll learn more about in IGME-230.)

To add the same border to all of them, I can list the elements separated by commas, and then assign a single style rule. 

```css
 header, footer, article, aside {border: 1px solid black;}
 ```

If I don't want the outlines when I'm done with my layout, I can then comment out or delete that line. 

## Page Background
The html element has a [background image](http://www.w3schools.com/cssref/pr_background-image.asp) of `http://silviahartmann.com/background-tile-art/images/black_woven_seamless_tile.jpg` . Note that I didn't put the patterned background in the element containing the text content, but rather put it in the element behind it. This allows me to use a dark or high contrast background image or pattern without impacting readability. 

```css
html {
    background-image: url(http://silviahartmann.com/background-tile-art/images/black_woven_seamless_tile.jpg);
}
```
## Text Formatting
We've retrieved the Open Sans font, but not applied it to the content yet. Format all of the text in the document by assigning a font, size, and line-height to the body element: 
```css
body {
    font-family: 'Open Sans', sans-serif;
    font-size: 16px;
    line-height: 1.4;
}
```
The font size of the level 2 headings needs to be tweaked a bit to match the example:
```css
h2 { font-size: 1.1em; }
```
## Centered, Fixed-Width Content Container
To keep the page content a set width regardless of the size of the browser, and to prevent the background image from making it unreadable, you can place it all inside a "container" div with a fixed width. The container can be centered on the page by setting its left and right margins to "auto". 

To prevent the HTML background image from interfering with text readability, you can add a solid background color. Some additional padding inside the container makes everything feel less crowded. a background color of white, and padding of 15px on all sides. 
```css
#container {
    width: 960px;
    margin: 0 auto;
    background-color: white;
    padding: 15px;
}
```
## Header
The header uses the text-align property to center its contents. It has a set height of 50px, and 1em of space below the border (the margin).  
```css
header {
    height: 50px;
    text-align: center;
    margin-bottom: 1em;
}
```
The level 1 heading inside the header needs less space above it. You can specify a rule for an element only when it's inside of another element by listing the external element before the internal element, and not using a comma between them:
```css
header h1 {
    margin-top: 0;
}
```

## Left-Side Content
The aside is floated to the left, and has a width of 30%. There's padding on the left and right side of the element to keep the text from pushing up against the border, and some extra margin space below the element. 

To make sure my content is visible on most browsers without a need to scroll, I used CSS to set an fixed height for both the aside and the article elements. If the content in the article container becomes too long to fit into a container of that height, the overflow:scroll property will add a scroll bar. 
```css
aside {
    float: left;
    width: 30%;
    padding: 0 1em;
    margin-bottom:1em;
    height: 500px;
}
```
## Main Content
The article is floated to the right, and has a width of 60%.  It has the same height, padding, and margin settings as the aside. Because the content might end up being larger than the fixed height can accommodate, I've added the overflow:scroll property to provide a scroll bar if necessary.  
```css
article {
    float: right;
    width: 60%;
    height: 500px;
    padding: 0 1em;
    margin-bottom: 1em;
    overflow: scroll;
}
```
## Photo Formatting
The photo has an ID of portrait. It needs a border around it to provide a cleaner distinction between it and the background, and some space above it so that it's not right up against the edge of the aside element:  
```css
#portrait {
    border: 1px solid black;
    margin-top: 1em;
}
```
(Why am I using margin rather than padding to provide that space? What happens if you change margin-top to padding top in that definition?)

## Footer Element
The footer element also has center-aligned text. It also needs to be forced underneath  the left and right floated elements with the clear attribute: 
```css
footer {
    text-align: center;
    clear: both;
}
``` 
## Uploading and Due Date
Upload the cssPositioning folder with your edited layout.css file to your igme110 folder on GitHub.
> userName.github.io/igme110/cssPositioning/layout.html

You have until the start of monday's' class (3/4) to complete the exercise.
