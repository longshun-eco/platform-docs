---
title: "SJS概述"
source: "https://open.dingtalk.com/document/development/sjs-overview-1"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 框架 / SJS语法参考"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-sjs-overview-1_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-sjs-overview-1_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17SJS（safe/subset javascript）是小程序一套自定义脚本语言，可以在 AXML 中使用其构建页面结构。 SJS 是 JavaScript 语言的子集，与 JavaScript 是不同的语言，其语法并不与 JavaScript 一致，请勿将其等同于 JavaScript。

## 使用方式

在 index.sjs 文件中定义 SJS：

```javascript
// pages/index/index.sjs
const message = 'hello dingtalk';
const getMsg = x => x;
export default {
  message,
  getMsg,
};
```

index.js示例代码：

```
// pages/index/index.js
Page({
  data: {
    msg: 'hello taobao',
  },
});
```

index.axml示例代码：

```json
{{m1.message}}
{{m1.getMsg(msg)}}
```

页面输出：

```
hello dingtalk
hello taobao
```

**重要**

* sjs 中只支持使用 import、export 管理模块依赖**。**
* sjs 只能定义在 `.sjs`文件中，然后在 axml 中使用 `<import-sjs>`标签引入。
* sjs 可以调用其他 sjs 文件中定义的函数。
* sjs 是 JavaScript 语言的子集，请勿将其等同于 JavaScript。
* sjs 的运行环境和其他 JavaScript 代码是隔离的，sjs 中不能调用其他 JavaScript 文件中定义的函数，也不能调用小程序提供的 API。
* sjs 函数不能作为组件事件回调。
* sjs 不依赖于基础库版本，可以在所有版本小程序中运行。

## import-sjs 标签

index.js示例代码：

```
// pages/index/index.js
Page({
  data: {
    msg: 'hello dingtalk',
  },
});
```

index.sjs示例代码：

```javascript
// pages/index/index.sjs
function bar(prefix) {
  return prefix;
}
export default {
  foo: 'foo',
  bar: bar
};
```

namedExport.sjs示例代码：

```javascript
// pages/index/namedExport.sjs
export const x = 3;
export const y = 4;
```

index.axml示例代码：

```json
 {{test.bar(test.foo)}}

 {{test.bar(msg)}}

{{x}}
{{z}}
```

页面输出：

```
foo
hello dingtalk

```

| **属性** | **类型** | **是否必填** | **说明** |
| --- | --- | --- | --- |
| name | String | 是 | 当前`<import-sjs>` 标签的模块名。 |
| from | String | 是 | 引用 .sjs 文件的相对路径。 |

name 属性指定当前 `<import-sjs>` 标签的模块名。在单个 AXML 文件内，建议将 name 值设为唯一。若有重复模块名则按照先后顺序覆盖（后者覆盖前者）。不同 AXML 文件之间的 `<import-sjs>` 模块名不会相互覆盖。

name 属性可使用一个字符串表示默认模块名，也可使用 `{x}` 表示命名模块的导出。

**重要**

* 引用时务必使用“.sjs”文件后缀。
* 若定义了一个 .sjs模块，但从未引用，则该模块不会被解析与运行。