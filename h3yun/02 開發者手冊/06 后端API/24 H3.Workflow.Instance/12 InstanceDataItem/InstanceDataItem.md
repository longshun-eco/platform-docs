---
title: "InstanceDataItem"
source: "https://help.h3yun.com/contents/694/775.html"
category: "開發者手冊 / 后端API / H3.Workflow.Instance / InstanceDataItem"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
类名 : InstanceDataItem
说明 : 流程实例数据项对象 属性 : 

| 名称 | 说明 |
| --- | --- |
| InstanceData | 流程实例数据集 |
| ActivityTemplate | 获取当前活动节点模板 |
| PropertySchema | 数据项定义 |
| RealType | 数据项的类型 |
| BizDataType | 数据项的逻辑类型 |
| Value | 数据项的值 |
| Visible | 在当前活动下是否可见 |
| Editable | 在当前活动下是否可写 |
| TrackVisible | 在当前活动下是否可以查看痕迹 |
| Required | 在当前活动下是否必输 |
| Printable | 在当前活动下是否可打印 |
| DisplayName | 获取显示名称 |



构造方法名称 : #ctor(H3.Workflow.Instance.InstanceData,H3.DataModel.PropertySchema)

| 参数 | 说明 |
| --- | --- |
| "instanceData" | 流程数据集 |
| "propertySchema" | 字段属性 |
| 返回值 |  |
| |  |