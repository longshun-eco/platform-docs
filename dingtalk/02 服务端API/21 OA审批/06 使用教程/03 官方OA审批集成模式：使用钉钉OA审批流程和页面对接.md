---
title: "官方OA审批集成模式：使用钉钉OA审批流程和页面对接"
source: "https://open.dingtalk.com/document/development/use-the-dingtalk-oa-approval-process-and-page-interface"
category: "服务端API / OA审批 / 使用教程"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-use-the-dingtalk-oa-approval-process-and-page-interface_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-use-the-dingtalk-oa-approval-process-and-page-interface_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-10

## 场景介绍

### **方案说明**

**官方OA审批集成模式：使用钉钉OA审批流程和页面对接。**可在业务系统发起流程，调用钉钉**官方OA审批相关接口**创建钉钉OA审批流程，在钉钉端打开钉钉官方审批详情页处理流程。

### **方案特点&价值**

**更标准**

1、标准化对接，使用钉钉OA流程和页面能力，无缝和钉钉聊天、待办、通知连接，高效审批。

2、复用钉钉官方OA审批流程引擎和表单组件能力，帮助不同业务的审批流程上钉，为用户在钉钉上提供一站式、多端统一的OA 审批产品体验。

## 业务流程

![[development-use-the-dingtalk-oa-approval-process-and-page-interface_p835400.png]]

## **实现效果**

### **支持从业务系统发起流程，调用钉钉OA审批接口创建OA审批流程**

![[development-use-the-dingtalk-oa-approval-process-and-page-interface_p838390.png]]

### 支持从钉钉OA审批列表打开官方OA审批详情页审批

![[development-use-the-dingtalk-oa-approval-process-and-page-interface_p838406.png]]

### **支持从钉钉待办打开官方OA审批详情页审批**

![[development-use-the-dingtalk-oa-approval-process-and-page-interface_p838407.png]]

## 开发流程

![[development-use-the-dingtalk-oa-approval-process-and-page-interface_p835415.png]]

### **接入流程简介**

本文档展示了，创建一个企业内部应用，使用**官方OA审批**相关API，通过创建/更新官方审批模板、发起/撤销/评论审批实例、同意/拒绝/转交审批任务、上传/下载审批附件等API，以及官方OA审批实例/审批任务回调事件，实现业务系统发起，钉钉端内打开官方OA审批详情页进行集成的场景案例。

前提条件：完成[创建应用](/document/dingstart/create-application)的流程。

步骤一：进入应用详情页，获取应用 Client ID 和 Client Secret。

步骤二：申请接口权限，申请“OA审批”相应权限。

步骤三：获取应用访问凭证[获取企业内部应用的accessToken](/document/development/obtain-the-access-token-of-an-internal-app)。调用接口时，通过accessToken鉴权调用者身份。

步骤四：调用OA审批相关API：

1. **创建官方OA审批模板：**管理员可在OA管理后台手动操作创建；或业务系统调用新版服务端API-[创建或更新审批表单模板](/document/development/create-an-approval-form-template)接口，获取模板的唯一编码`processCode`。若没有保存接口返回的模板编码`processCode`，可登录钉钉管理后台查看获取。

![[development-use-the-dingtalk-oa-approval-process-and-page-interface_p838408.png]]

```
{
    "name": "使用钉钉OA审批流程和页面对接",
    "description": "可在业务系统发起流程，调用钉钉官方OA审批相关接口创建钉钉OA审批流程，在钉钉端打开钉钉审批详情页处理流程。",
    "templateConfig": {
        "disableStopProcessButton": false,
        "disableFormEdit": false,
        "disableHomepage": false,
        "hidden": false
    },
    "formComponents": [
        {
            "componentType": "TextField",
            "props": {
                "label": "单行输入框", // 控件标题
                "placeholder": "请输入", // 输入提示
                "componentId": "TextField_17EZKEGSOCTC0", // 控件id，表单内唯一，无业务语义
                "required": false, // 是否必填，默认非必填
                "bizAlias": "staffId" // 控件的业务标识，表单内唯一，与componentId二选一
            }
        },
        {
```

2. 创建审批模板成功后，用户可以在钉钉OA审批管理后台，**查看/编辑**官方OA审批单模板、查看/搜索模板数据、导出/删除模板数据等。
3. **发起官方OA审批实例：**用户可通过OA审批官方应用手动发起审批；或业务系统可根据模板编码`processCode`，调用新版服务端API-[发起审批实例](/document/development/create-an-approval-instance)接口发起审批实例，获取审批实例`instanceId`。

```
{
    "processCode": "PROC-C512D64A-60F6-4F83-B708-xxx",
    "originatorUserId": "manager98xx",
    "deptId": -1,
    "microappAgentId": 348925476,
    "formComponentValues": [
        {
            "name": "日期",
            "value": "2021-08-17"
        },
        {
            "name": "[\"开始时间\",\"结束时间\"]",
            "value": "[\"2019-02-19\",\"2019-02-25\"]"
        },
        {
            "name": "身份证",
            "value": "xxxx"
        },
        {
            "name": "图片",
            "value": "[\"http://url1\",\"http://url2\",\"http://url3\"]"
```

