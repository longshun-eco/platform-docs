---
title: "CASCADEDATEINTERVALV2"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/dh7m8n/blbqwhbcsa44h4tb"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 时间函数"
updated: 
tags:
  - yida
  - 用戶手冊
---
CASCADEDATEINTERVALV2函数用于计算日期区间选择框组件中的，开始和结束日期的差值。

## 支持产品场景

CASCADEDATEINTERVALV2函数支持在宜搭的以下场景中使用。

-   表单（主表字段）
-   表单（业务关联规则）
-   表单（校验）
-   流程设计（校验规则）
-   流程设计（关联操作）
-   集成自动化
-   流程-节点
-   连接器

## 格式

```
CASCADEDATEINTERVALV2(日期组件,type,Offset)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| timestamp | 是 | 日期区间组件。 |
| type | 是 | 差值单位，取值：
-   d：天
-   **h**：小时
-   **s**：秒

 |
| Offset | 是 | 以单位长度作为偏移量，可以为正数或者负数。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 数字 | 得出日期区间的相隔天数。 |

## 使用示例

-   示例一：

日期区间，选择了日期格式为`年-月-日`，开始时间选择为`2023-12-01`，结束时间选择为`2023-12-31`。

![[yida_support-wtwabe-cnzrgo-gvtpe4-dh7m8n-blbqwhbcsa44h4tb_1703233218096-e38569fa-0ee2-48c5-8e9e-fda496ff135e.png]]

则公式返回的结果为 31。

![[yida_support-wtwabe-cnzrgo-gvtpe4-dh7m8n-blbqwhbcsa44h4tb_1703233178082-f58b946a-d37b-47e3-a812-5e7172fe1e92.png]]

-   示例二：

日期区间，选择了日期格式为`年-月-日 时:分:秒`，开始时间选择为`2023-12-01 09:30:00`，结束时间选择为`2023-12-01 18:00:00`。

![[yida_support-wtwabe-cnzrgo-gvtpe4-dh7m8n-blbqwhbcsa44h4tb_1703233521341-4939acff-101c-4663-94e8-614a7fa3312e.png]]

则公式返回的结果为 8.5。

![[yida_support-wtwabe-cnzrgo-gvtpe4-dh7m8n-blbqwhbcsa44h4tb_1703233918348-221cc185-2699-4296-b1bb-a54359f2d1b0.png]]

## 体验

计算日期区间选择框组件中的，开始和结束日期的相隔天数，[点击体验效果](https://www.aliwork.com/o/wesxsde?ddtab=true)。
