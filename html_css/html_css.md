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
```

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

