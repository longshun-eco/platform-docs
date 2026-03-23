---
title: "enableLeaveConfirm"
source: "https://open.dingtalk.com/document/development/jsapi-enable-leave-confirm"
category: "客户端JSAPI / 基础API / 界面 / TabBar"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-enable-leave-confirm_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-enable-leave-confirm_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

调用dd.enableLeaveConfirm对当前页面进行离开二次确认。

当前页面指调用dd.enableLeaveConfirm及dd.disableLeaveConfirm时小程序栈顶页面，与该 JSAPI 在哪个 page 实例下调用无关。

## 支持说明

| 应用能力 | Android | iOS | Harmony | Mac | Windows | 预览效果 |
| --- | --- | --- | --- | --- | --- | --- |
| 网页应用（原H5微应用） | 不支持 | 不支持 | 不支持 | 不支持 | 不支持 | - |
| 小程序 | 6.0.0 | 6.0.0 | 7.0.0 | 7.0.10 | 7.0.10 | [去预览](https://open.dingtalk.com/tools/explorer/jsapi?id=10072) |

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
| effect | Array<String> | 是 | ['back', 'close'] | 指定生效场景：   * back: 点击返回 * close：点击关闭 |
| info | Object | 是 |  |  |

## **返回结果**

继承[通用输出对象](https://open.dingtalk.com/document/direction/jsapi-standard-input-output-object)，扩展属性为空

## **示例****代码**

### 默认出入参

```
dd.enableLeaveConfirm({
  info: { title: '确认要离开吗', content: '离开后数据将不会被保存' },
  effect: ['back', 'close'],
  success: () => {},
  fail: () => {},
  complete: () => {},
});
```