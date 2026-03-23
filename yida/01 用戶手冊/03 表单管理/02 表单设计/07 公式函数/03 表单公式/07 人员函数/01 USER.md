---
title: "USER"
source: "https://docs.aliwork.com/docs/yida_support/wtwabe/cnzrgo/gvtpe4/namr73vcz90gduud/vwncwe"
category: "用戶手冊 / 表单管理 / 表单设计 / 公式函数 / 表单公式 / 人員函數"
updated: 
tags:
  - yida
  - 用戶手冊
---

USER 函数用于获取当前登录人或登录人主管的信息。

## 格式

```
USER(level)
```

## 属性说明

| **属性** | **是否必填** | **说明** |
| --- | --- | --- |
| level | 否 | 数字类型。用于决定当前公式获取的信息是当前登录用户，还是登录人的主管。<br>- 如果不传此参数或传入参数为 `0`，则返回当前登录用户的名称和 userId，<br>- 如果传入此参数切参数不为 `0`，则返回当前登录人的主管信息。传入 `1` 则返回一级主管，传入 `2` 则返回二级主管。 |

## 返回值

| **返回值类型** | **说明** |
| --- | --- |
| 数组 | 返回的人员信息。<br>获取登录人主管信息时，如果不存在该级别主管，则返回空。 |

## 使用示例

如下图所示，使用 `USER()` 函数获取当前登录人和她的主管的信息。

![[yida_support-wtwabe-cnzrgo-gvtpe4-namr73vcz90gduud-vwncwe_1704436531525-b7ba310d-165d-492e-bad9-ec119fc39631.gif]]
