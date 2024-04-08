# 1 About CSS

&emsp;&emsp;Cascading Style Sheet(CSS) is a stylesheet language used to describe the presentation of a document written in HTML or XML. CSS describes how elements should be rendered on screen, on paper, in speech, or on other media.

## 1.1 Sample code

`index.html`:

```html
<html>
    <head>
        <title>Hello CSS</title>
        <link rel="stylesheet" href="./css/style.css"/><!-- this is our link to the external stylesheet -->
        <style><!-- internal stylesheet  -->
            p {
                color: limegreen;
                /*
                    The text inside the p element will be set to limegreen,
                    because our internal stylesheet is read last.
                */
            }
        </style>
    </head>
    <body>
        <p>
I'm learning CSS!
        </p>
        <p style="color: blue"><!-- the color of this p element will be set to blue, because the stylesheet is applied directly to the element itself  -->
I'm learning CSS again!
        </p>
    </body>
</html>
```

`css/style.css`:

```css
/*
    this way is commonly used
*/
p {
    color: purple;
    font-size: 64px;
}
```

## 1.2 Anatomy of a CSS ruleset

![css_ruleset](./images/css_ruleset.png)

Note the other important parts of the syntax:

* Apart from the selector, each ruleset must be wrapped in curly braces `{}`. 
    * Leave a space before the curly braces and after the selector.
* Within each declaration, we must use a colon `:` to separate the property from its value or values.
    * Leave a space before the property value(s) and after the colon.
* Within each ruleset, we must use a semicolon `;` to separate each declaration from the next one:

```css
p {
    color: red;
    width: 500px;
    border: 1px solid black;
}
```

# 2 Selectors

## 2.1 Element Selector

&emsp;&emsp;An element selector is sometimes referred to as a **tag name selector** or **type selector** because it selects an HTML tag/type in our document.

```css
/*
    selecting an element
*/
p {
  color: red;
  width: 500px;
  border: 1px solid black;
}

/*
    selecting multiple elements
*/
p, li, h1 {
  color: red;
}

/*
    An element inherits some of the settings or properities from its parent element.
    And the body element is parent to any other element on the web page.
    Some properities would be inherited by all the elements inside it, such as "font-size".
    Some properities wouldn't be inherited by any element inside it, such as "border".
*/
body {
    /*
        
    */
    font-size: 10px;

    /*
        The border only went around the body element.
        It didn't apply to all the other elements inside the body.
    */
    border: 3px solid black;
}
```

## 2.2 Class Selector

&emsp;&emsp;The case-sensitive class selector starts with a dot `.` character. It will select everything in the document with that class applied to it.

&emsp;&emsp;The element(s) on the page with the specified class. Multiple instances of the same class can appear on a page. An element with multiple classes can also appear on a page.

&emsp;&emsp;In the example below we have created a class called highlight, and have applied it to several places in our document. All of the elements that have the class applied are highlighted.

```css
.hightlight {
    background-color: yellow;
}
```

```html
<h1 class="highlight">Class selectors</h1>
<p>Veggies es bonus vobis, proinde vos postulo essum magis <span class="highlight">kohlrabi welsh onion</span> daikon amaranth tatsoi tomatillo
    melon azuki bean garlic.</p>

<p class="highlight">Gumbo beet greens corn soko <strong>endive</strong> gumbo gourd. Parsley shallot courgette tatsoi pea sprouts fava bean collard
    greens dandelion okra wakame tomato. Dandelion cucumber earthnut pea peanut soko zucchini.</p>
```


## 2.3 Id Selector

```css
#name {
    
}
```

## 2.4 Universal Selector

&emsp;&emsp;The universal selector is indicated by an asterisk `*`. It selects everything in the document (or inside the parent element if it is being chained together with another element and a descendant combinator). 

&emsp;&emsp;This means **selecting everything** on the page. We typically only see this for what is called a css reset.

&emsp;&emsp;**This is not inheritance**. This is actually selecting all elements.

```css
* {
    font-family: monospace;

    /*
        All elements on the web page 
    */
    border: 10px solid black;
}
```

## 2.5 Attribute Selector

## 2.6 Pseudo-class Selector

## 2.7 Combinator

# 3 Colors

# 4 

# 5

