---
title: CSS Selectors
Date created: 2024-07-03 19:54
Aliases:
tags: 
  - Public
---

Selectors are specifiers used to target different elements of the page and apply css styles to them

## Types of Selectors

- Universal selector - selecting all elements
```css
* {
//css declarations
}
```

- Type selector - opening tag name of an html element
```css
type {
//css declarations
}
```

- Class selector - targeting the [[HTML Classes|class]]  attribute of an html element or group
```css
.class_value {
//css declarations
}
```

- ID selector - targeting [[HTML Id|id]] attribute, meaning a single html element
```css
#my-id {
//css declarations
}
```

- Attribute selector
	- By attribute type - targeting all elements with the attribute
	```css
	[attribute] {
	//css declarations
	}
	```
	- By attribute value - targeting all elements with the attribute and specified attribute value
	```css
	[attribute="value"] {
	//css declarations
	}
	```
	- By type, attribute and value - specifying the type of the element, the necessary attribute and it's value
	```css
	type[attribute="value"] {
	//css declarations
	}
	```

- Pseudo-class selector - can be attached to any other selector and targets a specific state ([[HTML Pseudo-classes|pseudo-class]])
```css
type:pseudo-class {
//css declarations
}
```
- Mixed selectors - requiring a selected element to match more than one selector
```css
type.class {
//would target type elements with class
}
```
- Descendant selector - targeting an element out of children of another selected element(s)
```css
.class type{
//would target type elements which are children of elements with class
}
```

### Multiple Selectors
In order to add the same style to multiple selectors, separate the selectors with a comma over one declaration block:
```css
type-selector,
.class-selector {
//css declarations
}
```

## Selector Priority
The browser displays css styles based on their specificity. Id's are the most specific and thus override other selectors used. 

The specificity hierarchy:
1. Inline styles
2. Id selectors
3. Classes, pseudo-class, Attributes
4. Elements, pseudo-elements

In case of more complicated selectors the specificity is calculated based on three categories of weight corresponding to three types of selectors (id - class - type). For each selector belonging to a category increase the weight value by 1 in it's column.

```css
[type="password"]             /* 0-1-0 */
input:focus                   /* 0-1-1 */
:root #myApp input:required   /* 1-2-1 */
```

In case of two selectors targeting the same element, their specificity is compared based on columns left to right. If a selector has a bigger value in the id column, it wins the comparison regardless of the values in class and element columns.

>[!info]
>Inline Styles always have the highest specificity unless `!important` is used
>

