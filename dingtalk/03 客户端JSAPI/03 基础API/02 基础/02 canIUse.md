---
title: "canIUse"
source: "https://open.dingtalk.com/document/development/jsapi-can-i-use"
category: "客户端JSAPI / 基础API / 基础"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-can-i-use_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-can-i-use_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

使用canIUse接口，判断小程序的 API、入参或返回值、组件、属性等在当前钉钉版本是否支持。

如果想判断 API 是否可用，入参需要如 ：

${API}.${type}.${param}.${option}：

* ${API} 表示 API 的名称，不包括 my. 的名称。例如：想判断 my.getFileInfo，只需传入 getFileInfo 即可。
* ${type} 表示 API 的调用方式，有效值为 object/return/callback。
* ${param} 表示参数的某一个属性名。
* ${option} 表示参数属性的具体属性值。

如果想判断组件是否可用，入参需要如 ${component}.${attribute}.${option}：

* ${component} 表示组件名称。
* ${attribute} 表示组件属性名。
* ${option} 表示组件属性值。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10000) |

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
| key | String | 否 | getLocation.object.type | 判断可用：   * 如果想判断 API 是否可用，入参需要如： ${API}.${type}.${param}.${option}。 * 如果想判断组件是否可用，入参需要如： ${component}.${attribute}.${option}。 |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| res | Boolean | true | 是否可用。 |

## **示例****代码**

### 判断接口 getFileInfo 是否可用

```javascript
const res = dd.canIUse(
  `API示例值`,
  `type示例值`,
  `param示例值`,
  `option示例值`,
  `attribute示例值`,
  `component示例值`,
);
const { isSupport } = res;
```

返回对象示例：

```json
{ "isSupport": true }
```

### 判断接口 getLocation 的入参是否包含 type

```javascript
const res = dd.canIUse('getLocation.object.type');
console.log(res);
// res: true
```

返回对象示例：

```
true
```

### 判断接口 getSystemInfo 的 success 回调中是否包含 storage

```javascript
const res = dd.canIUse('getSystemInfo.return.storage');
console.log(res);
// res: true
```

返回对象示例：

```
true
```

### 判断组件 open-avatar（关注生活号）是否可用

```javascript
const res = dd.canIUse('open-avatar');
console.log(res);
// res: true
```

返回对象示例：

```
true
```

### 判断组件 button 是否包含 open-type 属性

```javascript
const res = dd.canIUse('button.open-type');
console.log(res);
// res: true
```

返回对象示例：

```
true
```

### 判断组件 button 的 open-type 属性的值是否可以为 share

```javascript
const res = dd.canIUse('button.open-type.share');
console.log(res);
// res: true
```

返回对象示例：

```
true
```