---
title: "ISNSManager"
source: "https://help.h3yun.com/contents/674/774.html"
category: "開發者手冊 / 后端API / H3.SNS / ISNSManager"
updated: 2025-12-22
tags:
  - h3yun
  - 開發者手冊
---
类名 : ISNSManager
说明 : 社交管理器 
方法名称 : SetRelationship(H3.SNS.SNSRelationship)

| 参数 | 说明 |
| --- | --- |
| "relationship" | 业务对象的关注关系 |
| 返回值 |  |
| |  |


方法名称 : GetRelationships(System.String,System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "userId" | 用户Id |
| "schemaCodes" | 业务对象模式编码 |
| 返回值 |  |
| 业务对象模式关注关系 |  |


方法名称 : AddPostFile(H3.SNS.SNSPostFile)

| 参数 | 说明 |
| --- | --- |
| "file" | 帖子的附件 |
| 返回值 |  |
| |  |


方法名称 : AddPost(H3.SNS.SNSPost,System.String\[\],System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "post" | 要添加的帖子 |
| "postFileIds" | 新添加的帖子的附件的ID |
| "ownerFeedId" | 创建人的动态的ID |
| "dispatchFeed" | 分发Feed |
| 返回值 |  |
| |  |


方法名称 : GetPost(System.String,H3.SNS.SNSPostFileHeader\[\]@,H3.SNS.SNSComment\[\]@)

| 参数 | 说明 |
| --- | --- |
| "postId" | 帖子Id |
| "fileHeaders" | 与这个帖子相关的文件 |
| "comments" | 与这个帖子相关的所有用户评论 |
| 返回值 |  |
| 帖子信息 |  |


方法名称 : UpdatePost(H3.SNS.SNSPost,System.String\[\],System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "post" | 要更新的帖子的新内容 |
| "removedPostFileIds" | 要删除的帖子的附件 |
| "addedPostFileIds" | 新增加的帖子的附件 |
| 返回值 |  |
| |  |


方法名称 : DeletePost(System.String)

| 参数 | 说明 |
| --- | --- |
| "postId" | 要删除的帖子的ID |
| 返回值 |  |
| |  |


方法名称 : AddComment(System.String,System.String,System.String,System.String,System.String,System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "replyTo" | 要回复的评论的Id |
| "replyToUserId" | 回复给的用户的Id |
| "schemaCode" | 业务对象模式编码 |
| "bizObjectId" | 业务对象ID |
| "postId" | 帖子的ID，BizObjectId下面可以发帖子，帖子可以被回复 |
| "userId" | 用户ID |
| "text" | 评论的内容 |
| "newCommentId" | 前端传递过来的评论唯一ID |
| 返回值 |  |
| |  |


方法名称 : LikeFeed(System.String,System.String,System.String,System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "replyTo" | 要回复的评论的ID |
| "schemaCode" | 业务对象模式编码 |
| "bizObjectId" | 业务对象ID |
| "postId" | 帖子的Id，BizObjectId下面可以发帖子，帖子可以被回复 |
| "userId" | 用户ID |
| "objectId" | 前端传递过来的评论唯一ID |
| 返回值 |  |
| |  |


方法名称 : DeleteComment(System.String)

| 参数 | 说明 |
| --- | --- |
| "commentId" | 评论的Id |
| 返回值 |  |
| |  |


方法名称 : SetSharingItem(System.String,H3.LinkTargetType,System.String,System.String,System.String,System.String,System.Boolean,H3.SNS.SNSSharingItemPermissionType,System.String\[\],System.String\[\],System.String)

| 参数 | 说明 |
| --- | --- |
| "sender" | 发送分享的人 |
| "targetType" | 要分享的对象的类型 |
| "schemaCode" | 要分享的对象的业务对象模式编码 |
| "bizObjectId" | 要分享的业务对象的ID |
| "targetId" | 要分享的目标对象的ID，如果是WorkItem，则是WorkItemId |
| "targetName" | 要分享的目标对象的名称 |
| "isPublic" | 预留参数：是否是公开的，如果是公开的话，那么意味着只要用户知道SharingItemId，即可打开相应的表单。如果要发送给外部用户，那么必须是IsPublic=true的 |
| "permission" | 要分享的对象的权限 |
| "internalReceivers" | 内部接收分享的用户 |
| "externalReceivers" | 预留参数：外部接收分享的用户，格式是每个用户的邮箱 |
| "text" | 要分享的内容的描述，如果外部接收人员不为空的，则需要填写该字段 |
| 返回值 |  |
| |  |


方法名称 : GetSharingItem(System.String)

| 参数 | 说明 |
| --- | --- |
| "sharingItemId" | 分享设置的ID |
| 返回值 |  |
| 分享的详细信息 |  |


方法名称 : GetSharingItemBySender(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "targetId" | 分享的对象的ID |
| "sender" | 分享的发送者 |
| 返回值 |  |
| 分享的设置信息 |  |


方法名称 : GetSharingItemBySenderObjectId(System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "targetId" | 分享的对象的ID |
| "sender" | 分享的发送者 |
| 返回值 |  |
| 分享的设置信息 |  |


方法名称 : GetSharingItemReceivers(System.String)

| 参数 | 说明 |
| --- | --- |
| "bizObjectId" | 业务对象ID |
| 返回值 |  |
| 分享的接收者 |  |


方法名称 : DeleteSharingItem(System.String)

| 参数 | 说明 |
| --- | --- |
| "sharingItemId" | 分享设置 |
| 返回值 |  |
| |  |


方法名称 : GetPostFileHeaders(System.String\[\])

| 参数 | 说明 |
| --- | --- |
| "fileIds" | 文件ID |
| 返回值 |  |
| 所有的文件头信息 |  |


方法名称 : GetPostFile(System.String)

| 参数 | 说明 |
| --- | --- |
| "fileId" | 文件Id |
| 返回值 |  |
| 文件头信息 |  |