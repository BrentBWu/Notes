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

