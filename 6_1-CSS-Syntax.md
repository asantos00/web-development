## CSS - Syntax

CSS main function is to specify values to specific properties. The CSS engine uses the **selectors** to understand which elements should the properties and rules by applied to.

### Selectors

In order to apply our properties and values to style elements, it's needed to known how to target those elements. In CSS, that is done by **selectors**.

Selectors prefix a declaration block (CSS properties that are inside {}).

```css
div p {
    font-size: 12px;
}
```

CSS selectors can have some complexity, they can be chained, match multiple elements and be related with each other.

Example: *A CSS selector to target every h3 inside odd articles, only when the mouse is over it*

*Note:* When one CSS selector in a group is invalid, all selectors are ignored.

```css
article:nth-child(odd) h3:hover {
    /* Properties to apply to this element*/
}
```

In Cascading StyleSheets we can define multiple properties for the same element with conflicting values, in the future, it will be explained how CSS handles precedence, called the *cascade algorithm*.

### Other types of Statements

Rules are the most used and seen types of CSS statements, however, there are others.

#### At-rules

**At-rules** are used to convey metadata, conditional or descriptive information. As the name says, they start with an at (@), continue with an identifier (name of the rule) and end with a semi-colon. At-rules have their own syntax.

[At rules](https://developer.mozilla.org/en/docs/Web/CSS/At-rule)

Examples:

- @charset @import (metadata)
- @media @document (conditional)
- @font-face (descriptive)

```css
/* @import syntax example */
@import 'menu.css';
```

#### Nested statements

There are some *at-rules* that can be nested have have declaration blocks in them, in this case, those declarations will only be applied if at-rules' conditions are accomplished.

Example:

- @media content is only applied when the browser have those specific conditions(related to viewport, resolution, type of device, etc)

```css
@media (min-width: 720px) {
  h2 {
    font-size: 14px
  }
}

/* The rule is only applied when the page has a minimum of 720 pixels width */
```

### Readability good practices

#### White space

CSS ignores the majority of the white space you add in your code. However, that's not a reason to not use it. It's used to say that "programs must be written for people to read, and only incidentally for machines to execute", according to that, white space should be used to increase *code readability*.

- Leave a blank line at the end of a declaration block.
- Leave a white space between the selector and the {
- Leave a white space between the color and the value.
- Have different properties in different lines.
- End every property declaration with a semi-colon.

**Note:** There are properties where the white space is used and needed as *syntax*

```css
margin: 0 auto;
padding- left: 10px;
```

#### Comments

In an utopic world, class names and selectors should be intuitive enough to be clear why they're used, however, that isn't always possible. That's when we should use comments. 

Keep in mind that `good code doesn't need comments`. So if you find yourself writing a lot of comments, pay attention if you are doing everything you can to keep your code clean.

#### Shorthand

Sometimes CSS has different ways of defining the same properties, shorthand syntax is an example of that, a shorter syntax that can be used in some cases.

```css
/* top, right, bottom, left */
padding: 0 10px 15px 20px;

padding-top: 0;
padding-right: 10px;
padding-bottom: 15px;
padding-left: 20px;
```

The two blocks of declarations above do the exact same thing but one is (obviously) shorter than the other.

Keep in mind that shorthand are not always the most clear way of showing your intention.

#### Code standards

One of the things that really improves code in every language are coding standards. Pay attention to them, even if you are working alone, it is good to keep consistency between all your code, and CSS code clearly benefits from well defined coding standards.
