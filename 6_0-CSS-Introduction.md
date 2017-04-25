## CSS - Introduction

### What is CSS?

CSS (Cascading Style Sheets) is a stylesheet language used to describe HTML or XML. CSS is the main responsible for page styling, positioning elements and describe how they should render in different media. Although it is normally used to describe the layout *on screen* it can be used to define printed and projected layouts.

### CSS and HTML relation

Cascading style sheets CSS affects HTML by defining rules that change the way elements are displayed:

### What is a CSS Rule?

A CSS rule is composed by two parts:

**Properties** - Describe element presentation, can go from color, font-size, text-underline, visible or not, and so on.

Example: "I want elements to be blue, bordered and it big font"

**Selector** - *Selects* the element which the properties are gonna have effect into.

*Properties* and *Selectors* are separated by a colon (:) and should have a semi-colon at the end. If the property is the last one in the declaration, it is not needed, however, it is taken as good practice.

Example: "I want to apply this rule to *this* element"

```css
.post-title {
    font-size: 14px;
    font-weight: bold;
}
/* This rule makes the element with "post-title" class become bold and with 14px font. */
```


### Including CSS in the page

#### Embed CSS on HTML 

When CSS is embedded in HTML it is directly written in the same html file, inside the `<head>` element. Although this works, it is normally an unsustained way of keeping your CSS.

Example:
```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS</title>
    <style>
        h1 { font-size: 14px }
    </style>
</head>
<body>
  
</body>
</html>
```

#### Inline styles

Inline styles are styles defined in the element they're gonna by applied, using the `style` attribute. 

Example:
```html
<h1 style="font-size: 14px">Title</h1>
```

This approach is not recommended too, as it is even less maintainable than the embedded one and could lead to a lot of copy paste to *apply the same style to different elements*. This is also *too specific* and can break any other CSS rules applied by embedding or including an external file.

#### Including external files

An external stylesheet is when you include your CSS from a different file, with the `.css` extension through a `link` tag.

```html
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>External Stylesheet</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  
</body>
</html>
```

