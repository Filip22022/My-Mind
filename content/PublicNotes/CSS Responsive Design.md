---
title: CSS Responsive Design
Date created: 2024-07-09 15:10
Aliases: Media Query
  - Public
---

Responsive design refers to designing websites in a way that will allow them to look good on screens of all sizes, without elements falling out of place.

One of the most important factors in responsive design is using [[CSS Length Units#Relative Units|Relative Units]] along with `min-width/height` and `max-width/height` properties to ensure elements stay in correct size range.

### Scaling Images
A common pattern used with images or videos is scaling the image automatically with it's container and hiding the overflowing part:
```css
.container {  
  width: 50%;  
  height: 200px;  
  overflow: hidden;  
}  
  
.container img {  
  max-width: 100%;  
  height: auto;  
  display: block;  
}
```
Alternatively the values can be swapped to ensure the container resizes with the image.


## Media Queries

### `<meta>` Viewport Tag
The `<meta>` element with `name="viewport"` tag instructs the browser on how to render website's scale and dimensions. 
Example: `<meta name="viewport" content="width=device-width, initial-scale=1" />`

The element can have [various attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Viewport_meta_tag#viewport_basics) that alter the size, zoom and scaling

### Media Query
Media queries define css rulesets based on size of current screen.
```css
@media only screen and (max-width: 480px) {  
  selector {  
    ...
  }  
}
```
- `@media` signifies the beginning of media query
- `only screen` is the media type designation, in modern css (media queries 4) only `screen`, `print` and `all` are possible values. The `only` keyword signifies that the rule only applies to the specified type
- `and (max-width: 400px)` *media feature* part of the query, they are the condition that must be met in order to render the css inside the query
#### Multiple Media Features
Media features can be chained together with the `and` keyword  to make the target more specific
```css
@media screen and (min-width: 400px) and (max-width: 480px) {}
```
Or they can be specified in comma separated list to achieve *"or"* behaviour:
```css
@media screen and (min-width: 400px), (max-width: 480px) {}
```


They can also be used separately to activate more than one ruleset:
```css
@media screen and (min-width: 400px) {}

@media screen and (max-width: 480px) {}
```
In this case the second ruleset can override or extend the first ruleset

### Available media features
- `min/max-width` in pixels
- `min/max-resolution` in dpi (dots per inch)
- `orientation` landscape or portrait