## HTML Common Elements 

There are tons of HTML elements, [HTML Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element). But following the Pareto principle, we know that 20% of them do 80% of the work, the most common ones are listed below.

HTML elements might have default styles defined by the browser (normally to match its functions in a web page). However, the styles are completely "overidable".

Elements have a specific meaning in the page, they're used not for their default styles but for their function, for what they represent on a page. As an example, it makes total sense to use an heading element when developers want to do an heading.

### HTML Charset

#### ASCII

The first character encoding standard. Defined 127 different alphanumeric characters that could be used on the internet. Numbers from 0 to 9, letters from A-Z and some common special characters.

#### ANSI 

Was the original Windows charset, supporting 265 different character codes.

#### ISO-8859-1

Default character set for HTML4. Also supporting 265 character codes.

#### UTF-8

Also called Unicode, is the default charset for the web nowadays covering almost all characters and symbols in the world.

[HTML Symbols](https://www.w3schools.com/charsets/ref_html_symbols.asp)
[HTML UTF-8](https://www.w3schools.com/charsets/ref_html_utf8.asp)

______

### Anchor <a>

Anchor tags are the known *links* in HTML pages. They normally have an `href` attribute with the URL to redirect when clicked.
Another common `a` element attribute is the `target`, this attribute is used to control the place where the link should open.

```html
<a href="http://google.com">Google</a>
```

#### Paths

Paths are ways to represent the location of a file. In HTML you can use *relative* or *absolute* paths to define your resources location.

##### Absolute paths

Absolute paths represent the absolute path to get to a file. An example of a absolute path are the URLs we use to represent a common website (`http://google.com`).

##### Relative paths

Relative paths are (as the name says) paths that are relative to the document they're in. They can also be relative to the server root (commonly `localhost` or `127.0.0.1` when developing or the domain name in a server). 

Example folder structure:
```
|- index.html
|- articles
 |- article-1.html
 |- article-2.html
|- contact-us-html
```

On `index.html` page, the path to the `article-1.html` page is `articles/article-1.html`.

```html
<a href="articles/article-1.html">Articles</a>
```

When using relative paths, the usage of `..` represents *the parent node on the folder structure*.

On `article-1.html` page, the path to the `index.html` page is `../index.html`.

```html
<a href="../index.html">Home</a>
```

### Paragraph <p>

Used as the name says, to contain a *paragraph* of text.

```html
<p>This is a sample paragraph</p>
```

### List <ul> <ol>

Respectively *unordered list* and *ordered list*. This element itself doesn't do much, it's main differences are the effect they have on their child elements. The first one renders *bullets* as their children and the second one renders *numbers*.

```html
<!-- Renders a list with bullets (• Home) -->
<ul>
  <li>Home</li>
  <li>About</li>
  <li>Contacts</li>
</ul>
<!-- Renders a list with numbers (1. Home) -->
<ol>
  <li>Home</li>
  <li>About</li>
  <li>Contacts</li>
</ul>
```

### List item <li>

Closely related with the *list element*. The `li` elements are used as list items, it's behaviour is mostly related with their parent

```html
<ul>
  <li>Home</li>
  <li>About</li>
  <li>Contacts</li>
</ul>
```

### Image

The `img` tag is used to render images. It must have a `src` attribute with the path to the image resource. A common attribute in images is `alt`, this attribute defines the alternative text to show when the image is not displayed.

```html
<img src="flag.jpeg" alt="Logo"/>
```

### Containers

There are two mostly used containers. `span` and `div`, their main difference is about the default styles, where `div` *occupies the whole line (display:block)* and `span` *only takes the space of it's content (display: inline-block)* by default. In *CSS* `div`s have `display: block` by default and `span`s have `display: inline-block`

While `span`s should only contain text, `div`s can contain anything. The usage of both this containers should be avoided when there are other elements that make more sense *semantically*.

`div` and `span` are heavily used when we want to define groups of elements to style.

```html
<span>I'm a span</span>

<div>
    <img src="abcd.jpeg" />
</div>
```

### Tables

Tables are not the most used element nowadays. However, some sites still use it. A table can define rows and columns using the `tr` and `td` elements. Table headers can also be defined using `thead`.

```html
<table>
  <thead>Name</thead>
  <thead>id</thead>
  <tr>
    <td>João</td>
    <td>102432123</td>
  </tr>
  <tr>
    <td>João</td>
    <td>102432123</td>
  </tr>
</table>
```

### Button

A button is also a common element in a lot of HTML pages. It's content is defined inside `<button>` tags.

```html
<button>Click me!</button>
```

### Heading

The html element `<h1> ... <h6>` is used to represent headings. Numbers are given in a hierarchic way, being 1 the most important, and 6 the less one. 
Even though elements have default styles (as the majority of the elements), the heading usage is mainly a question of semantics, to clearly represent the importance of titles in page.

### Input

An input (`<input>`) is an element where users can insert data, can be used and integrated with the `<form>` element. Inputs normally have a `type` attribute that changes the input appearance and behaviour. Another common attributes are `placeholder` and `value`, which define, respectively, the placeholder and the default value for that input.

```html
<input type "text" placeholder="Insert your name" value="FLAG"/>
```

#### Labels

Inputs can be together with labels. Labels, as the name says, act as input labels, describing what should be in the input. Labels reference inputs by the `for` attribute, referencing input's `id` attribute.

### Forms

Forms are groups of input that when submitted, send data to a URL. Forms normally have two main attributes `action` and `method`. Respectively defining the URL to redirect after submission and the *HTTP verb* used to do the request.

In forms, `input` values are stored and sent by the input `name` attribute.

```html
<form action="/createUser.php" method="post">
    <label for="username">Username</label>
    <input type="text" id="username" name="username"/>

    <label for="password">Password</label>
    <input type="password" id="password" name="password"/>
    
    <input type="submit" value="Submit!"/>
    <input type="reset" value="Clear"/>
</form>
```

## Common attributes

### class

Classes are mostly used in CSS to reference elements. `class`es are used to group elements in a way that makes sense, normally by appearance. Is common for a lot of elements to have the same *class*, and an element can have more than one *class*.

```html
<img class="banner" src="test.jpg" />
```

### id 

Id's are unique identifiers for the elements in the page. It is semantically incorrect to have elements with the same id.

```html
<img id="logo" src="site_logo.jpg" />
```
