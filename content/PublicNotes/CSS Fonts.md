---
title: CSS Fonts
Date created: 2024-07-09 10:20
Aliases:
tags: 
  - Public
---

As most websites consist largely of text, it's important to ensure readability and styling of the textual elements. 

## Font Family

The `font-family` property specifies which font should be used for rendering the element's text.

To choose a font that will be recognized in most browsers use [web safe fonts](https://www.cssfontstack.com/)
Other fonts can be found on free font services like [Google Fonts](https://fonts.google.com/) or [Adobe Fonts](https://fonts.adobe.com/)

### Linking a Web Font
Web font providers will usually provide a link that can be used on your site that will connect the font

```html
<!-- Example -->
<head>  
  <!-- Add the link element for Google Fonts along with other metadata -->  
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@100&display=swap" rel="stylesheet">  
</head>
```

A linked font can be then used in the stylesheet

```css
selector {
	font-family: 'Roboto';
}
```

### Adding a Font File

A downloaded font files can be linked with a stylesheet using `@font-face` ruleset by providing the path to the font files

```css
// Example
@font-face {  
  font-family: 'CustomName';  
  src: url('fonts/Roboto.woff2') format('woff2'),  
       url('fonts/Roboto.woff') format('woff'),  
       url('fonts/Roboto.ttf') format('truetype');  
}
```

In this case the usage is as follows

```css
selector {
	font-family: 'CustomName';
}
```
### Fallback Fonts

If more than one font is specified in the `font-family` directive, the browser will try to use them in the order they're provided in. It allows to safeguard a website for when the user/browser doesn't have the desired font.

```css
selector {
	font-family: Georgia, Carlson, "Times New Roman"
}
```

`serif` and `sans-serif` can be also used as fallback keywords, to apply any serif or non-serif font that is available

## Font Weight & Style
\
The `font-weight` can take keyword values `bolder`, `bold`, `normal`, `lighter`, as well as numerical values from `1` to `1000`. Default weight is `400` and `bold` equals to `700`

Not all fonts can be assigned numeric weight, and not all numeric weights are available to all fonts.

`font-style` on the other hand is used to italicize the text. It accepts either `italic` or `normal` as value.

## `text-transform`

Transforming the text can make it appear all uppercase of all lowercase by using the `uppercase`/`lowercase` values.


## Text Layout

The text layout can be altered with few different properties:

- `letter-spacing` - sets the horizontal distance between characters
- `wors-spacing` - sets the horizontal space between words
- `line-height` - sets how tall each line of the text is, unitless values will be relative to font size
- `text-align` - aligns the text within it's parent element 

