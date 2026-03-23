---
title: "getSystemInfoSync"
source: "https://open.dingtalk.com/document/development/jsapi-get-system-info-sync"
category: "客户端JSAPI / 基础API / 设备 / 系统信息"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-get-system-info-sync_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-get-system-info-sync_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用dd.getSystemInfoSync获取手机系统信息的同步接口。

## 支持说明

| 应用能力 | Android | iOS | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 6.0.0 | 6.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10141) |

## 支持应用类型

| 应用类型 | 是否支持调用 |
| --- | --- |
| 企业内部应用 | 是 |
| 第三方企业应用 | 是 |
| 第三方个人应用 | 是 |

## 鉴权规则

无需鉴权即可直接调用

## **参数说明**

继承[通用输入对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性描述：

| 名称 | 类型 | 示例值 | 描述 |
| --- | --- | --- | --- |
| model | String | iPhone13,2 | 手机型号。 |
| app | String | DingTalk | 应用名。 |
| brand | String | iPhone | 手机品牌。 |
| pixelRatio | Number | 3 | 设备像素比。 |
| windowWidth | Number | 390 | 窗口宽度。 |
| windowHeight | Number | 753 | 窗口高度。 |
| language | String | zh\_CN | 钉钉设置的语言。 |
| version | String | 7.0.1 | 钉钉版本号。 |
| storage | String | 119.09 GB | 设备磁盘容量。 |
| currentBattery | String | 84% | 当前电量百分比。 |
| system | String | 16.1.1 | 系统版本。 |
| paltform | String | iOS | 系统名。 |
| screenWidth | Number | 390 | 屏幕宽度。 |
| screenHeight | Number | 844 | 屏幕高度。 |
| fontSizeSetting | Number | 17 | 用户设置字体大小。 |
| isIphoneXSeries | Boolean | true | 是否是iphone手机。 |
| lowPowerMode | Boolean | false | 是否是低电量模式。 |
| orientation | Number | 0 | * 0：竖屏 * 1： 横屏 |
| titleBarHeight | Number | 44 | 标题栏高度。 |
| statusBarHeight | Number | 47 | 状态栏高度。 |

## **示例****代码**

### 默认出入参

```javascript
const res = dd.getSystemInfoSync();
const {
  app,
  brand,
  model,
  system,
  storage,
  version,
  language,
  paltform,
  pixelRatio,
  orientation,
  screenWidth,
  windowWidth,
  lowPowerMode,
  screenHeight,
  windowHeight,
  currentBattery,
  titleBarHeight,
  fontSizeSetting,
  isIphoneXSeries,
```

返回对象示例：

```
{
  "app": "DingTalk",
  "brand": "iPhone",
  "model": "iPhone13,2",
  "system": "16.1.1",
  "storage": "119.09 GB",
  "version": "7.0.1",
  "language": "zh_CN",
  "paltform": "iOS",
  "pixelRatio": 3,
  "orientation": 0,
  "screenWidth": 390,
  "windowWidth": 390,
  "lowPowerMode": false,
  "screenHeight": 844,
  "windowHeight": 753,
  "currentBattery": "84%",
  "titleBarHeight": 44,
  "fontSizeSetting": 17,
  "isIphoneXSeries": true,
  "statusBarHeight": 47
```