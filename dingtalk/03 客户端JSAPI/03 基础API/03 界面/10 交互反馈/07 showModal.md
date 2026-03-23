---
title: "showModal"
source: "https://open.dingtalk.com/document/development/jsapi-show-modal"
category: "客户端JSAPI / 基础API / 界面 / 交互反馈"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-show-modal_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-show-modal_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

增强版modal弹浮层

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11615) |
| 小程序 | 7.0.10 | 7.0.10 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=11615) |

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
| cells | Array<String> | 否 | [ { "image":"https://img.alicdn.com/tfs/TB1KzrwRFXXXXasXXXXXXXXXXXX-540-380.png", "title":"DEMO版本更新", "content":"图片尺寸是540x380;" }, { "image":"https://img.alicdn.com/tfs/TB1KzrwRFXXXXasXXXXXXXXXXXX-540-380.png", "title":"DEMO版本更新", "content":"图片尺寸是540x380;" } ] | 浮层元素数组，每一个item为一个包含image、title、content内容的对象。 |
| image | String | 否 | image示例值 | 图片地址。 |
| title | String | 否 | title示例值 | 标题。 |
| content | String | 否 | content示例值 | 文本内容。 |
| buttonLabels | Array<String> | 是 | ["了解更多","知道了"] | 按钮列表，至少有一个按钮，最多两个按钮。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| buttonIndex | String | 1 | 被点击按钮的索引。  从0开始。 |

## **示例****代码**

### 默认出入参

```javascript
dd.showModal({
  cells: [
    {
      image:
        'https://img.alicdn.com/tfs/TB1KzrwRFXXXXasXXXXXXXXXXXX-540-380.png',
      title: 'DEMO版本更新',
      content: '图片尺寸是540x380;',
    },
    {
      image:
        'https://img.alicdn.com/tfs/TB1KzrwRFXXXXasXXXXXXXXXXXX-540-380.png',
      title: 'DEMO版本更新',
      content: '图片尺寸是540x380;',
    },
  ],
  image: 'image示例值',
  title: 'title示例值',
  content: 'content示例值',
  buttonLabels: ['了解更多', '知道了'],
  success: (res) => {
    const { buttonIndex } = res;
```

`success`返回对象示例：

```json
{ "buttonIndex": "1" }
```