---
title: "客户群查询DSL语法说明"
source: "https://open.dingtalk.com/document/development/dsl-syntax-description"
category: "服务端API / 客户管理（官方CRM） / 控件格式"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-dsl-syntax-description_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-dsl-syntax-description_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-23本文档介绍客户群和客户群组查询DSL语法的使用。

## DSL语法的介绍

DSL语法是用在获取客户群列表和客户群组列表时，按照某些条件查询并且按照指定方式排序，获取需要的客户群或者客户群组。由以下两部分组成：

* 过滤字段列表
* 排序字段列表

## DSL语法的格式

DSL语法包括过滤字段列表、排序列表。

```
{
    "queryGroupList":[
        {
            "logicType":"AND",
            "queryObjectList":[
                {
                    "filterType":"过滤类型",
                    "fieldId":"过滤字段名"
                    "value":"过滤字段的值",
                },
                {
                    "filterType":"过滤类型",
                    "fieldId":"过滤字段名"
                    "value":"过滤字段的值",
                }
            ]
        }
    ],
    "orderByFields":[
        {
            "orderByFieldId":"排序字段名",
```

### 过滤字段列表

字段是queryGroupList。

| 字段 | 说明 |
| --- | --- |
| logicType | 固定值AND。 |
| queryObjectList | 过滤字段条件。 |
| filterType | 过滤类型，支持以下值：   * **SEARCH**：模糊搜索 * **EQ**：值相等 * **LT**：小于 * **GT**：大于 * **BETWEEN**：介于，使用该过滤类型时，value值格式为数组。 |
| value | 过滤字段的值。 |
| fieldId | 过滤字段名，支持以下值：   * **name**：群名称 * **ownerUserId**：群主userId * **gmtCreate**：创建时间 |

### 排序条件列表

字段是orderByFields。

| 字段 | 说明 |
| --- | --- |
| orderByFieldId | 排序字段名。  **重要**  只支持gmtCreate（创建时间）。 |
| orderByDirection | 排序方式，支持以下值：   * **ASC**：升序 * **DESC**：降序 |

## 使用示例

### 示例代码

**模糊搜索群名称包含"测试客户群"且创建时间大于1640002249001（时间戳，单位毫秒）的客户群数据，并按照创建时间升序排序JavaScript。**

```
{
    "queryGroupList":[
        {
            "logicType":"AND",
            "queryObjectList":[
                {
                    "filterType":"SEARCH",
                    "value":"测试客户群",
                    "fieldId":"name"
                },
                {
                    "filterType":"LT",
                    "value":"1640002249001",
                    "fieldId":"gmtCreate"
                }
            ]
        }
    ],
    "orderByFields":[
        {
            "orderByFieldId":"gmtCreate",
```

### 示例代码

**搜索群主userId为manaxxxx的客户群数据，并按照创建时间降序排序。**

```json
{
    "queryGroupList":[
        {
            "logicType":"AND",
            "queryObjectList":[
                {
                    "filterType":"EQ",
                    "value":"XX",
                    "fieldId":"ownerUserId"
                }
            ]
        }
    ],
    "orderByFields":[
        {
            "orderByFieldId":"gmtCreate",
            "orderByDirection":"DESC"
        }
    ]
}
```