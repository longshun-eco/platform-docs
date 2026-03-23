---
title: "showActionSheet"
source: "https://open.dingtalk.com/document/development/jsapi-show-action-sheet"
category: "客户端JSAPI / 基础API / 界面 / 交互反馈"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-show-action-sheet_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-show-action-sheet_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用dd.showActionSheet，显示操作菜单。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 7.0.10 | 7.0.10 | 7.0.0 | 7.0.10 | 7.0.10 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10071) |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10071) |

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
| items | Array<String> | 是 | ['北京', '上海', '杭州'] | 菜单按钮文字数组。 |
| title | String | 是 | 夏天去哪里玩 | 菜单标题。 |
| cancelButtonText | String | 是 | 我不去了 | 取消按钮文案。  Android平台此字段无效，不会显示取消按钮。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| index | Number | 0 | 被点击的按钮的索引，从0开始。  点击取消或蒙层时返回 -1。 |

## **示例****代码**

### 默认出入参

```javascript
dd.showActionSheet({
  items: ['北京', '上海', '杭州'],
  title: '夏天去哪里玩',
  cancelButtonText: '我不去了',
  success: (res) => {
    const { index } = res;
  },
  fail: () => {},
  complete: () => {},
});
```

`success`返回对象示例：

```json
{ "index": 0 }
```