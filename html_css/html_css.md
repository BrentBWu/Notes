## HTML CSS Foundation
### 1.1 HTML tags
> words need to remember: hyperlink

~~~html
<h1>Recipe World</h1>
~~~
#### html allows you to take a plain text document created in any simple text editor
#### html stands for HyperText Markup Language

#### Writing HTML
Most of the time, you'll put your content in between HTML tags, which have corresponding   **opening**  and **closing** versions.

~~~html
<h1>for head title</h1>

<p>for paragragh</p>

<ul> -- parent tag
    <li>2 eggs</li> -- child tag
</ul>

<ol>ordered list tag
    <li>2 eggs</li>
</ol>

<body> -- the parent of all visible content
Any content that appears on a web page should be in between a body tag.
</body>

<head> 
Non-visible stuff goes in the head tag.
You'll eventually use the head tag to load other useful scripts,
like CSS and JavaScript.
</head>

<!DOCTYPE html> -- sets the HTML version number
<html> -- All of your HTML goes inside of the html tag
<head>
    <title></title>
</head>
<body>

</body>
</html>
~~~

#### Remember to use <p> tag to make up your contents.

### 1.8 HTML links

#### Adding likns to our recipe site

#### What happens when you type a URL in the Browser
* Enter a URL into the browser's address bar
* A request is sent to the server, and the server looks for the file that's being requested.
* The server returns the file to the browser and the browser displays it.

~~~html
<a href="#"target='_black'>How to make a link</a>
<h3>The target attribute sets</h3>
~~~

#### Absolyte vs. Relative paths
Absolute paths ask for a file from a specific server

~~~html
<a href="http://example.com/legal.html">legal page</a> // abosulte always includes the protocol and server, which need to always be used when linking to pages that are located on another site/server.

<a href="legal.html">legal page</a> // Since no server name is included, the browser assumes you mean the same server that your page is on.
~~~

#### 2.1 CSS selector

#### The early days of style on the web
When the Web was brand new, there was no separation between HTML and the presentaion of that HTML.
Tags are selected by creating sth called a selector.

~~~css
selector {
    transition-property: value;
}
~~~

* A **descendent selector** can be used to select tags only if they are children of another tag.

~~~css
ul li {
    font-size: 24px;
}
~~~
##### select only li tags that are children of ul tags

* A **pseudo-selector** is a modifier that can be added to a selector to select a tag only when a certain condition has occurred.

~~~css
a {
    text-decoration: none; 
    /*remove the underline from all links on a page*/
}

a:hover {
    text-decoration: underline;
    color: darkred;
    /*adds an underline and changes the color of all links on a page ONLY when the mouse is over the link*/
}
~~~

* The **:first-child** pseudo-selector can be applied to narrow the amont of child tags selected

~~~html
<h3>Directions</h3>
<ol>
    <li>Mix eggs, sugar... </li>
    <li>Spread into a... </li>
    <li>Bake at 350</li>
</ol>
~~~

~~~css
ol li:first-child {
    color: red;    /* select only the first li tag */
}
~~~


#### Where to put css tags
One place you can put CSS is in a style tag that's a child of the head tag.

~~~html
<!DOCTYPE html>
<html>
<head>
    <title></title>
    <style type="text/css"> /*The type attribute lets the browser know that css is coming*/
        a {
            color: red; /*Your CSS selectors can be written in between the style opening and closing tags*/
        }
    </style>
</head>
<body>

</body>
</html>
~~~

#### Hexadecimal colors
Each hex color is actually three different parts.

```
#FFFF00
first two numbers set the amount of red
next two set green
last two set blue
```


### The box model
#### Our page after changing some styles with css

```
**Questions** 
How does our page know how much vertical and horizontal space to put between tags?
How can we control that spacing?
```

```
**Answer**
Box Model
```

#### The Box
Every tag shown in the body is contained in an invisible rectangle that we'll call **the box**.

~~~html
<p>Magic cake is one of... </p>
<p>We also need to stress... </p>
~~~

##### These twwo paragraph tags are shown as two boxes stacked on top of each other.

```
**Block-level tags**
The content of block-level tags take up the entire width of the container.
The tags that contain this content are all block-level.
```

```
**Inline-level tags**
Inline-level tags don't try to take up more width than they need
```

##### The box model
The **box model** is a way to describe the borders and spacing in between the **boxes** of each tag.

