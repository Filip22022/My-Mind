---
title: CSS Length Units
Date created: 2024-07-31 12:34
Aliases:
tags: 
  - Public
---

The lengths in [[CSS]] can be specified using two main types of units: relative and absolute

## Relative Units

Relative length units represent the measurement in terms of other distance. They can be based on font, viewport or query

### Relative Units Based on Font
These units are based on the font size of the element/it's parent. If the unit is prefixed with `r` character the unit is relative to the font-size of `root` element instead
- `cap/rcap` - nominal height of capital letters
- `ch/rch` - width of `0` glyph, assumes `0.5em`x`1em` by default
- `em/rem` - calculated font size of the element
- `ex/rex` - height of lowercase letters (`x`) in the font
- `ic/ric` - measure of the water ideograph glyph
- `lh/rlh` - equal to computed `line-height`

### Relative Units Based on Viewport
These units define values by percentages relative to the visible area of the document. These units represent the viewport based on browser's default viewport size, to use other viewport sizes prefix the unit with `s` for small, `l` for large or `d` for dynamic
- `vh` - percentage of viewport's initial *containing block* height
- `vw` - percentage of viewport's initial *containing block* width
- `vmax` - the largest of `vw` and `vh`
- `vmin` - the smallest of `vw` and `vh`
- `vb` - percentage of the size of initial *containing block* in the direction of `root`'s *block axis*
- `vi` - percentage of the size of initial *containing block* in the direction of `root`'s *inline axis*


### Relative Units Based on Container Query
These units define values relative to a query container.
- `cqw` - percentage of width of query container
- `cqh` - percentage of height of query container
- `cqi` - percentage of query container's *inline* size
- `cqb` - percentage of query container's *block* size
- `cqmin` - the smallest of `cqi` and `cqb`
- `cqmax` - the largest of `cqi` and `cqb`

## Absolute Units
Absolute length units represent a physical measurement. For low-dpi devices units are relative to a reference pixel and might not always be equal to their actual physical counterparts.

- `px` - one device pixel for screen displays. For high-resolution devices it might represent more device pixels
- `cm` - `96px/2.54`
- `mm` - `1cm/10`
- `Q` - one quarter of a millimetre `1cm/40`
- `in` - `96px`
- `pc` - `1in/6`
- `pt` - `1in/72`