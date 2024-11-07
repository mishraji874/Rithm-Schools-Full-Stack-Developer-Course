# CSS Transforms

Transforms are a newer CSS technology that allow us to move elements on the page by translating them, rotating them, scaling them, and more. Sometimes these `transforms` are used in isolation, but they’re more commonly found in conjunction with CSS animations, which we’ll get to in the next chapter.

There’s only one property you need to know to use transforms: the transform property. However, this property can take a variety of different values. Here’s an overview:

- `transform` – CSS transforms change the shape and position of the affected content and allow you to translate, rotate, scale, and skew elements.A transformation is an effect that lets an element change shape, size and position. Here are a few of the methods that can be values of transform property:
    - `translate` – The `translate()` method moves an element from its current position. For example, if you give an element the rule transform: `translate(50px,100px);`, the element will be 50 pixels to the right and 100 pixels down.
    - `rotate` – The `rotate()` method rotates an element clockwise or counter-clockwise according to a given degree. For example, if you give an element the rule `transform: rotate(90deg);`, the element will rotate 90° clockwise.
    - `scale` – The `scale()` method increases or decreases the size of an element (according to the parameters given for the width and height). For example, if you give an element the rule `transform: scale(2,3);`, the element will scaled 200% horizontally and 300% vertically.