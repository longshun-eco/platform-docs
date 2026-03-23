---
title: "PTS服务使用指南"
source: "https://open.dingtalk.com/document/services/stress-test"
category: "平台服务 / 运营规范（废弃） / 规范&协议汇总（废弃） / 技术规范 / 稳定性认证审核相关规范"
updated: 
tags:
  - dingtalk
  - 平台服务
---
![[services-stress-test_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[services-stress-test_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-23

## **一、注意事项**

**如果开发者开发的是第三方企业应用，提交上架稳定性审核报告使用，请注意以下事项：**

**（1）限流要求使用PTS进行演练，参考**[稳定性认证标准-限流标准](/document/operation-specification/stabilistandards#topic-2625301)[稳定性认证标准-限流标准标准](/document/isvapp/stabilistandards)**。**

**（2）压测过程建议使用PTS，也可以使用其他压测工具进行压测。压测参考**[稳定性认证标准-稳定性压测标准](/document/isvapp/stabilistandards)**。**

**（3）开发者后台压测后，无需进行绑定报告。稳定性审核时仅以提交的审核报告为准。**

## 二、获取阿里云账号

**若目前已有阿里云账号，登录**[钉钉开发者后台](http://open-dev.dingtalk.com)-应用开发-钉钉云，点击登录控制台。

**若无阿里云账号，需先获取账号，请参考以下步骤：**

步骤一，登录[开发者后台](https://open-dev.dingtalk.com)，选择应用开发- 钉钉云 - 入驻钉钉云，进入钉钉云页面

![[services-stress-test_p163706.png]]

步骤二，选择钉钉云基础版，完成实名认证

![[services-stress-test_p163707.png]]

步骤三，进入账号申请状态

![[services-stress-test_p163708.png]]

步骤四，等待几分钟，刷新页面会获取到一个子账号

![[services-stress-test_p163709.png]]

##

## 三、开通PTS

登录管理控制台-云产品开通-性能测试PTS，如下图所示：

![[services-stress-test_p163710.png]]

点击基础信息，切换到账号信息页面

![[services-stress-test_p163711.png]]

点击登录控制台

![[services-stress-test_p163712.png]]

登录进入阿里云，从产品列表里找到PTS或者搜索PTS，如下图所示：

![[services-stress-test_p163713.png]]

打开性能测试PTS页面，点击购买套餐。注意，以下是PTS新版页面，旧版请点击‘跳转到PTS铂金版”，并点击链接购买。

![[services-stress-test_p163714.png]]

购买成功后，此时我们可以看到自己的剩余VUM，这时候就可以压测了。

![[services-stress-test_p163715.png]]

## 四、压测

在概览页单击

**快速压测**

，或者左侧菜单栏单击**创建压测**，配置相关参数

![[services-stress-test_p163716.png]]

![[services-stress-test_p163717.png]]

点击右上角的保存，开始压测，会生成压测报告：

![[services-stress-test_p163718.png]]

压测快速入门，详细内容也可参考[阿里云PTS压测文档](https://help.aliyun.com/document_detail/70290.html?spm=a2c4g.11186623.6.552.1e4d5e7dCh4JUS)。