#### There are 4 parts of the box model

* Content area
    - The *content area* contains your actual content(text, image, etc.)
    - The content area will only take up as much vertical space as it needs to display the content inside.

* Padding
    - Padding is added to the top, bottom, ot left of the content area.

* Border
    - Borders are added around the top, right, bottom, or left of the padding.

* Margin
    - Margins are added to the top, right, bottom, or left of the border.


#### How to calculate the size of the box
The full size of a box after these four properties have been set can be calculated like this:

![boxmodel][boxmodel]

[boxmodel]:https://cl.ly/3H3y2K2w383l/Image%202018-03-06%20at%203.24.58%20PM.png

```
+ content area width
+ padding-left + padding-right
+ border-left + border-right
+ margin-left + marigin-right
    = the full box width
```

If we want to put some space aboe and to the right of some text, one option is to adjust the padding.

#### Applying the box model properties

~~~css
h2 {
    padding-top: 6px;
    padding-right: 3px;
    padding-bottom: 1px;
    padding-left: 0px;
}

/*all at once in a clockwise order*/

h2 {
    padding: 6px 3px 1px 0;
}
~~~

If we want ot put some space above and to the right of some text, one option is to adjust the padding.

You'll can apply borders all at once and not specify a side.

~~~css
h2 {
    border-width: 6px;
    border-style: solid;
    border-color: black;
}

/*You can also just pick one side and just add a border there.*/

h2 {
    border: 6px solid black;
}
~~~


Add margins the same way you add padding...

~~~css
h2 {
    margin-top: 6px;
    margin-right: 0;
    margin-left: 6px;
    margin-left: 0;
}

/*or use the same shortcut syntax as paddiing.*/

h2 {
    margin: 6px 0 6px 0;
}
~~~

#### When should you use padding?
Padding is used to control the size of a box without adjusting the size of the content inside the box.

![padding][padding]

[padding]:https://cl.ly/26390d2f373E/Image%202018-03-06%20at%204.05.26%20PM.png


#### When should you use margin?
Margin is used to control the space between boxes.

![margin][margin]

[margin]:https://cl.ly/2v1D1l1K433z/Image%202018-03-06%20at%204.08.19%20PM.png


#### What we now know:
* Each tag's content fits in an invisible box
* Each block-level tag's box takes up an entire line
* Padding can be used to adjust spacing within a container
* Margin can be used to adjust spacing between containers


#### Default browser styles
Browsers actually have a default stylesheet for when no custom styles are set.

#### Resetting default browser styles
Add this to the very top of your CSS file to reset default styles.

~~~css
html, body, h1, h2, h3, p, ol, ul, li, a {
    padding: 0;
    border: 0;
    margin: 0;
}

/* Include each tag that's in your HTML for that page*/
~~~

Now, all of the default box properties are reset, and we need to set the box model properties ourselves.

#### A box Model process - Start with the body

The order that you apply the box model properties is personal preference, but here's one approach:

Start from the highest parent element
This is often **<body>**

~~~css
body {

}
~~~

This padding has the effect of pushing all of the children away from the edges of the **<body>**

Next, focus on the heading tags



#### A Box Model process- padding
Padding is also used to adjust list and list them indentation.


## 3.1 CSS selectors

##### Using classes in descendent selectors

Classes can be used interchangeably with tags, so the way descendant selectors work doesn't change.
??????????????????????????????????????????????????




#### Writing class and type selectors in the right order
When you're just using type selectors, the order doesn't really matter.
When you start combining them with class selectors - the older matters.

~~~css
.nav {
    padding-left: 0;
}

ul{
    padding: 0 0 0 50px;
}

/*This ul padding overrides the .nav padding because it comes after the .nav in the stylesheet.*/
~~~

Padding for *.nav* before *ul* rule
*padding-left: 0;*

Padding for *.nav* after *ul* rule
*padding-left: 50px;*

#### Generally speaking, **first declare the broadest rules** with type selectors, and then get more specific with class selectors.

~~~css
ul{
    padding: 0 0 0 50px;
}

.nav {
    padding-left: 0;
}
~~~

This way, the borader rules cascade down and become defaults, and more specific rules can change the defaults.


#### Creating a page that lists all recipes

Our recipes.html page will have a list of links to individual recipe pages.




