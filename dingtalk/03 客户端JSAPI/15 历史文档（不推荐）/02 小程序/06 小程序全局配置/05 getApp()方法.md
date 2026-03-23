---
title: "getApp()方法"
source: "https://open.dingtalk.com/document/development/getapp-method-1"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 小程序全局配置"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-getapp-method-1_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-getapp-method-1_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17小程序提供了全局的getApp()方法，可以获取到小程序实例，一般用在各个子页面之中获取顶层应用。

```javascript
var app = getApp()
console.log(app.globalData) // 获取 globalData
```

**重要**

* `App()`必须在 `app.js` 里调用，且不能调用多次。
* 不要在 `App()` 内定义的函数中调用 `getApp()`，使用 `this` 就可以拿到 `app` 实例。
* 不要在 `onLaunch` 里调用[getCurrentPages 方法](/document/orgapp/getcurrentpages-methods)，这个时候 `page` 还没有生成。
* 通过 `getApp()` 获取实例之后，不要私自调用生命周期函数。

全局变量如果在一个页面中被改变，会在所有页面中都有效。

全局的数据可以在 App() 中设置，各个子页面通过全局函数 getApp() 可以获取全局的应用实例。

app.js示例代码：

```
// app.js
App({
  globalData: 1
})
```

a.js示例代码：

```javascript
// a.js

// localValue 只在 a.js 有效
var localValue = 'a'
// 生成 app 实例
var app = getApp()
// 拿到全局数据，并改变它
app.globalData++
```

b.js示例代码：

```javascript
// b.js

// localValue 只在 b.js 有效
var localValue = 'b'
// 如果 a.js 先运行，globalData 会返回 2
console.log(getApp().globalData)
```

上面代码中，`a.js`和`b.js`都声明了变量`localValue`，它们不会互相影响，因为各个脚本声明的变量和函数只在该文件中有效。