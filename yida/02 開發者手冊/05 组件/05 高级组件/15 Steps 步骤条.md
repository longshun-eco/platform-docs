---
title: "Steps 步骤条"
source: "https://docs.aliwork.com/docs/developer/components/advanced/steps"
category: "開發者手冊 / 组件 / 高级组件"
updated: 
tags:
  - yida
  - 開發者手冊
---
引导用户按照流程完成任务的导航条。

## 何时使用

-   当任务复杂或者存在先后关系时，将其分解成一系列步骤，从而简化任务。

## 组件示例

## 组件属性

| 属性 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
|
animation

 | 是否开启动效 | boolean | true |
|

contentRender

 | 内容自定义渲染 | (item: StepsDataSource, index: number)=> ReactNode |

\-

 |
|

current

 | 当前步骤 | number | 1 |
|

dataSource

 | 步骤数据 | [StepsDataSource\[\]](/docs/developer/components/interface#stepsdatasource) |
```json
[
{
  "title": "step1",
  "content": "Open the refrigerator door"
},
{
  "title": "step2",
  "content": "Put the elephant in the refrigerator"
},
{
  "title": "step3",
  "content": "Close the refrigerator door"
}
]
```
 |
|

direction

 | 步骤条展示方向 | 'horizontal' | 'vertical' | 'horizontal' |
|

labelPlacement

 | 内容排列方式 | 'horizontal' | 'vertical' | 'vertical' |
|

onClick

 | 点击步骤时触发事件 | (index: number) => void |

\-

 |
|

readOnly

 | 是否只读模式 | boolean | false |
|

shape

 | 步骤条展示类型 | 'circle' | 'arrow' | 'dot' | 'circle' |
