---
title: CSS Transitions
Date created: 2024-07-20 19:12
Aliases:
tags: 
  - Public
---

CSS transitions are tools for managing the way changes happen to elements on the website.

If an element has a defined state change - changing color on hover for example - specifying a transitions can make it change the color gradually over a set time instead of abruptly.

## Transition Properties

### `transition-property`
Declares which css property will be transitioning, [list of properties allowing transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties)

This property can accept `all` as value to transition all changes in the same way.

### `transition-duration`
Defines how long will the transition take, accepts time values in seconds or milliseconds, for example `3s, 500ms`

### `transition-timing-function`
Controls the speed of transition in time, the default value `ease` starts and ends slowly, speeding up in the middle. List of [possible values](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-timing-function)

### `transition-delay`
Sets the wait time before the transition starts, with default of `0s`

### `transition`
shorthand for the four transition properties above, specified in order `<-property> <-duration> <-timing-function> <-delay>`. Omitting one of the properties will apply the default value. 

This property allows for defining multiple transitions by separating them with comas, for example:
```css
transition: 
	color 1s linear, 
	font-size 7s ease-in 1s;
```