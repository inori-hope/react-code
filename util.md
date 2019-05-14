#### flattenChildren
    
* 支持数组、object类型
* 返回 `ReactTextComponent`
* 考虑 循环调用问题



#### escapeTextForBrowser
* 支持以下五种：
```js
var ESCAPE_LOOKUP = {
  "&": "&amp;",
  ">": "&gt;",
  "<": "&lt;",
  "\"": "&quot;",
  "'": "&#x27;",
  "/": "&#x2f;"
};
```



#### accumulate
```javascript
var isEmpty = a == null
```