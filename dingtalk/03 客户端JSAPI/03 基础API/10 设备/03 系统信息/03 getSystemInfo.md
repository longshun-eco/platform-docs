---
title: "getSystemInfo"
source: "https://open.dingtalk.com/document/development/jsapi-get-system-info"
category: "客户端JSAPI / 基础API / 设备 / 系统信息"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-get-system-info_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-get-system-info_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-10-21

调用getSystemInfo，获取系统信息。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 6.0.0 | 6.0.0 | 7.0.0 | 不支持 | 不支持 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10140) |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 7.0.0 | 7.0.0 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10140) |

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
| model | String | iPhone13,2 | 手机型号。  桌面端不支持该字段。 |
| app | String | DingTalk | 应用名。 |
| brand | String | iPhone | 手机品牌。  桌面端不支持该字段。 |
| pixelRatio | Number | 3 | 设备像素比。 |
| windowWidth | Number | 390 | 窗口宽度。 |
| windowHeight | Number | 753 | 窗口高度。 |
| language | String | zh\_CN | 钉钉设置的语言。  仅小程序应用返回。 |
| version | String | 15 | 系统版本号。  小程序全局 API 调用时为钉钉版本号 |
| storage | String | 119.09 GB | 设备磁盘容量。 |
| currentBattery | String | 84% | 当前电量百分比。  桌面端不支持该字段。 |
| system | String | 16.1.1 | 系统版本。 |
| platform | String | iOS | 系统名。 |
| screenWidth | Number | 390 | 屏幕宽度。 |
| screenHeight | Number | 844 | 屏幕高度。 |
| fontSizeSetting | Number | 17 | 用户设置字体大小。 |
| orientation | Number | 0 | * 0：竖屏 * 1： 横屏   桌面端不支持该字段。 |
| titleBarHeight | Number | 44 | 标题栏高度。  桌面端不支持该字段。 |
| statusBarHeight | Number | 47 | 状态栏高度。  桌面端不支持该字段。 |

## **示例****代码**

### 默认出入参

```javascript
dd.getSystemInfo({
  success: (res) => {
    const {
      app,
      brand,
      model,
      system,
      storage,
      version,
      language,
      platform,
      pixelRatio,
      orientation,
      screenWidth,
      windowWidth,
      screenHeight,
      windowHeight,
      currentBattery,
      titleBarHeight,
      fontSizeSetting,
      statusBarHeight,
```

`success`返回对象示例：

```json
{
  "app": "DingTalk",
  "brand": "iPhone",
  "model": "iPhone13,2",
  "system": "16.1.1",
  "storage": "119.09 GB",
  "version": "15",
  "language": "zh_CN",
  "platform": "iOS",
  "pixelRatio": 3,
  "orientation": 0,
  "screenWidth": 390,
  "windowWidth": 390,
  "screenHeight": 844,
  "windowHeight": 753,
  "currentBattery": "84%",
  "titleBarHeight": 44,
  "fontSizeSetting": 17,
  "statusBarHeight": 47
}
```