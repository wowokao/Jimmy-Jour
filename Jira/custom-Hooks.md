## useDebounce

Debounce functions in JavaScript are higher-order functions that limit the rate at which another function gets called.

```js
const debounce = (fn, delay) => {
  let timeout
  return () => {
    clearTimeout(timeout)
    timeout = setTimeout(fn, delay)
  }
}

const log = debounce(() => console.log("call"), 5000)

log()
log()
log()
// only once call  
```

#### Write it in Hooks

```js

const useDebounce = (val, delay) => {
  const [debouncedVal, setDebounceVal] = useState(val)

  useEffect(() => {
    const timeout = setTimeout(() => setDebounceVal(val), delay)
    return () => clearTimeout(timeour)
  })

  return debouncedVal
}

```

