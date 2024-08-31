# 1 Getting started with CSS

## 1.1 What is CSS?

&emsp;&emsp;CSS (Cascading Style Sheets) is a **style sheet language**, which is what we use to selectively style HTML elements. While HTML is used to define the structure and semantics of our content, CSS is used to style it and lay it out.

## 1.2 Starting with some HTML and styling it

1. The HTML document:

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>Getting started with CSS</title>
  </head>

  <body>
    <h1>I am a level one heading</h1>

    <p>
      This is a paragraph of text. In the text is a
      <span>span element</span> and also a
      <a href="https://example.com">link</a>.
    </p>

    <p>
      This is the second paragraph. It contains an <em>emphasized</em> element.
    </p>

    <ul>
      <li>Item <span>one</span></li>
      <li>Item two</li>
      <li>Item <em>three</em></li>
    </ul>
  </body>
</html>
```

2. Create a file in the same folder as our HTML document and save it as `styles.css`.

```css
<link rel="stylesheet" href="styles.css" />
```

3. Adding the CSS file to our document.

```html
<link rel="stylesheet" href="styles.css"/>
```

> Note:  
> &emsp;&emsp;This `<link>` element tells the browser that we have a stylesheet, using the **rel** attribute, and the location of that stylesheet as the value of the **href** attribute.

### 1.2.1 

## 1.3 How CSS is structured

### 1.3.1 Applying CSS to HTML

1. External stylesheet

&emsp;&emsp;An external stylesheet contains CSS in a separate file with a `.css` extension. This is the most common and useful method of bringing CSS to a document. We can link a single CSS file to multiple web pages, styling all of them with the same CSS stylesheet.



2. Internal stylesheet

3. Inline styles







