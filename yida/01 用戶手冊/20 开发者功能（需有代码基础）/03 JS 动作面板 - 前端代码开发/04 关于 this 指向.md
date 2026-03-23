---
title: "关于 this 指向"
source: "https://docs.aliwork.com/docs/yida_support/lbtl0t/ocmxyv/tucdd3"
category: "用戶手冊 / 开发者功能（需有代码基础） / JS 动作面板 - 前端代码开发"
updated: 
tags:
  - yida
  - 用戶手冊
---

## 1. 前景提要

-   了解 this 的指向需要先了解 JavaScript 中 this 的指向
-   在绝大多数情况下，函数的调用方式决定了 this 的值（运行时绑定）。this 不能在执行期间被赋值，并且在每次函数被调用时 this 的值也可能会不同。ES5 引入了 [bind](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Function/bind) 方法来设置函数的 this 值，而不用考虑函数如何被调用的。ES2015 引入了[箭头函数](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Functions/Arrow_functions)，箭头函数不提供自身的 this 绑定（this 的值将保持为闭合词法上下文的值）。

![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/ico/favicon.ico)[

![](https://yida-support.oss-cn-shanghai.aliyuncs.com/static/ico/favicon.ico)

this - JavaScript | MDN

https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/this

](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/this)

## 2. 宜搭动作面板中的 this

-   在了解了 JavaScript this 之后，在宜搭动作面板中调用函数只需要注意是否有 `export` 关键字即可。
-   建议，纯工具函数不涉及任何页面上下文，比如随机生成一个字符串 `function uid() { return new Date().getTime().toString(32); }` , 不需要使用 export 关键字，否则所有方法都要使用 export 关键字，并且使用 this 来调用。

案例一

```javascript
export function a() {
  console.log(this);
}
export function b() {
  this.a(); // 正确, a 方法中可以正确的获取宜搭渲染引擎上下文 this
  a(); // 错误, a 方法中无法获取宜搭渲染引擎上下文 this
}
```

案例二

```javascript
function a() {
  console.log(this);
}
export function b() {
  this.a(); // 错误且会报错，a 方法没有通过 export 关键字导入的方法无法使用宜搭渲染引擎上下文 this 去调用
  a(); // 错误, a 方法中无法获取宜搭渲染引擎上下文 this
}
```

案例三

```javascript
export function a() {
  console.log(this);
}
function b() {
  a(); // 错误, b 方法没有使用 export 关键字且没有使用 this.a() 来调用，所以 a 方法中无法获取宜搭渲染引擎上下文 this
}
```