4. 发起审批实例成功后，用户可进入钉钉OA审批中心，查看审批四大列表（待处理、已处理、已发起、我收到的）、搜索审批实例数据、执行审批等操作。
5. **添加审批评论附件：**若需要添加审批评论附件，需先将文件上传至审批钉盘空间，再调用新版服务端API-[添加审批评论](/document/development/add-an-approval-comment-pop)接口。具体使用教程参考：[评论及撤销审批流](/document/development/comment-and-revoke-approval-flow)。

   1. 需先调用新版服务端API-[获取审批钉盘空间信息](/document/development/obtains-the-information-about-approval-nail-disk)接口，获取钉盘空间的上传权限，并获取审批钉盘空间spaceId。
   2. 调用客户端JSAPI-[uploadAttachmentToDingTalk](/document/development/jsapi-upload-attachment-to-ding-talk)接口，获取文件基本信息，本流程示例使用[JSAPI Explorer](https://open.dingtalk.com/tools/explorer/jsapi?id=10318)实现。
   3. 获取审批钉盘空间spaceId后，可根据审批实例`instanceId`，调用新版服务端API-[添加审批评论](/document/development/add-an-approval-comment-pop)接口，实现审批单的添加评论操作。

```json
{
    "commentUserId": "manager98xx",
    "processInstanceId": "DQ7-X2EESQunrozGEe_xxx",
    "text": "测试添加审批评论",
    "file": {
        "attachments": [
            {
                "spaceId": "817447xxx",
                "fileSize": "173404",
                "fileId": "6660150xxx",
                "fileName": "评论附件.jpg",
                "fileType": "jpg"
            }
        ],
        "photos": [
            "https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/9227796361/p352432.png"
        ]
    }
}
```

6. **预览下载审批附件：**若需要预览/下载附件，可调用服务端API-[授权下载审批钉盘文件](/document/development/download-the-approval-nail-file)接口、[授权预览审批附件](/document/development/preview-authorization-attachment-pop)接口，进行审批钉盘文件的授权操作，再调用服务端API-[下载审批附件](/document/development/download-an-approval-attachment)接口，获取文件的链接`downloadUri`实现下载。具体使用教程参考：[审批附件的操作流程](/document/development/new-version-of-attachment-approval-process)。
7. **同意/拒绝审批任务：**审批人可通过钉钉OA审批中心、钉钉待办中心手动操作同意/拒绝审批任务；或业务系统根据审批实例`instanceId`，调用新版服务端API-[获取单个审批实例详情](/document/development/obtains-the-details-of-a-single-approval-instance-pop)接口，获取审批实例详情，获取审批任务各个任务节点信息`taskId`。
8. 根据审批实例`instanceId`和相应的任务节点`taskId`信息，调用新版服务端API-[同意或拒绝审批任务](/document/development/approve-or-reject-the-approval-task)接口，实现审批任务的操作，所有审批节点同意后，则该审批单通过。

```json
{
    "actionerUserId": "manager98xx",
    "processInstanceId": "fsTunaLIRyeRMrddA1YwZQ0964170020xxxx",
    "remark": "同意",
    "taskId": 8333450,
    "result": "agree",
    "file": {
        "attachments": [
            {
                "space_id": "817447xxxx",
                "file_size": "173404",
                "file_id": "6660150xxxx",
                "file_name": "评论附件.jpg",
                "file_type": "jpg"
            }
        ],
        "photos": [
            "https://help-static-aliyun-doc.aliyuncs.com/assets/img/zh-CN/9227796361/p352432.png"
        ]
    }
}
```

9. 撤销官方OA审批实例：查看审批后，若发现提交的审批单有误需撤销该审批实例，可根据审批实例`instanceId`，调用新版服务端API-[撤销审批实例](/document/development/revoke-an-approval-instance)，实现审批单的撤销操作。

```json
{
    "isSystem": true,
    "processInstanceId": "oKPAxjtgSP-AqeVTk-xxxx",
    "operatingUserId": "manager98xx",
    "remark": "撤销审批实例"
}
```

10. 审批单状态发生变化后，OA审批支持将[审批任务状态变化](/document/development/event-bpms-task-change)和[审批实例状态变化](/document/development/event-bpms-instance-change)等回调事件推送至业务系统侧，可以让企业应用能够更深度地与钉钉平台集成，实现信息共享和业务协同。具体使用教程参考：[事件订阅操作指南](/document/development/event-subscription-overview)。

## 客户案例

<https://page.dingtalk.com/wow/tianyuan/act/toufang?wh_showError=true&caseId=NTMzNg==>

![[development-use-the-dingtalk-oa-approval-process-and-page-interface_p835426.png]]