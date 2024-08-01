---
title: CSS Positioning
Date created: 2024-07-08 19:45
Aliases:
tags: 
  - Public
---

By default the browser renders elements left to right, top to bottom as they stand in the html document, but this behaviour can be changed with [[CSS]] 

## `position`

The `position` property defines the element placement in the document. It can take one of five values:

- `static` (default) - appears in it's  html location
- `relative` - allows the use of *offset* properties of `top`, `right`, `bottom` and `left` to alter the element position from it's default static position
- `absolute` - removes the element from the static flow, rendering the element on top. Makes other elements ignore it and position like it's not on the page. The element will be positioned relatively to it's closes ancestor with `relative` positioning and *offset properties* can be used.
- `fixed` - removed from the static flow, rendering on top of other elements. Positioned relatively to the document page, making it appear in the same spot of the screen. Position using `top`, `right`, `bottom` and `left`
- `sticky` - the element is treated as relative, but only inside it's parent element
\

## `z-index`

The property defining the depth of the element placement, with the default value of `0`. Does not work on static elements

## `display`

The `display` property dictates if an element takes up the entire horizontal space, or if it can share it with other elements. The property has three possible values: 

- `inline` - element takes up only the space necessary to display it's content. Cannot be altered with `width` or `height` properties
- `block` - displayed on different line than other elements. Element takes up entire horizontal space by default, but `width` can be specified. The default `height` is the same as the content but can be altered.
- `display-block` - the element is displayed on the same line as other elements, but it's `width` and `height` can be specified.
- `flex` and `inline-flex` - making an element a [[CSS Flexbox|flex container]] 

## `float`

The property used to move an element as far left or right as possible. It accepts `left` or `right` as value and the element it's used on must have a specified `width`

## `clear`

This property specifies how an element should behave if it would "bump" into other elements on the page. The value tells which sides won't touch other elements in the same container, the possible values are: 
- `left`
- `right`
- `both`
- `none`