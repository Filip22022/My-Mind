---
title: CSS Grid
Date created: 2024-07-10 17:48
Aliases:
tags: 
  - Public
---

[Grid Guide](https://css-tricks.com/snippets/css/complete-guide-grid/)

Grid is a layout system alternative to [[CSS Flexbox]]. 

## Terminology

### Grid Container
An element with `display: grid` property, makes it's direct children *grid items*
### Grid Item
A direct descendant of a *grid container*
### Grid Line
A dividing line between the columns or rows of a grid
### Grid Cell
A single unit of the grid, placed between two adjacent column grid lines and between two adjacent row grid lines
### Grid Track
Space Between two adjacent grid lines - a column or a row
### Grid Area
A rectangular part of the grid

## Properties
### Container Properties
#### Display
Defines the element as a grid container and establishes grid formatting context. Possible values are `grid` and `inline-grid`
#### Grid-template-columns / Grid-template-rows
Defined the columns/rows with list of values. For each row/column two values can be specified:
- track-size - length, percentage or fraction of free space (`fr` unit)
- line-name - chosen name

examples:
```css
selector {
	grid-template-columns: [name] 25%;
	grid-template-columns: [startname] 25% [endname];
	grid-template-columns: [name1 name2] 2fr [name3] 50%;
}
```
#### Grid-template-areas
Defines the grid by assigning the grid areas specified with `grid-area` property. A `.` signifies an empty cell, and repeating an area name causes the content to span more cells. Each row needs to have the same number of cells.
```css
#header {
	grid-area: header;
}

...

selector {
	grid-template-areas: 
		"header header header"
		"main" . "side"
		"footer footer footer";
}
```

#### Grid-template
Shorthand for setting template-columns, template-rows and template-areas at the same time. Accepts `none` to reset initial property values or `<grid-template-rows>/<grid-template-columns>` to set the specified vales and set `template-areas` to `none`. This property doesn't reset implicit grid properties `auto-columns`, `auto-rows` and `auto-flow`, and using the `grid` property is recommended for that reason.

The syntax for setting all three properties is as follows:
```css
selector {
	grid-template:
		[row-startname] "area area area" height [row-endname]
		[row-startname] "area area area" height [row-endname]
		/ auto 1fr 50% <- column syntax
}
```




