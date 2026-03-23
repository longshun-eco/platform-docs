---
title: "API 卡片数据的填写说明"
source: "https://open.dingtalk.com/document/development/instructions-for-filling-in-api-card-data"
category: "服务端API / 互动卡片"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-instructions-for-filling-in-api-card-data_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-instructions-for-filling-in-api-card-data_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-23本文介绍了创建卡片、创建并投放卡片、更新卡片 三个接口中卡片数据（包括公共数据和私有数据）的填写说明。

## **前言**

[创建卡片](/document/development/interface-for-creating-a-card-instance)、[创建并投放卡片](/document/development/create-and-deliver-cards)、[更新卡片](/document/development/interactive-card-update-interface)三个接口都是使用 `Map<String, String>` 来传递卡片数据的，其中 Key 为参数名、Value 为参数值。本文介绍了当参数值的类型为 String 和非 String 时填写说明。

## **卡片 String 类型参数的填写说明**

对于 String 类型的参数，可以直接将参数名和参数值填写到卡片数据中即可，如：

```json
{
  "outTrackId": "testId"
  "cardData": {
    "cardParamMap" {
        "strParam1": "str1",            // 公共 String 类型属性
        "strParam2": "str2"             // 公共 String 类型属性
    }
  },
  "privateData": {
    "myUserId": {
      "cardParamMap" {
          "privateStrParam3": "str3",   // 私有 String 类型属性
          "privateStrParam4": "str4"    // 私有 String 类型属性
      }
    }
  },

  ...
}
```

## **卡片非 String 类型参数的填写说明**

对于非 String 类型，需要做一些特殊处理。

* 基本类型，如 Number、Boolean，填写范例如下：

  ```json
  {
    "outTrackId": "testId"
    "cardData": {
      "cardParamMap" {
        "intParam": "1",            // 公共整数类型属性
        "trueParam": "true",        // 公共布尔类型属性，对应 TRUE
      }
    },
    "privateData": {
      "myUserId": {
        "cardParamMap" {
            "floatParam": "1.23",    // 私有浮点类型属性
            "falseparam": "false"    // 私有布尔类型属性，对应 FALSE
        }
      }
    },

    ...
  }
  ```
* 对象类型，需要将对象转成 JSONString，填写范例如下：

  ```json
  {
    "outTrackId": "testId"
    "cardData": {
      "cardParamMap" {
          "objParam": "{\"str\":\"stringValue\",\"innerObj\":{\"innerStr\":\"stringValue\",\"innerInt\":123,\"innerBool\":true},\"bool\":true,\"float\":1.23,\"int\":123}"
      }
    },
    ...
  }
  ```

  **说明**

  objParam 对应的值解析成 JSON 对象后如下：

  ```json
  {
    "strParam": "stringValue",         // 对象的字符串类型属性
    "boolParam": true,                 // 对象的布尔类型属性
    "floatParam": 1.2,                 // 对象的浮点类型属性
    "intParam": 123,                   // 对象的整数类型属性
    "innerObjParam": {                 // 对象的对象类型属性
      "innerStrParam": "stringValue",  // 内部对象的字符串类型属性
      "innerIntParam": 123,            // 内部对象的整数类型属性
      "innerBoolParam": true           // 内部对象的布尔类型属性
    },
  }
  ```
* 数组类型，需要将数组转成 JSONString，填写范例如下：

  ```json
  {
    "outTrackId": "testId"
    "cardData": {
      "cardParamMap" {
        "intArrParam": "[1,2,3]",
        "boolArrParam": "[true,false]",
        "objArrParam": "[{\"param1\":\"val1\"},{\"param2\":\"val2\"}]"
      }
    },
    "privateData": {
      "myUserId": {
        "cardParamMap" {
          "floatArrParam": "[1.1,2.2,3.3]",
          "stringArrParam": "[\"str1\",\"str2\"]"
        }
      }
    },

    ...
  }
  ```

  **说明**

  `intArrParam`、`boolArrParam`、`objArrParam`、`floatArrParam` 和 `stringArrParam` 参数对应的值解析成 JSON 对象后为：

  ```json
  {
    "intArrParam": [1, 2, 3],
    "boolArrParam": [true, false],
    "objArrParam": [
      {
        "param1": "val1"
      },
      {
        "param2": "val2"
      }
    ],
    "floatArrParam": [1.1, 2.2, 3.3],
    "stringArrParam": ["str1", "str2"]
  }
  ```