---
title: Core CSS Syntax
Date created: 2024-07-03 19:53
Aliases:
tags: 
  - Public
---

CSS code can be written either as a ruleset in a `*.css` file or as an inline style within the `*.html` file tags.  In both of these cases the core syntax is the same, consisting of a collection of *declarations*

```declaration
property:value
```

The difference is that in case of a ruleset the declarations are placed inside a *declaration block* attached to a *selector*

```CSS
selector {
	property:value
}
```

While in case of inline CSS styling the declaration becomes the value of a html `style` *attribute* inside an *opening tag*
```html
<element style='value:attribute;'></element>
```

### Examples
```css
p {
	color: red;
	font-size: 20px;
}
```

```html
<p style='color:red; font-size: 20px;'> Text </p>
```
