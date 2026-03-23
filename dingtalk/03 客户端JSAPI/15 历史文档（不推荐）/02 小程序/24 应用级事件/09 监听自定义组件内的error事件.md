---
title: "监听自定义组件内的error事件"
source: "https://open.dingtalk.com/document/development/listen-to-error-events-in-custom-components"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 应用级事件"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-listen-to-error-events-in-custom-components_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-listen-to-error-events-in-custom-components_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**dd.onComponentError**监听小程序自定义组件内部JS代码的error事件。

## 扫码体验

![[development-listen-to-error-events-in-custom-components_p407124.png]]

## 使用说明

|  |  |  |  |
| --- | --- | --- | --- |
| **客户端** | **Android** | **iOS** | **PC** |
| 支持说明 | 支持 | 支持 | 不支持 |

**说明**

开发者可以通过[dd.canIUse](/document/orgapp/dd-caniuse)函数判断端上是否支持此能力。

## 示例代码

**说明**

示例代码以小程序index页面引入component自定义组件的用法为例。

### component的axml示例代码

```

```

### component的js示例代码

```java
Component({
  mixins: [],
  data: {
  },
  props: {},
  didMount() {},
  didUpdate() {},
  didUnmount() {},
  methods: {
    handleError(){
      throw new Error('component error');
    }
  },
});
```

### index.axml示例代码

```
    自定义组件
```

### index.js示例代码

```
Page({
  data: {},
  onLoad() {
    dd.onComponentError(this.callBack);
  },
  callBack(error, method, component){
    dd.alert({
      title:"监听自定义组件内的error异常",
      content:JSON.stringify(error)+JSON.stringify(method)+JSON.stringify(component),
    });
  },
  handleCancel(){
    dd.offComponentError(this.callBack);
  },
});
```

## 入参说明

|  |  |  |
| --- | --- | --- |
| 属性 | 类型 | 描述 |
| 回调函数 | Function | 自定义组件内部 JS 代码运行抛出错误时的回调函数。 |

## 回调函数说明

|  |  |  |
| --- | --- | --- |
| 属性 | 类型 | 描述 |
| error | Error | 标准error对象。 |
| method | String | 抛出错误的具体方法。 |
| component | Component | Component实例。 |