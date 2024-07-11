---
title: CSS Box Model
Date created: 2024-07-08 10:14
Aliases:
tags: 
  - Public
---

Everything in a web document layout is represented as a box. When styling websites these boxes have to be manipulated to achieve the desired layout.

## Basic Box Composition

The box is composed of four layers, from the outermost to the innermost:
- Content area - Contains the actual content of the element, with size defined with *content width* and *content height*.
- Padding area - Extends the content space to create room from the content to the border. The thickness of the padding in each direction can be set separately or all can be set together.
- Border area - The space taken by the border of an element.
- Margin area - Extends from the border and includes the empty area separating the element from its neighbours.

### Shorthand
`padding` and `margin` values can be specified with separate properties:
```css
selector {
	padding-top: value;
	padding-right: value;
	padding-bottom: value;
	padding-left: value;
}
```

or with the shorthand `padding` property, in three different ways:

```css
selector {
	padding: value_top value_right value_bottom value_left;
	padding: value_top value_RightAndLeft value_bottom;
	padding: value_TopAndBottom value_RightAndLeft;
}
```

### Margin Collapse
The top and bottom margins of an element *collapse* maintaining the distance of elements equal to the larger of their margins.

While padding or vertical margins add together, and the space between elements is always equal to their sum, if an element with `margin-bottom: 10px` was placed above an element with `margin-top: 30px`, the space between them would only be 30px high, without counting the 10px.


### `box-sizing`

By default the `box-sizing` property is set to `content-box`, which means that the `width` and `height` properties change the dimensions of the element content's, and the margin, padding and borders are added on top of it. 
This can make it difficult to judge the actual size of an element. An alternative solution is to use the `box-sizing: border-box` property which makes `width` and `height` apply to the sum of element, padding and border dimensions. The margins are still added on top of that.