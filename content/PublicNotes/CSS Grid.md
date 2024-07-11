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
Defined the columns and rows with list of values