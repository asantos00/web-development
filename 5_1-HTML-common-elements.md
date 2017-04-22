## HTML Common Elements 

There are tons of HTML elements, [HTML Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element). But following the Pareto principle, we know that 20% of them do 80% of the work, the most common ones are listed below.

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

In HTML you can use *relative* or *absolute* paths. 
Relative paths depend on the location of the file the user is seeing at the moment. 
Absolute paths are relative to server route (/).

### Paragraph <p>

Used as the name says, to contain a block of text. 

```html
<p>This is a sample paragraph</p>
```

### List <ul> <ol>

Respectively *unordered list* and *ordered list*. This element itself doesn't do much, it's main differences are the effect they have on their child elements. The first one renders *bullets* as their children and the second one renders *numbers*.

```html
<ul>
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

The `img` tag is used to render images. It must have a `src` attribute with the path to the image resource.

```html
<img src="flag.jpeg" />
```

### Containers

There are two mostly used containers. `span` and `div`, their main difference is about the default styles, where `div` *occupies the whole line* and `span` *only takes the space of it's content* by default. In *CSS* `div`s have `display: block` by default and `span`s have `display: inline-block`

While `span`s should only contain text, `div`s can contain anything. The usage of both this containers should be avoided when there are other elements that make more sense *semantically*.

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

### Style `<style>`

Style elements are used to insert CSS code *inlined* on the page.

Example

```css
h2 {
    font-size: "14px"
}
```

### Script `<script>`

Script tags are used to include *javascript* code, either by embedding it or importing it with the `src` attribute. Another common attribute for `script` is `async`. This attribute tells the browser that the javascript file can be executed *asynchronously*, only affects external scritps.

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
