---
title: "获取企业CorpId"
source: "https://open.dingtalk.com/document/development/obtain-enterprise-corpid"
category: "客户端JSAPI / 历史文档（不推荐） / H5微应用"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-obtain-enterprise-corpid_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-obtain-enterprise-corpid_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17本文介绍了H5微应用获取企业CorpId的流程。

## H5微应用

在应用首页地址和PC端首页地址中使用$CORPID$做为参数占位符，当用户在工作台打开应用时，钉钉容器会将$CORPID$替换为当前访问用户的企业CorpId。

**重要**

只有在钉钉工作台打开应用，才能将$CORPID$动态解析为企业CorpId。

### 示例

如下图所示，登录**开发者后台** > **找到对应应用** > **基础信息** > **开发管理**页面，将应用首页地址和PC端首页地址设置为`https://mm.vaiwan.cn/view/*******?corpId=$CORPID$`。

![[development-obtain-enterprise-corpid_p434182.png]]

用户在工作台打开应用时，会将CorpId替换。例如，企业CorpId是CorpId12345，替换后的地址为`https://mm.vaiwan.cn/view/*******?corpId=ding9f***********`。

在PC端和移动端打开效果相同。以移动端为例，打开效果如下图所示：

![[development-obtain-enterprise-corpid_p434190.png]]