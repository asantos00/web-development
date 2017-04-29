## CSS - Box model

The CSS box model is one of the foundations of layouts on the web. On it's core it says that each element is represented as a rectangular box. 

Consider the box as an onion, having *content*, *padding*, *border* and *margin*. Each one of the layer being a customizable CSS property than can be set to match the layout.

### Box properties

![What is the box model?][box_model_properties]

[box_model_properties]: https://mdn.mozillademos.org/files/13647/box-model-standard-small.png

- [width](https://developer.mozilla.org/en-US/docs/Web/CSS/width) and [height](https://developer.mozilla.org/en-US/docs/Web/CSS/height) - Customize the dimensions of the content box, the place where element content is going to be displayed.

- [padding](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) - Customize the **inner margin** of a CSS box, *padding* is known as the inner space within a box. CSS allows to specify different paddings for every side (top, right, bottom, left).

- [border](https://developer.mozilla.org/en-US/docs/Web/CSS/border) - Border is the layer after *padding*. It represents (as the name says) the element's border. Border has as lot of properties that can be customized, from style, thickness to color.

- [margin](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) - Margin is the layer after border, it represents the outer space the element needs to have to the surrounding elements.

![Box model in chrome dev tools][box_model_dev_tools]

[box_model_dev_tools]: http://blog.teamtreehouse.com/wp-content/uploads/2014/05/chrome-computed.png

### Advanced box properties

- [overflow](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow) - Overflow defines how the element should behave when the content is bigger than the defined dimensions (it is widely used to define which elements should scroll or not, and which ones should crop).

- [display](https://developer.mozilla.org/en-US/docs/Web/CSS/display) - The type of box in CSS is defined by the *display* property. And is this property that defines how the element behaves when used around other elements.

The most common *display* properties are:

- `block` - With `display: block` the boxes are stacked one upon another, each box occupying the whole line.

- `inline` - With `display: inline` the box will be shown as if it was text. Boxes with this display type completely ignore *width* and *height*.

- `inline-block` - With `display: inline-block`, as the name says, this property is like a mix between `block` and `inline`. The main characteristic of this display type is that is allows to have elements flowing with the text but to customize *height* and *width*, keeping the *block integrity*.

