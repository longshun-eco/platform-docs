---
title: "InstanceDataKeywordItem"
source: "https://help.h3yun.com/contents/696/780.html"
category: "開發者手冊 / 后端API / H3.Workflow.Instance / InstanceDataKeywordItem"
updated: 2025-12-22
tags:
  - h3yun
  - 開發者手冊
---
类名 : InstanceDataKeywordItem
说明 : 关键值数据项。这是一类特殊的数据项，他是为了统一以InstanceData\["..."\].Value的访问方式而设计的。 属性 : 

| 名称 | 说明 |
| --- | --- |
| Value | 值，只能读取不能设置 |
| Visible | 数据项的可见性，这里统一都是可见 |
| Editable | 是否可编辑，只读，不可写 |
| TrackVisible | 数据变更日志是否可见，不可见 |
| Required | 数据是否必填，全部是否 |
| Printable | 数据项是否可打印，默认都是可以 |
| RealType | .Net类型 |
| BizDataType | 逻辑类型 |
| DisplayName | 获取显示名称 |



构造方法名称 : #ctor(H3.Workflow.Instance.InstanceData,H3.Data.BizDataType,System.Object)

| 参数 | 说明 |
| --- | --- |
| "instanceData" | 流程实例数据集 |
| "bizDataType" | 逻辑类型 |
| "value" | 值 |
| 返回值 |  |
| |  |