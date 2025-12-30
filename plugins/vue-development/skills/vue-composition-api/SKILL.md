---
name: vue-composition-api
description: Master Vue 3 Composition API with setup, ref, reactive, computed, watch, and composables for building scalable reactive applications.
---

# Vue Composition API

Master Vue 3's Composition API for building scalable, reusable, and type-safe reactive applications.

## Core Concepts

### Script Setup
```vue
<script setup lang="ts">
import { ref, computed } from 'vue'

const count = ref(0)
const doubled = computed(() => count.value * 2)

function increment() {
  count.value++
}
</script>

<template>
  <div>
    <p>{{ count }} x 2 = {{ doubled }}</p>
    <button @click="increment">Increment</button>
  </div>
</template>
```

### Composables
```typescript
// composables/useFetch.ts
export function useFetch<T>(url: string) {
  const data = ref<T | null>(null)
  const error = ref<Error | null>(null)
  const loading = ref(true)

  const fetchData = async () => {
    loading.value = true
    try {
      const response = await fetch(url)
      data.value = await response.json()
    } catch (e) {
      error.value = e as Error
    } finally {
      loading.value = false
    }
  }

  onMounted(fetchData)

  return { data, error, loading, refetch: fetchData }
}
```

### Reactive State
```typescript
import { reactive, toRefs } from 'vue'

const state = reactive({
  count: 0,
  message: 'Hello'
})

// Destructure while maintaining reactivity
const { count, message } = toRefs(state)
```

## Best Practices

1. Use `ref` for primitives, `reactive` for objects
2. Extract reusable logic into composables
3. Use TypeScript for type safety
4. Implement proper cleanup in `onUnmounted`
5. Use `computed` for derived state
6. Leverage `watchEffect` for side effects

## Resources
- https://vuejs.org/guide/extras/composition-api-faq.html
