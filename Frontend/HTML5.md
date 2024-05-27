# 1 Getting started with HTML

## 1.1 What is HTML?

&emsp;&emsp;HTML (HyperText Markup Language) is a markup language that tells web browsers how to structure the web pages we visit.

&emsp;&emsp;For example, consider the following line of text:

```html
My cat is very grumpy
```

&emsp;&emsp;If we want the text to stand by itself, we could specify that it is a paragraph by **enclosing it in a paragraph `<p>` element**:

```html
<p>My cat is very grumpy</p>
```

## 1.2 Anatomy of an HTML element

![html_element_anatomy](./images/html_element_anatomy.png)

The anatomy of our element is:

* The **opening tag**: Marks where the element begins or starts to take effect.
* The **content**: The content of the element.
* The **closing tag**: Marks where the element ends.

### 1.2.1 Nesting elements

&emsp;&emsp;Elements can **be placed within other elements**. This is called nesting. 

&emsp;&emsp;If we wanted to state that our cat is very grumpy, we could wrap the word "very" in a `<strong>` element, which means that the word is to have strong(er) text formatting:

```html
<p>My cat is <strong>very</strong> grumpy.</p>
```

&emsp;&emsp;The following is an example of the wrong way to do nesting:

```html
<p>My cat is <strong>very grumpy.</p></strong>
```

### 1.2.2 Void elements

&emsp;&emsp;Not all elements follow **the pattern of an opening tag, content, and a closing tag**. Some elements **consist of a single tag**, which are called void elements.

&emsp;&emsp;For example, the <img> element embeds an image file onto a page:

```html
<img
  src="https://raw.githubusercontent.com/mdn/beginner-html-site/gh-pages/images/firefox-icon.png"
  alt="Firefox icon" />
```

## 1.3 Attributes

![html_attribute](./images/html_attribute.png)

> Note:  
> &emsp;&emsp;Attributes contain extra information about the element that won't appear in the content. In this example, the **class** attribute is an identifying name used to target the element with style information.

### 1.3.1 Boolean attributes

&emsp;&emsp;Sometimes we will see attributes written without values. This is entirely acceptable. These are called **Boolean attributes**.

&emsp;&emsp;For example, consider the disabled attribute, which we can assign to form **input** elements. (We use this to **disable the form input elements so the user can't make entries**.)

```html
<input type="text" disabled="disabled" />
```

&emsp;&emsp;As shorthand, it is acceptable to write this as follows:

```html
<!-- using the disabled attribute prevents the end user from entering text into the input box -->
<input type="text" disabled />

<!-- text input is allowed, as it doesn't contain the disabled attribute -->
<input type="text" />
```

> Notes:  
> &emsp;&emsp;Boolean attributes can only have one value, which **is generally the same as the attribute name**. 

### 1.3.2 Omitting quotes around attribute values

&emsp;&emsp;If we look at code for a lot of other sites, we might come across a number of strange markup styles, including attribute values without quotes.

&emsp;&emsp;This is permitted in certain circumstances, but it can also break our markup in other circumstances.

```html
<!-- pass -->
<a href=https://www.mozilla.org/>favorite website</a>

<!-- error -->
<a href=https://www.mozilla.org/ title=The Mozilla homepage>favorite website</a>
```

> Notes:  
> &emsp;&emsp;As written above, the browser misinterprets the markup, mistaking the title attribute for three attributes: a title attribute with the value **The**, and two boolean attributes, **Mozilla** and **homepage**.

### 1.3.3 Single or double quotes?

&emsp;&emsp;In some web pages, we will also notice that the attributes are wrapped in double quotes. However, we might see single quotes in some HTML code.

&emsp;&emsp;This is a matter of style. We can feel free to choose which one we prefer. Both of these lines are equivalent:

```html
<a href='https://www.example.com'>A link to my example.</a>

<a href="https://www.example.com">A link to my example.</a>
```

&emsp;&emsp;But make sure we don't mix single quotes and double quotes. That is to say the following lines are not acceptable.

```html
<a href="https://www.example.com'>A link to my example.</a>
<a href='https://www.example.com">A link to my example.</a>
```

## 1.4 Anatomy of an HTML document

```html
<!doctype html>
<html lang="en-US">
  <head>
    <meta charset="utf-8" />
    <title>My test page</title>
  </head>
  <body>
    <p>This is my page</p>
  </body>
</html>
```

* `<!doctype html>`: 
* `<html></html>`: This element wraps all the content on the page, which is sometimes known as the root element.
* `<head></head>`: This element acts as a container for everything we want to include on the HTML page, that isn't the content the page will show to viewers.

## 1.5 Entity references: Including special characters in HTML

|Literal character|Character reference equivalent|
|:---------------:|:----------------------------:|
| White Space     | `&nbsp;`                     |
| Tab             | `&emsp;`                     |
| \<              |	`&lt;`                       |
| \>              | `&gt;`                       |
| \"              | `&quot;`                     |
| \'              | `&apos;`                     |
| \&              | `&amp;`                      |

## 1.6 HTML comments

&emsp;&emsp;To write an HTML comment, wrap it in the special markers `<!--` and `-->`. For example:

```html
<p>I'm not inside a comment</p>
<!-- <p>I am!</p> -->
```

# 2 




# 3 Multimedia and embedding

# 4 HTML tables

# 5 Form




