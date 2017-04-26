## CSS Selectors in depth

CSS selectors are *the first part* of a CSS rule, and are one of the more important parts of CSS, they define which elements will the rules be applied into.

**Simple** - Match elements based on element type, *class* or *id*

**Attribute** - Match elements based on their attributes and/or respective values

**Pseudo-classes** - Match elements in a certain state.

**Pseudo-elements** - Match content or parts of it that are in a certain position related to an element, aren't a real element but can act as one.

**Combinators** - Not exactly a selector, are ways of combining and relation selectors.

**Multiple** - Not a separate selector, is the idea that you can use multiple selectors in the same rule

### Simple selectors

Simple selectors have no *logic*, they directly select one of more elements based on type, *class* or *id*.

#### Type or element selectors

Type of elements selectors are just the name of the element in HTML.

```html
<p>
    I'm a paragraph
</p>

<div>
    I'm a div
</div>
```

```css
p {
    font-size: 12px;
}

div {
    font-size: 14px;
}
```

#### Class selectors

Class selectors are just a dot `.` followed by the class name.

```html
<img class="top-image" src="img.png" />

<img class="footer-image" src="footer.png" />
```

```css
.top-image {
    width: 100%;
}

.footer-image {
    width: 50%;
}
```

#### Id selectors

Id selectors consist in an hash followed by the id of the element.

```html
<img id="logo" src="logo.png" />

<div id="side-menu" />
```

```css
#logo {
    width: 200px;
}

#side-menu {
    display: none;
}
```

#### Universal selector

Universal selector selects all elements in a page, it is represented by (\*) and selects all elements.

```css
/* Gives a padding of 5 to every element and a color of red */
* {
    padding: 5px;
    background-color: red;
}
```

#### Combinators

Combinators allow to combine multiple selectors together, you can select elements related to other elements. 

There are four combinators:

- Descendant - ` (space)` - Selects an element inside other (directly or not)

- Child - `>` - Selects an immediate child of another element

- Adjacent - `+` - Selects an element next to another, in the same hierarchy level

- Sibling - `~` - Selects an element that are at same hierarchy level, not necessarily next to it

```html
<section>
  <h2>Heading 1</h2>
  <p>Paragraph 1</p>
  <p>Paragraph 2</p>
  <div>
    <h2>Heading 2</h2>
    <p>Paragraph 3</p>
    <p>Paragraph 4</p>
  </div>
</section>
```

```css
section p {
  color: blue;
}

section > p {
  background-color: yellow;
}

h2 + p {
  text-transform: uppercase;
}

h2 ~ p {
  border: 1px dashed black;
}
```


### Attribute selectors

Attribute selectors match elements based on attributes and attribute values. Their generic syntax consists of square brackets ([]) containing an attribute name and an optional condition to match against the attribute value.

#### Presence and value

- `[attr]` - Select elements with the attribute `attr`.

- `[attr=val]` - Select elements with the attribute `attr` equaling `val`.

- `[attr~=val]` - Select elements with the attribute `attr` having `val` as an element of a list of values separated by spaces

```html
<ul class="shopping-cart">
    <li data-quantity="2" data-discount data-category="tech storage">Memory card</li>
    <li data-quantity="1" data-discount data-category="tech camera">Go Pro Hero Black 4</li>
    <li data-quantity="1" data-brand="Apple">MacBook Pro 2016</li>
</ul>
```

```css
/* Targets Memory Card and Go Pro */
[data-discount] {
    color: red;
}

/* Targets MacBook Pro */
[data-brand="Apple"] {
    font-weight: bold;
}

/* Targets Memory Card */
[data-category~="storage"] {
    color: blue;
}
```

#### Substring and value attribute

Substring and value attribute selectors are also known as "RegEx-like" because they offer matching almost as flexible as a regular expression.

- `[attr|=val]` - Selects elements with attribute `attr` which the value is exactly `val` or `val-` (widely used for language selection).

- `[attr^=val]` - Selects elements with attribute `attr` and `value` starting with `val`.

- `[attr$=val]` - Selects elements with attribute `attr` and `value` ending with `val`.

- `[attr*=val]` - Selects elements with attribute `attr` and `value` containing `val` (the difference to `[attr~=val]` is that this one doesn't consider spaces and item delimiters in val but as characters).

```html
<ul class="shopping-cart">
    <li data-quantity="2" lang="en-US" data-discount data-category="tech storage">SSD 256 GB</li>
    <li data-quantity="1"  data-product-code="APPLEMBP2016">MacBook Pro 2016</li>
    <li data-quantity="1" data-product-code="APPLEHDMIVGAADAPTER">HDMI to VGA adapter</li>
    <li data-quantity="1" data-product-code="SSDADAPTER">SSD 2.5'' to 3.5 Adapter</li>
</ul>
```

```css
/* Targets SSD */
[lang|=en] {
    color: red;
}

/* Targets MacBook Pro and HDMI to VGA adapter*/
[data-product-code^="APPLE"] {
    font-weight: bold;
}

/* Targets both adapters */
[data-product-code$="ADAPTER"] {
    color: green;
}

/* Targets SSD */
[data-category*="orage"] {
    background-color: red;
}
```



