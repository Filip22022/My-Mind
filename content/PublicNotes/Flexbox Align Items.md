---
title: Flexbox Align Items
Date created: 2024-07-10 10:23
Aliases:
tags: 
  - Public
---

`align-items` property defines the layout along flex containers **cross axis**

[Browser support documentation](https://developer.mozilla.org/en-US/docs/Web/CSS/align-items#browser_compatibility)

Possible values:
- `stretch` (default) - tries to fill the container, respecting min/max-width
- `flex-start`/`start`/`self-start` - items are placed at the start of the cross axis. The difference between different start values is between working with `flex-direction` rules or `writing-mode` rules (see [[Flexbox Justify Content]] )
- `flex-end`/`end`/`self-end` - items are placed at the end of cross axis, differences as above
- `center` - items are centred in cross axis
- `baseling` - items are places so that their bases align

`safe` and `unsafe` keywords can be used to allow or prevent content rendering in an inaccessible way