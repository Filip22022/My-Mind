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

## Creating the Grid

The grid layout is created by giving a container element a `display` property with value `grid` or `inline-grid`. The immediate children of the container will be grid items.

## Defining the Grid

The grid by itself doesn't have a defined form, and to display content we need to specify the grid template - rows, columns, areas and gaps with the following properties:

### `grid-template-columns` / `grid-template-rows`
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
### `grid-template-areas`
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

### `grid-template`
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

### `grid-auto-columns`/`grid-auto-rows`
Specifies the size of auto-generated (implicit) grid tracks. These properties accept a length value, percentage or fraction unit.

### `grid-auto-flow`
Controls the *auto-placement algorithm* for items that aren't explicitly placed on the grid. Possible values:
- `row` - auto fills items in each row before adding a second item to a column
- `column` - auto fills items in each column before adding a second item to a row
- `dense` - attempts to fill holes in the grid if smaller items come up

### `grid`
A shorthand for all other grid template properties. All values for explicit ***or*** implicit grid can be specified in one declaration. The property can accept values in three ways:
- same as [[#`grid-template`|grid-template]]
- `<grid-template-rows> / auto-flow [dense?] <grid-auto-columns>?` - sets template-rows to specified value and auto-flow to `column`
	- if auto-column property is omitted it will be set to `auto`
- `auto-flow [dense?] <grid-auto-rows>? / <grid-template-columns>` - sets template-columns to specified value and auto-flow to `row`
	- if auto-rows is omitted it will be set to `auto`

Values denoted with `?` can be omitted

## Grid Item Placement

Aside from being placed by *auto-placement algorithm* the items can be placed freely on the grid even overlapping each other with the use of following properties:

### `grid-column-start` / `grid-column-end` / `grid-row-start` / `grid-row-end`
These properties determine item's location by specifying on which lines the item begins and ends. The allowed values are:
- `<line>` referred to by a name or number, places the item's start/end on the specified line 
- `span <number>` the item will span across `<number>` of grid tracks
- `span <name>` the item will span until hitting the `<name>` line
- `auto` indicates auto-placement or an automatic span with default span of one

### `grid-column` / `grid-row`
Shorthand for column-start/column-end in the form `<start-line> / <end-line>`

### `grid-area`
Gives item a name that can be referenced by [[#`grid-template-areas`|grid-template-areas]].
Can also be used as a shorthand for `grid-column` + `grid-row` in the form: `<grid-row-start> / <grid-column-start> / <grid-row-end> / <grid-column-end>`

## Other Properties
### Container Properties

#### `column-gap`/`row-gap`
These properties specify the size of grid lines, effectively creating gaps between the items. They accept a length value

#### `gap`
Shorthand for setting both `column-gap` and `row-gap` at the same time

#### `justify-items`
Positions items along the row (*inline*) axis. Possible values:
- `start`
- `end`
- `center`
- `stretch` (default)

#### `align-items`
Positions items along the column (*block*) axis. Possible values:
- `stretch` (default)
- `start`
- `end`
- `center`
- `baseline`

#### `place-items`
Shorthand for `align-items` and `justify-items`, accepts two values in the form `align_value / justify_value` or one value for both properties.

#### `justify-content`
Positions the entire grid along the row (*inline*) axis. Possible values:
- `start`
- `end`
- `center`
- `stretch`
- `space-around` - even amount of space between grid items, half on the start and end
- `space-between` - even amount of space between grid items, no space on ends
- `space-evenly` - even amount of space between grid items and ends

#### `align-content`
Positions the entire grid along the column (*block*) axis. Possible values:
- `start`
- `end`
- `center`
- `stretch`
- `space-around` - even amount of space between grid items, half on the start and end
- `space-between` - even amount of space between grid items, no space on ends
- `space-evenly` - even amount of space between grid items and ends

#### `place-content`
Shorthand for `align-content` and `justify-content`, accepts two values in the form `align_value / justify_value` or one value for both properties.

### Item Properties

#### `z-index`
Controls the stacking order of items, higher value items will be put in front. 

#### `justify-self`
Controls the placement of the item along the row (*inline*) axis. Applies to a single grid item inside a cell. Possible values are:
- `start`
- `end`
- `center`
- `stretch` (default)

#### `align-self`
Controls the placement of the item along the column (*block*) axis. Applies to a single grid item inside a cell. Possible values are:
- `start`
- `end`
- `center`
- `stretch` (default)

#### `place-self`
Shorthand for `align-self` and `justify-self` in the form `<align-value> <justify-value>`


## Sizing
Additional options for sizing the grid and items
### Keywords
- `min-content` - sets size to the minimum size needed by the content
- `max-content` - sets size to the maximum size necessary for the content
- `auto` - automatically allocate the free space

### Functions
- `fit-content()` - uses the size available with respect to `min-content` and `max-content`
- `minmax()` - sets a minimum and maximum values for a length
- `min()` - sets a minimum value
- `max()` - sets a maximum value
- `repeat()` - takes the amount of repetitions and length, creates the specified number of tracks
	- `auto-fill` - fits as many columns as possible on a row
	- `auto-fit` - fits existing columns into the space expanding them
