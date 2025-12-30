---
name: react-hooks-patterns
description: Master React hooks patterns including useState, useEffect, useContext, custom hooks, and advanced patterns for building scalable React applications.
---

# React Hooks Patterns

Master modern React hooks patterns for building scalable, maintainable applications with proper state management, side effects, and custom logic reuse.

## Common Hooks

### useState
```typescript
const [count, setCount] = useState(0);
const [user, setUser] = useState<User | null>(null);

// Functional updates
setCount(prev => prev + 1);
```

### useEffect
```typescript
useEffect(() => {
  // Side effect
  const subscription = api.subscribe();
  return () => subscription.unsubscribe();
}, [dependencies]);
```

### useContext
```typescript
const theme = useContext(ThemeContext);
```

### useMemo & useCallback
```typescript
const memoized = useMemo(() => expensive(a, b), [a, b]);
const callback = useCallback(() => doSomething(a), [a]);
```

### Custom Hooks
```typescript
function useFetch<T>(url: string) {
  const [data, setData] = useState<T | null>(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState<Error | null>(null);

  useEffect(() => {
    fetch(url)
      .then(res => res.json())
      .then(setData)
      .catch(setError)
      .finally(() => setLoading(false));
  }, [url]);

  return { data, loading, error };
}
```

## Best Practices

1. Always provide dependency arrays
2. Use useCallback for event handlers
3. Create custom hooks for reusable logic
4. Keep components focused and small
5. Use TypeScript for type safety
6. Clean up effects properly
7. Avoid excessive use of useEffect

## Resources

- https://react.dev/reference/react
- https://usehooks.com
