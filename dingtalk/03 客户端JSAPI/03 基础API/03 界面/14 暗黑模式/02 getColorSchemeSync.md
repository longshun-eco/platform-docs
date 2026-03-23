---
title: "getColorSchemeSync"
source: "https://open.dingtalk.com/document/development/jsapi-get-color-scheme-sync"
category: "客户端JSAPI / 基础API / 界面 / 暗黑模式"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-get-color-scheme-sync_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-get-color-scheme-sync_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用getColorSchemeSync，获取钉钉当前显示模式。返回当前系统的显示模式"light" 或 "dark"。

**使用方法**

```javascript
const colorScheme = dd.canIUse("getColorSchemeSync") ? dd.getColorSchemeSync() : "light";
// use colorScheme
```

**监听显示模式事件**

通过 `dd.onColorSchemeChange` 监听显示模式变化，通过 `dd.offColorSchemeChange` 解除绑定。
代码示例：

```
Page({
  colorSchemeChangeHandler({ colorScheme }) {
        // use colorScheme
    },

    onLoad() {
    dd.onColorSchemeChange(this.colorSchemeChangeHandler);
  },

  unbind() {
    dd.onColorSchemeChange(this.colorSchemeChangeHandler);
  },
});
```

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10062) |

## 支持应用类型

| 应用类型 | 是否支持调用 |
| --- | --- |
| 企业内部应用 | 是 |
| 第三方企业应用 | 是 |
| 第三方个人应用 | 是 |

## 鉴权规则

无需鉴权即可直接调用

## **参数说明**

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
dd.getColorSchemeSync({});
```