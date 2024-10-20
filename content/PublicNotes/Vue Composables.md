---
title: Vue Composables
Date created: 2024-09-23 12:18
Aliases:
tags: 
  - Public
---

[Vue Documentation on Composables](https://vuejs.org/guide/reusability/composables.html)

Composables are Composition API functions used to encapsulate stateful logic. They allow for use of [Composition API Functions](https://vuejs.org/api/#composition-api) and nesting other composables.


![[Vue Fetching Data from a Component#Example Composable]]
## Reactive State
If the composable takes a static input it will perform it's action once, on the other hand if the composable accepts a ref or a getter function and watches the effect (`watchEffect` and `toValue` in the example above) it will track any dependencies and re-run whenever a tracked dependency changes.

## Lifecycle Hooks
A composable can hook into the lifecycle of it's owner component:
```js
//composable code

onMounted(() => window.addEventListener('mousemove', update))
onUnmounted(() => window.removeEventListener('mousemove', update))

//return
```

which can be also abstracted into it's own composable:
```js
// event.js
import { onMounted, onUnmounted } from 'vue'

export function useEventListener(target, event, callback) {
  // if you want, you can also make this
  // support selector strings as target
  onMounted(() => target.addEventListener(event, callback))
  onUnmounted(() => target.removeEventListener(event, callback))
}
```
and used:
```js
// mouse.js
import { ref } from 'vue'
import { useEventListener } from './event'

export function useMouse() {
  const x = ref(0)
  const y = ref(0)

  useEventListener(window, 'mousemove', (event) => {
    x.value = event.pageX
    y.value = event.pageY
  })

  return { x, y }
}
```