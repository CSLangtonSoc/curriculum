# Lesson 1: Introduction

Web development is the field of creating content for the web.

There are two main components of web development:

## Front-end development

Front-end development involves creating the visual component of the website, the part the user interacts with. This is known
as the **client**.

This involves HTML, CSS and JavaScript. Front-end developers must write code for browsers to interpret and display, so there
is less flexibility in how you can arrange your code as it must be in a format that browsers can understand.

More advanced software developers utilise tools known as **frameworks** which simplify
and speed up the creation of user interfaces. Examples include React, Vue.js and Angular.

In this module, we will stick to using vanilla, unmodified HTML, CSS and JS.

## Back-end development

Back-end development involves creating the functional component of the website, the software systems that run in the background that enable it to provide a service. This is known as the **server**, as the code usually runs on a remote server in the cloud.

Back-end software systems are usually made with Python, JavaScript, Java, C# and more. There is much more variety in how you
can create a back-end system as the implementation can be entirely decided by you.

Server-side code is typically the main difficulty of making a website, as it determines the actual functionality it has.
The client or front-end is simply there to display information and allow the user to input actions.

## [Activity] Create a development environment

In order to practice HTML, CSS and JS we will make an online code sandbox.

1. Go to [codesandbox.io](https://codesandbox.io/).
2. Sign up with your school account or GitHub
3. Create a vanilla HTML + CSS sandbox

## HTML Basics

For now, we are just going to focus on the HTML aspect of the website.

Ensure on the left hand toolbar you have the
`index.html` file open. It should look something like this:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>HTML + CSS</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <h1>This is a simple HTML + CSS template!</h1>
  </body>
</html>
```

### Elements

You may notice a number of different "elements", represented with tags such as `<html>`, `<head>`, `<body>` etc...

These elements define the structure of the website so that the browser knows how to format it. Each element has a different
purpose and a different definition.

Every HTML tag has to be "closed" so that the browser knows where it starts and where it ends.

Usually, it looks like this:
```html
<tag>...</tag>
```

The closing tag has a / to indicate it is the end of that particular tag. Anything in between the opening and closing tags is
"content" that is inside the tag.

We can see this in the code, with `<html>`, `<title>`, `<body>` and `<h1>` etc...

However, some special tags do not have any content inside and therefore do not need a closing tag.

The closing identifier can be placed inside the opening tag, like this:
```html
<tag />
```

### Body

The default HTML structure is quite complicated, and be overwhelming for beginners. For now, just worry about what is in between
the `<body></body>` tags. There should only be one of these tags per HTML document, inside the `<html></html>` tags.

`<body>` is a special tag that defines the actual content displayed on the page.

Everything that you put in there will be rendered by the browser and shown when you visit the website.

From now on, when you want to add content to your website, put it inside your `<body>` tag.

Experiment with the following tags:

### Text

Regular text in HTMl is signified with the `<p></p>` tag.

Larger, more important text is defined using header tags:

- `<h1></h1>`
- `<h2></h2>`
- `<h3></h3>`
- `<h4></h4>`
- `<h5></h5>`
- `<h6></h6>`

`<h1>` is the biggest, and they get smaller in descending order.

Use these to signify titles and headers in your website.

If we want to make links to other pages in HTML, we use hyperlinks - made with the `<a></a>` tag.

The website you want to direct the browser to when the link is clicked is defined with the `href` attribute. Put it inside the opening tag as so, using an `=` symbol and defining the value in double quotes.

```html
<a href="https://langtoncompsci.tech/">Link to society website</a>
```

Hyperlinks are often placed within other elements in order to create a single link within a block of text, such as here:
```html
<p>You can find out more about the society <a href="https://langtoncompsci.tech/">here</a><p>
```
Just the text that you want to become a hyperlink is placed in the `<a>` tag.

### Grouping elements

HTML is used to create a structure of elements on the page. This not only defines the content on the page, but also how 
it is laid out.

Grouping several elements together using a tag is an essential part of front-end development, as it allows those elements to
follow a specific rule, such as how they are displayed or what they look like.

Elements are typically grouped using the `<div></div>` element. 

There are other elements such as `<section>`, `<main>` and `<article>` which do the same purpose. However, these are no different in functionality as `<div>`, and are intended to be descriptive, helping describe what content is being grouped together. 

The `<div>` element can group elements together like this:

```html
<div>
  <h1>About</h1>
  <p>The CS Society aims to teach CS to Year 12.</p>
</div>
</div>
  <h1>When</h1>
  <p>Form time Tuesday & Wednesday + Period 5 Wednesday</p>
</div>
```

As you can see, different sections are separated from each other. In most websites, `<div>` elements are often highly 
nested in extremely complex website structures.

`<div>` elements are also used to create boxes and containers on the page, which hold elements.

The `<span>` element is similar to a div, except it is designed to hold only "inline" elements, just text elements while
a `<div>` can group all kinds of elements together.

### Other elements

`<img>` tags are used to create images on the page.

They are defined like this, using one self-closing tag:

```html
<img src="https://langtoncompsci.tech/assets/img/logo-light.png" width="903" height="252" />
```

The image URL is defined with the `src` (source) attribute, and the image width and height (in pixels) using the `width` and `height` attributes.

## [Assignment] Create a personal bio page

In your sandbox, create a personal bio page with your name, A-level subjects and what you want to learn in CS.

If you have already learned how to use basic CSS, add some to your site in order to spruce up the visuals.
