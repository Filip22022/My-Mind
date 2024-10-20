---
title: Vue Computed Properties
Date created: 2024-10-14 18:49
Aliases:
tags: 
  - Public
---

Computed properties are ways to encapsulate logic with reactive data in Vue

## Basics

Computed functions expect a [getter function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/get#description) as an input, and return a **computed ref**, which behaves much like a normal [[Vue Ref Object|ref]]. Computed properties track their reactive dependencies and update bindings accordingly.

### Best Practices
- Don't create side effects in the getter functions
- Don't mutate computed values
### Example
```html
<script setup>
import { reactive, computed } from 'vue'

const author = reactive({
  name: 'John Doe',
  books: [
    'Vue 2 - Advanced Guide',
    'Vue 3 - Basic Guide',
    'Vue 4 - The Mystery'
  ]
})

// a computed ref
const publishedBooksMessage = computed(() => {
  return author.books.length > 0 ? 'Yes' : 'No'
})
</script>

<template>
  <p>Has published books:</p>
  <span>{{ publishedBooksMessage }}</span>
</template>
```