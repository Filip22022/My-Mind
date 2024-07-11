---
title: CSS Flexbox
Date created: 2024-07-09 15:39
Aliases: felxbox
tags: 
  - Public
---

[Flexbox guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

Flexible Box Layout is a layout tool for positioning elements on a website.

Flexbox layout works using *flex containers* designated by setting an element's `display` property to `flex` or `inline-flex` and `flex items` - direct children of the flex container.

### `display:flex`

This property creates a block *flex container*, and makes all it's immediate children *flex items*. The element will remain block level, but the child elements will not begin on new lines.

The child elements (flex items) will change size and location according to the size and position of the container

The `inline-flex` property creates a flex container that will be an inline elemet.

## Flexbox Structure

A flexbox  is defined with its `main` and `cross` dimensions, with `size`, `start`, `end`, and `axis` being defined fort both of them. The direction of the main axis (horizontal or vertical) is decided by `flex-direction` property

## Flexbox Properties

### Container Properties
- `display` - `flex` or `inline-flex`
- `flex-direction` - `row`, `row-reverse`, `colun` or `column-reverse`
- `flex wrap` - should items try to fit onto one line or wrap: `nowrap`, `wrap` or `wrap-reverse`
- `flex-flow` - direction and wrap shorthand, accepts direction value and wrap value. default: `row nowrap`
- `justify-content` - [[Flexbox Justify Content]] - main axis item placement on a line
- `align-items` - [[Flexbox Align Items]] - cross axis item placement on a line
- `align-content` - line alignment on cross axis. Works only on multi-line containers with `wrap` or `wrap-reverse`. Works identically to [[Flexbox Justify Content]] 
- `gap`, `row-gap`, `column-gap` - controls minimal space between flex items. `gap` can take two values in form `row-gap col-gap`
### Item Properties
- `order` - order in which flex items appear in the container, source order by default, and default in case of ties
- `flex` - preferred shorthand for `grow`, `shrink` and `basis`. the default value is `0 1 auto`. 
	- Setting it with a single value `v` will result in  `flex-grow: v; flex-shrink:1; flex-basis: 0%;`
	- Setting with two values will set `grow` and `basis` if second value is valid `basis` value. If two relative values are provided it will set `grow` and `shrink`
- `flex-grow` - defines the ability of a flex item to grow if necessary, accepts a unitless value that is relative to other flex items. Default `0`
- `flex-shrink` - defines the ability of a flex item to shrink, accepts a unitless value relative to other items. Bigger values mean the item will shrink relatively more. Default `1`
- `flex basis` - default size of an element. Accepts a length measure or a keyword, `auto` results in following `width`/`height` properties, `content` results in sizing based on content
- `align-self` - overrides default container alignment for an item. Works like [[Flexbox Align Items]]. `float` `clear` and `vertical-align` have no effect on flex items