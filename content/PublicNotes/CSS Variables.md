---
title: CSS Variables
Date created: 2024-08-23 17:27
Aliases:
tags: 
  - Public
---

Variables in css are created by declaring them as property with double hyphen `--` at the beginning followed by the variable name 
```css
selector {
	--variable-name: #ABDCAB;
}
```

Variable names are case sensitive and by convention separate words with hyphens.

we can use a previously defined variable as follows:
```css
selector {
	color: var(--variable-name)
}
```

## Scope

Variables declared in individual selector are accessible to that selector and it's children.  Specific selector variables override general variables
### Global variables
To create a globally accessible variable define it in the `:root` element
```css
:root {
	--variable: x;
}
```

## Fallback values
Variables can provide fallback values in case of improperly set variables:
```css
selector {  
  property: var(--main-background-color, #F3F3F3);  
}
```

they can also be chained:
```css
selector {
font-color: var(--main-color, var(--favorite-orange, var(--favorite-yellow, yellow)));  
}
```
falling back on next layers of variables in case of errors and finally settling `yellow` if all the variables are improperly set

## Variables with media queries
We can set the values of variables based on a media query allowing us to apply a dark mode setting or other changes

Example:
```css
@media screen and (min-width: 600px) {    
  :root {  
    /* Light Color Theme */  
    --body-background: lightblue;  
    --inner-margin: 6px;  
    --body-text-color: black;  
    --font-size: 18px;  
  }  
}  
  
@media screen and (max-width: 600px) {  
  :root {  
    /* Dark Color Theme */  
    --body-background: #000;  
    --inner-margin: 12px;  
    --body-text-color: #fff;  
    --font-size: 12px;  
  }  
}
```