#### Where do you write CSS?
While CSS can be written inside of a <style> tag in an HTML file, most of the time it's written in a separate file and connected to the HTML file with a **link** tag.

    * The link tag should be a child of the head tag
    * The link tag is and empty tag, meaning it is written with only and opening tag and has no closing tag.

Since the tag is empty, the way you use it is by setting different **attributes**.

~~~html
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" type="text/css" href="">
    /* The rel attribute is short for relationship */
    /* Setting rel to stylesheet tells the HTML that it should use the linked file to determine page styles */
    /* The type attribute set to test/css lets the browser know we'ew going to be loading a CSS file */
    /* The href attribute works just like it does with the <a> tag*/
</head>
<body>
</body>
</html>
~~~


## divs and layout

### The div tag
div is short for division, and it's a *block-level tag* that's a generic way to *group related content into sections* on a page.


#### Centering with margin auto
**auto** here means take as much space as you can.

~~~css
magic-cake {
  margin: 30px auto 0 auto;  
}
~~~

![auto][auto]

[auto]:https://cl.ly/3y0u2602233x/Image%202018-03-07%20at%205.52.22%20PM.png

#### Centering content
There's two main ways to center things, but the CSS you write depends on what you're centering.
    **IF** you want to center children *inside* a block-level tag
    **Then* set the *text-align* of the children to *center*




### 4.1 Content Images
#### Creating content images
Content images are created in HTML with the <img> tag,

~~~html
<img src="images/cake.png" alt="Magic Cake Photo">
~~~

The alt attribute should contain text that describe the image or the purpose of the image.


#### Centering an image inside a block-level tag
**<img>** is an *inline-level* tag so it can't be centered with text-align.
Instead, set just that image to **display**: **block** and center it with the **margin: auto** approach.

~~~html
<div class="header">
    <img src="images/logo.png" alt="Recipe World Logo">
</div>
~~~

~~~css
.header img {
    display: block;
    margin: 0 auto 0 auto;
}
~~~


#### Uderstanding the background property
**background-image** can point to a relative or absolute path.

~~~css
body {
    background-image: url(images/gobbler.png);
}
~~~

**background-position** can be used to position the image in a container.

~~~css
body {
    background-position: center left; /*the*/
}
~~~

**background-repeat** can be used to repeat tiled images.

~~~css
body {
    background-repeat: no-repeat; /*the*/
}
~~~



#### Creating different tiled backgrounds

 We can set different backgrounds for different containers
 Here, we're using one repeated background for the body, another for the main-content, and another for the divs on the recipes page.

~~~html
<div class="featured-image">
    <h3>Featured: Magic Cake</h3>
</div>
~~~

~~~css
.featured-image {
    width: 630px;
    height: 246px;
    background: #ffffff url(images/featured-cake.png) top left no-repeat;
}
~~~


#### Displaying an image to the side of block-level tags

HTML elements are usually either block-level elements or inline elements. A block-level element occupies the entire space of its parent element(container), thereby creating a block.

By defualt, bloack-level elements begin on new lines, but inline elements can start anywhere in a line.

#### Floating images

You might try setting two divs to inline. Turns out, we can't just flip things to inline and then put block-level tags inside of them.


## 5.1 Adjusting Font Styles

The **font-family** property is used to set the ideal font and a few fallback options.

~~~css
body {
    font-family: Helvetica, Arial, sans-serif;
} 
/*The first is the ideal font, not all fonts are installed in all browsers*/
~~~

### Adjusting the line height
**line-height** is like margin for each line in a box.

You can adjust the vertical spacing between different text tags by changing the margin.


### Creating web forms

#### Web Forms

basic HTML example

~~~html
<form>
    <label>Recipe Name</label>
    <input type="text" name="">
    <input type="submit" value="Click to submit" name="">
</form>
~~~

![commonform][commonform]

[commonform]:https://cl.ly/2n181s0M2U1P/Image%202018-03-12%20at%204.37.37%20PM.png

#### The for and id attributes
The value of the **for** attribute in the label should be the same as the value of the id attribute in an input field to associate the label and input.

Each for/id pair has to be unique on the page.

~~~html
<form>
    <label for="recipe-name">Recipe Name</label>
    <input type="text" id="recipe-name" name="">
    <textarea id="ingredients"></textarea> 
    textareas also don't need to define types
</form>
~~~

~~~css
input[type=submit] {
  width: 165px;
}
~~~
