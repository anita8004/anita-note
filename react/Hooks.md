# React Hooks

## Hook的規則

- 只在最上層呼叫Hook，不可以在迴圈、條件式或巢狀的function中呼叫Hook
- 只在React Function中呼叫Hook

## useState
```jsx
import React, { useState } from 'react';

function Example() {
  const [count, setCount] = useState(0);
  return (
    <div>
      <span>{ count }</span>
      <button onClick={setCount(1)}>Add 1</button>
    </div>
  )
}

```

## useEffect

可以使用componentDidMount，componentDidUpdate，與 componentWillUnmount功能
可以同時使用多個useEffect

```jsx
useEffect(() => {
  // componentDidMount，componentDidUpdate
  return () => {
    // componentWillUnmount
  }
}, [count]) // 只有count變更時才重新執行該useEffect, 如果設定[]則只會在mount時執行一次
```

## useContext

讓你不需要巢狀化就可以訂閱 React context

```jsx
function Example() {
  const local = useContext(LocaleContext);
  const theme = useContext(ThemeContext);
}
```

## useReducer

讓你在複雜的 component 中用 reducer 管理 local state

```jsx
function Example() {
  const [todos, dispatch] = useReducer(todosReducer)
}
```

## useMemo

讓你可以透過「記住」先前的計算來快取多個 render 之間的計算

```jsx
const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
```

## useCallback

## useRef

## useLayoutEffect

與宣告 useEffect 本身相同，但它會在所有 DOM 改變後，同步調用。使用它來讀取 DOM layout 並同步重新 render。在瀏覽器執行繪製之前，useLayoutEffect 內部的更新將被同步刷新。