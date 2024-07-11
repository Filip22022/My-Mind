---
title: Flexbox Justify Content
Date created: 2024-07-10 09:52
Aliases:
tags: 
  - Public
---

The `justify-content` property defined item alignment along the main axis of a flex container, distributing any leftover space on the line and controling the alignment of overflowing items.

Not all browsers support all the possible values in the same way - [documentation](https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content#browser_compatibility)

Possible values:
- `flex-start`(default) - items grouped at the start of the flexbox
- `flex-end` - items grouped at the end of the flexbox
- `start` - items grouped at the start of `writing-mode` direction
- `end` - items grouped at the end of `writing-mode` direction
- `left` - items grouped to the left edge of the container, if conflicting with `flex-direction` behaves like `start`\
- `right` - items grouped to the right edge of the container, if conflicting with `flex-direction` behaves like `end`
- `center` - items are centred
- `space-between` - items are evenly distributed with first item on the start and last item on the end
- `space-around` - items are evenly distributed with equal space around each item (results in half space to the edges)
- `space-evenly` - items are evenly spaced (between themselves and to the edges) 


two additional keywords are `safe` and `unsafe` marking if an element can be pushed to render off-screen