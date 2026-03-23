---
title: "关于购买企业应用开发增购包获取增值OpenAPI权益的说明"
source: "https://open.dingtalk.com/document/development/notes-on-purchasing-enterprise-application-development-package-to-obtain-exclusive"
category: "服务端API / 平台公告"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-notes-on-purchasing-enterprise-application-development-package-to-obtain-exclusive_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-notes-on-purchasing-enterprise-application-development-package-to-obtain-exclusive_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-01-22钉钉增值 OpenAPI 将提供更丰富的能力，支持不同场景下的企业内部应用开发，建议开发者更合理、有效地使用 OpenAPI，打造更健康的钉钉开放生态。

## **钉钉**增值 OpenAPI **列表**

**说明**

钉钉可能会因法律法规或政策调整、执行监管指令所需，或者为维护钉钉服务安全性等，对以下接口的范围或具体功能进行增加、修改或删除。实际对客户开放的接口以钉钉开放平台届时公示的内容为准。

|  |  |  |
| --- | --- | --- |
| **OpenAPI名称** | **OpenAPI详情** | **是否已上线** |
| [添加待入职员工](/document/development/add-employees-to-be-hired-supports-system-and-custom-fields) | 在企业自有通讯录系统内，添加待入职员工时，调用本接口在钉钉智能人事应用内同步添加待入职员工 | 是 |
| [配置考勤排班附加信息](/document/development/synchronization-scheduling-information) | 企业考勤排班信息较多，手动配置排班的打卡位置、打卡WiFi信息比较繁琐，可调用本接口，更新排班的附加信息 | 是 |
| [查询指定用户的封账规则](/document/development/encapsulate-account-sealing-and-unsealing-rules) | 开启封账后，封账范围内的考勤结果将封存不允许修改。包含以下操作：请假，外出，出差，加班，补卡申请；员工排班，修改考勤结果等，调用本接口根据企业员工userId列表，获取员工的封账规则信息 | 是 |
| [发送DING消息](/document/development/robot-sends-nail-message) | 企业在紧急场景下，可调用本接口给指定员工发起应用内DING消息、短信DING消息和电话DING消息提醒 | 是 |
| [撤回已经发送的DING消息](/document/development/robot-withdraws-pin-message) | 已发送的DING消息，支持调用本接口进行撤回 | 是 |
| [上传打卡记录](/document/development/upload-punch-records) | 企业使用三方打卡设备或门禁系统刷卡，调用本接口，可将三方打卡或刷卡记录上传到钉钉考勤，作为员工的考勤打卡信息 | 是 |

## 增值 OpenAPI **的使用条件**

增值 OpenAPI，需要企业升级钉钉专业版、[钉钉专属版](https://partner.dingtalk.com/opportunity_web.html?channel=openpf_web_devdoc_trial&templateId=092b3722b3fd4dd08fb641a194a90691#/consultingService)或者购买企业应用开发增购包后才能申请使用。

## 增值 OpenAPI **的申请步骤**

申请入口：「[**开发者后台**](https://open-dev.dingtalk.com/)**> 应用开发 > 钉钉应用 > 新建应用或已有应用 > 点击应用 > 权限管理 > 只看专业版专享接口」**

* 专业/专属版客户，在「权限申请」处，点击即可申请对应接口权限。

  ![[development-notes-on-purchasing-enterprise-application-development-package-to-obtain-exclusive_p973801.png]]
* 标准版客户，在「权限申请」处，点击跳转专业版的购买页面，升级专业版或[升级专属版](https://partner.dingtalk.com/opportunity_web.html?channel=openpf_web_devdoc_trial&templateId=092b3722b3fd4dd08fb641a194a90691#/consultingService)后再申请接口权限。

  ![[development-notes-on-purchasing-enterprise-application-development-package-to-obtain-exclusive_p973796.png]]

## **常见问题**

1. 增值 OpenAPI 的计费规则是什么？

   答：标准版钉钉客户无法使用专业版和专属版的增值 OpenAPI，需要先升级专业版、[升级专属版](https://partner.dingtalk.com/opportunity_web.html?channel=openpf_web_devdoc_trial&templateId=092b3722b3fd4dd08fb641a194a90691#/consultingService)或购买应用开发增购包后才能调用这些接口，专业版和专属版的增值 OpenAPI 接口（除发DING接口）使用时消耗专业版和专属版的OpenAPI额度，发DING接口消耗OpenAPI发DING额度。
2. 标准版客户能看到这些增值 OpenAPI 接口吗？

   答：2023 年 8月 1 日起，开发者可在开放平台开发者文档及[开发者后台](https://open-dev.dingtalk.com/)中看到本次上线的增值 OpenAPI。