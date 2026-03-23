---
title: "关于新增专业版和专属版钉钉专享OpenAPI的说明"
source: "https://open.dingtalk.com/document/development/description-of-the-new-professional-and-exclusive-editions-of-nail-exclusive-openapi"
category: "服务端API / 平台公告"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-description-of-the-new-professional-and-exclusive-editions-of-nail-exclusive-openapi_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-description-of-the-new-professional-and-exclusive-editions-of-nail-exclusive-openapi_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-01-22为满足广大开发者在个性化应用开发方面的需求，钉钉新增了一批面向专业版和[专属版](https://partner.dingtalk.com/opportunity_web.html?channel=openpf_web_devdoc_trial&templateId=092b3722b3fd4dd08fb641a194a90691#/consultingService)客户的专享OpenAPI。这些专享OpenAPI将提供更丰富的能力，支持不同场景下的企业内部应用开发，建议开发者更合理、有效地使用OpenAPI，打造更健康的钉钉开放生态。

## 一、本次新增的专业版和专属版钉钉的专享OpenAPI列表

**说明**

钉钉可能会因法律法规或政策调整、执行监管指令所需，或者为维护钉钉服务安全性等，对以下接口的范围或具体功能进行增加、修改或删除。实际对客户开放的接口以钉钉开放平台届时公示的内容为准。

|  |  |  |
| --- | --- | --- |
| **OpenAPI名称** | **OpenAPI详情** | **是否已上线** |
| [智能人事添加待入职员工信息（支持花名册数据和分组明细更新）](/document/orgapp/add-employees-to-be-hired-supports-system-and-custom-fields) | 在企业自有通讯录系统内，添加待入职员工时，调用本接口在钉钉智能人事应用内同步添加待入职员工 | 是 |
| [配置考勤排班附加信息，例如打卡位置，打卡WiFi等](/document/orgapp/synchronization-scheduling-information) | 企业考勤排班信息较多，手动配置排班的打卡位置、打卡WiFi信息比较繁琐，可调用本接口，更新排班的附加信息 | 是 |
| [查询指定用户的封账规则](/document/orgapp/encapsulate-account-sealing-and-unsealing-rules) | 开启封账后，封账范围内的考勤结果将封存不允许修改。包含以下操作：请假，外出，出差，加班，补卡申请；员工排班，修改考勤结果等，调用本接口根据企业员工userId列表，获取员工的封账规则信息 | 是 |
| [发送DING消息](/document/orgapp/robot-sends-nail-message) | 企业在紧急场景下，可调用本接口给指定员工发起应用内DING消息、短信DING消息和电话DING消息提醒 | 是 |
| [撤回已经发送的DING消息](/document/orgapp/robot-withdraws-pin-message) | 已发送的DING消息，支持调用本接口进行撤回 | 是 |
| [上传打卡记录](/document/orgapp/upload-punch-records) | 企业使用三方打卡设备或门禁系统刷卡，调用本接口，可将三方打卡或刷卡记录上传到钉钉考勤，作为员工的考勤打卡信息 | 是 |

## 二、专享OpenAPI上线时间

2023年08月01日起将陆续上线。

## **三、**专享OpenAPI**的使用条件**

上述专享 OpenAPI，标准版钉钉需要升级专业版或[升级专属版](https://partner.dingtalk.com/opportunity_web.html?channel=openpf_web_devdoc_trial&templateId=092b3722b3fd4dd08fb641a194a90691#/consultingService)后才可申请使用；部分客户在 8 月 1 日上线前已经参与公测，获得了这些 OpenAPI的调用权限，请按以下规则调用：

|  |  |  |
| --- | --- | --- |
| **客户类型** | **是否参与公测** | **是否受影响** |
| 专业版/专属版客户 | 已参与公测 | 不受影响，继续正常调用 |
| 未参与公测 | 申请接口使用权限后，可调用 |
| 标准版客户 | 已参与公测 | 不可调用，需升级至专业/专属版后，申请接口调用权限后才能恢复调用；权限申请步骤请参考本文档第四部分的说明 |
| 未参与公测 | 不可调用，需升级至专业/专属版后，申请接口调用权限后才能调用；权限申请步骤请参考本文档第四部分的说明 |

## **四、专享**OpenAPI **权限申请步骤**

申请入口：「[**开发者后台**](https://open-dev.dingtalk.com/) **> 应用开发 > 钉钉应用 > 新建应用或已有应用 > 点击应用 > 权限管理 > 只看专业版专享接口」**

* 专业/专属版客户，在「权限申请」处，点击即可申请对应接口权限

![[development-description-of-the-new-professional-and-exclusive-editions-of-nail-exclusive-openapi_p690996.png]]

* 标准版客户，在「权限申请」处，点击跳转专业版的购买页面，升级专业版或[升级专属版](https://partner.dingtalk.com/opportunity_web.html?channel=openpf_web_devdoc_trial&templateId=092b3722b3fd4dd08fb641a194a90691#/consultingService)后再申请接口权限。

![[development-description-of-the-new-professional-and-exclusive-editions-of-nail-exclusive-openapi_p690995.png]]

## **五、常见问题**

1. 专享OpenAPI的计费规则是什么？

   答：标准版钉钉客户无法使用专业版和专属版的专享OpenAPI，需要先升级专业版或[升级专属版](https://partner.dingtalk.com/opportunity_web.html?channel=openpf_web_devdoc_trial&templateId=092b3722b3fd4dd08fb641a194a90691#/consultingService)后才能调用这些接口，专业版和专属版的专享OpenAPI（除发DING接口）使用时消耗专业版和专属版的OpenAPI额度，发DING接口消耗OpenAPI发DING额度。
2. 标准版客户能看到这些专享OpenAPI吗？

   答：2023年 08月 01日起，开发者可在开放平台开发者文档及[开发者后台](https://open-dev.dingtalk.com/)中看到本次上线的专享OpenAPI。