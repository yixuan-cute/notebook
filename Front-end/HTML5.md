# 1 Getting Started

## 1.1 What is HTML?

&emsp;&emsp;HTML is an acronym that stands for Hypertext Markup Language. And HTML is the most basic building block of the web. It defines the meaning and structure of web content. Other technologies besides HTML are generally used to describe a web page's appearance/presentation(CSS) or functionality/behavior(JavaScript).

&emsp;&emsp;"Hypertext" refers to links that connect web pages to one another, either within a single website or between websites.

&emsp;&emsp;Overall, HTML uses "markup" to annotate text, images, and other content for display in a Web browser.

## 1.2 The first html file

```html
<html>  <!-- every page starts and end with html opening and closing tags -->
        <!-- everything else on the page goes between those tages -->

    <head>  <!-- contains data and is not seen on the page -->
            <!-- this is considered to be metadata about the page -->

        <title>The Title of the Page</title>
    </head>

    <body>  <!-- the part of the page that everybody sees in the broswer -->

        <h1>Hello, World!</h1>
    </body>

</html>
```

## 1.3 Check errors and warnings

&emsp;&emsp;Click <a href="https://validator.w3.org/" target="_blank">Validator</a>, and upload the file.

## 1.4 Add a `lang` attribute

```html
<html lang="en">
    ......
</html>
```

&emsp;&emsp;We might have other language to put here and we can find a list of those at MDN network.

## 1.5 Declare the character encoding

```html
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        ......
    </head>
    ......
</html>
```

## 1.6 Document type declaration

```html
<!DOCTYPE html>  <!-- this declaration should be on the very first line of the page -->
                <!-- this is not really an HTML element or tag -->
<html>
    ......
</html>
```

# 2 Head Element

&emsp;&emsp;Everything inside head element is not seen on the web page.

## 2.1 `meta` element

```html
<head>
    <!-- the author of the page -->
    <meta name="author" content="Dave Gray"/>

    <!-- the description of the page -->
    <meta name="description" content="This page contains all the things I am learning how to create as I learn HTML."/>
</head>
```

## 2.2 `link` element

```html
<head>
    <!-- set a little favicon beside the title -->
    <link rel="icon" href="./assets/html.ico" type="image/x-icon"/>
</head>
```

&emsp;&emsp;Using `link` element, we would link to CSS files and even JavaScript files and other resources that we pull in from the web.

```html
<head>
    <!-- link to a CSS file -->
    <link rel="stylesheet" href="./css/main.css" type="text/css" />

    <!-- link to a JavaScript file -->
    <link rel="" href="./js/main.js" type="text/javascript" />
</head>
```

## 2.3 `style` element

```html
<head>
    <style>
    html {
        font-size: 22px;
    }
    body {
        background-color: #333;
        color: whitesmoke;
    }
    </style>
</head>
```

## 2.4 `script` element

```html
<head>
    <script type="text/javascript">

    </script>
</head>
```

# 3 Text Basics

## 3.1

# 4 List Types

# 5 Add Links

# 6 Add Images

# 7 Semantic Tags

# 8 Create Tables

# 9 Forms & Inputs

# 10 HTML Project
