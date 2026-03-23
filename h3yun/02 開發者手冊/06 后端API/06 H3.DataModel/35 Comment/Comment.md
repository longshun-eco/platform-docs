---
title: "Comment"
source: "https://help.h3yun.com/contents/374/395.html"
category: "開發者手冊 / 后端API / H3.DataModel / Comment"
updated: 2025-12-23
tags:
  - h3yun
  - 開發者手冊
---
类名 : Comment
说明 : 用于记录用户对于业务对象在每条流程中的审批意见 属性 : 

| 名称 | 说明 |
| --- | --- |
| CommentId | 审批意见的Id |
| SchemaCode | 业务对象模式编码 |
| BizObjectId | 业务对象ID |
| InstanceId | 流程实例Id |
| Activity | 活动名称 |
| UserId | 用户ID |
| Delegant | 代理给他人的源，比如：A委托给B，那么B将会是这个工作项的参与者，A是Delegant；同样，对于转发也是这样的，A转发给B，B是参与者，A是Delegant |
| UserParentName | 部门或者是公司名称，用于记录审批人当时隶属于的部门或者公司 |
| TokenId | 流程令牌的Id |
| Text | 审批意见的内容 |
| Approval | 审批结果 |
| CreatedTime | 创建时间 |
| ModifiedTime | 修改时间 |
| ModifiedBy | 最后一个修改用户 |
| Signature | 电子签章,类似base64的数据流 |
| AttachmentIds | 审批附件 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| TableName | 表名称 |
| PropertyName\_SchemaCode | 属性名称 |
| PropertyName\_BizObjectId | 属性名称 |
| PropertyName\_InstanceId | 属性名称 |
| PropertyName\_Activity | 属性名称 |
| PropertyName\_UserId | 属性名称 |
| PropertyName\_Delegant | 代理给他人的源 属性名称 |
| PropertyName\_UserParentName | 属性名称 |
| PropertyName\_TokenId | 属性名称 |
| PropertyName\_Text | 属性名称 |
| PropertyName\_Approval | 属性名称 |
| PropertyName\_CreatedTime | 属性名称 |
| PropertyName\_ModifiedTime | 属性名称 |
| PropertyName\_ModifiedBy | 属性名称 |
| PropertyName\_Signature | 电子签章,类似base64的数据流 |
| PropertyName\_AttachmentIds | 附件Id |


构造方法名称 : #ctor

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| |  |


方法名称 : Clone

| 参数 | 说明 |
| --- | --- |
| |
 |
| 返回值 |  |
| 克隆出来的审批意见 |  |