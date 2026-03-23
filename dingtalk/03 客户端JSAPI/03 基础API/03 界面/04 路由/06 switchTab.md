---
title: "switchTab"
source: "https://open.dingtalk.com/document/development/jsapi-switch-tab"
category: "客户端JSAPI / 基础API / 界面 / 路由"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-switch-tab_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-switch-tab_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用switchTab，跳转到指定 tabBar 页面，并关闭其他所有非 tabBar 页面。

只能跳转在app.json里配置的tabbar页面，例如app.json中配置了叫”我的“的Tab页面，如下：

```
// app.json
{
  "tabBar": {
    "items": [{
      "pagePath": "user",
      "name": "我的"
    }]
  }
}
```

这样调用switchTab才可以跳转到”我的“这个tab，代码如下：

```
dd.switchTab({
  url: '/user'
})
```

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11539) |

## 支持应用类型

| 应用类型 | 是否支持调用 |
| --- | --- |
| 企业内部应用 | 是 |
| 第三方企业应用 | 是 |
| 第三方个人应用 | 是 |

## 鉴权规则

无需鉴权即可直接调用

## **参数说明**

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| --- | --- | --- | --- | --- |
| url | String | 是 | /user | 跳转的 tabBar 页面的路径（需在 app.json 的 tabBar 字段定义的页面）。  路径后不能带参数。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
dd.switchTab({
  url: '/user',
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```