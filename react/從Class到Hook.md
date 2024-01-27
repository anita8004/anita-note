# 從 Class 到 Hook

## 生命週期方法與 Hook 如何對應？

- constructor：Function component 不需要 constructor。你可以在呼叫 useState 時初始化 state。如果初始化 state 的操作代價很高，你可以傳遞一個 function 到 useState。
- getDerivedStateFromProps：改為在 render 時安排更新。
- shouldComponentUpdate：參考 React.memo 如下。
- render：這是 function component body 本身。
- componentDidMount、componentDidUpdate、componentWillUnmount：useEffect Hook 可以表達這些所有的組合（包含少見和常見）的情況
- getSnapshotBeforeUpdate、componentDidCatch 和 getDerivedStateFromError：現在沒有 Hook 等價於這些方法，，但是它們未來很快會被加入。


---

## 參考資料：
- https://zh-hant.legacy.reactjs.org/docs/hooks-faq.html#do-hooks-work-with-static-typing