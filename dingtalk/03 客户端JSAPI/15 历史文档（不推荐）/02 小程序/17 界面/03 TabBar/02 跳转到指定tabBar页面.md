---
title: "跳转到指定tabBar页面"
source: "https://open.dingtalk.com/document/development/dd-switchtab"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 界面 / TabBar"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-dd-switchtab_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-dd-switchtab_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17调用**dd.switchTab**跳转到指定 tabBar 页面，并关闭其他所有非 tabBar 页面。

## 扫码体验

![[development-dd-switchtab_p172077.png]]

## **示例代码**

```
// app.json
{
  "tabBar": {
    "items": [{
      "pagePath": "home",
      "name": "首页"
    },{
      "pagePath": "user",
      "name": "用户"
    }]
  }
}
```

```
dd.switchTab({
  url: '/home'
})
```

## **入参**

| 参数 | 类型 | 是否必填 | 描述 |
| --- | --- | --- | --- |
| url | String | 是 | 跳转的 tabBar 页面的路径（需在 app.json 的 tabBar 字段定义的页面）。  **重要**  路径后不能带参数。 |
| success | Function | 否 | 调用成功的回调函数。 |
| fail | Function | 否 | 调用失败的回调函数。 |
| complete | Function | 否 | 调用结束的回调函数（调用成功、失败都会执行）。 |