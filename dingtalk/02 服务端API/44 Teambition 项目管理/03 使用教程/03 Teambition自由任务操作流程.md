---
title: "Teambition自由任务操作流程"
source: "https://open.dingtalk.com/document/development/teambition-free-task-operation-process"
category: "服务端API / Teambition 项目管理 / 使用教程"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-teambition-free-task-operation-process_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-teambition-free-task-operation-process_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-23本文介绍了Teambition自由任务操作流程。

## **预期效果**

### **自由任务展示**

![[development-teambition-free-task-operation-process_p525634.png]]

## **流程简介**

本文档展示了，创建一个企业内部应用，使用Teambition项目管理提供的API，实现自由任务的相关操作流程：

步骤一：登录[开发者后台](https://open-dev.dingtalk.com/#/)，点击应用开发-企业内部开发，根据[创建应用](/document/dingstart/create-application)文档，创建企业内部应用。

步骤二：单击基础信息 > 应用信息，获取应用AppKey和AppSecret。

步骤三：根据[添加接口调用权限](/document/development/add-api-permission)文档，搜索“项目”，申请项目管理的接口权限。

步骤四：获取应用访问凭证[获取企业内部应用的accessToken](/document/development/obtain-the-access-token-of-an-internal-app)。调用接口时，通过accessToken鉴权调用者身份。

步骤五：调用项目管理相关API：

1. 创建自由任务：

   1. 调用服务端API-[创建自由任务](/document/development/create-a-free-task)接口，实现自由任务创建，获取自由任务ID。
2. 自由任务管理相关操作：

   * 根据自由任务ID，调用服务端API-[更新自由任务的优先级](/document/development/change-free-task-priority)接口，实现自由任务优先级更新操作。
   * 根据自由任务ID，调用服务端API-[更新自由任务标题](/document/development/change-free-task-title)接口，实现自由任务标题更新操作。
   * 根据自由任务ID，调用服务端API-[更新自由任务截止时间](/document/development/change-free-task-deadline)接口，实现自由任务截止时间更新操作。
   * 根据自由任务ID，调用服务端API-[更新自由任务执行者](/document/development/change-free-task-executor)接口，实现自由任务执行者更新操作。
   * 根据自由任务ID，调用服务端API-[增加或删除自由任务的参与者](/document/development/change-task-participant)接口，实现自由任务参与者更新操作。
   * 根据自由任务ID，调用服务端API-[更新自由任务备注](/document/development/update-free-task-notes)接口，实现自由任务备注更新操作。
   * 根据自由任务ID，调用服务端API-[更新自由任务状态](/document/development/change-free-task-status)接口，实现完成自由任务。
3. 自由任务查询相关操作：

   * 根据自由任务ID，调用服务端API-[获取自由任务详情](/document/development/queries-free-task-details)接口，实现获取单个自由任务的详细信息。
   * 根据自由任务ID，调用服务端API-[批量获取自由任务详情](/document/development/obtains-details-about-multiple-free-tasks)接口，实现获取多个自由任务的详细信息。

## 步骤一：创建企业内部应用

**说明**

如果已有企业内部应用，可直接使用已有应用，可忽略此步骤。

1. 登录[开发者后台](https://open-dev.dingtalk.com/#/)，根据[创建应用](/document/dingstart/create-application)文档，创建企业内部应用。

   * 应用类型：选择H5微应用。
   * 开发方式：选择企业自主开发。

     ![[development-teambition-free-task-operation-process_p477411.png]]

## 步骤二：获取AppKey和AppSecret

获取应用AppKey和AppSecret信息。

![[development-teambition-free-task-operation-process_p477413.png]]

## 步骤三：添加接口权限

根据[添加接口调用权限](/document/development/add-api-permission)文档，搜索“项目”，申请项目管理的接口权限。

![[development-teambition-free-task-operation-process_p524594.png]]

## 步骤四：获取应用访问凭证accessToken

**重要**

服务端API差异详情参见[旧版服务端API、新版服务端API的区别](/document/development/how-to-call-apis#section-8lr-id4-rbz)。以下接口均使用服务端API接口，SDK下载详情参见[服务端SDK下载](/document/development/download-the-server-side-sdk)。

根据步骤二中的AppKey和AppSecret，获取应用访问凭证[获取企业内部应用的accessToken](/document/development/obtain-the-access-token-of-an-internal-app)。

```java
 public void getAccessToken() throws Exception {
        Config config = new Config();
        config.protocol = "https";
        config.regionId = "central";
        com.aliyun.dingtalkoauth2_1_0.Client client = new com.aliyun.dingtalkoauth2_1_0.Client(config);
        GetAccessTokenRequest accessTokenRequest = new GetAccessTokenRequest()
                .setAppKey("din*********hgn")
                .setAppSecret("9G_O************mBkhgGIO");
        GetAccessTokenResponse accessToken = client.getAccessToken(accessTokenRequest);
        System.out.println(JSON.toJSONString(accessToken.getBody()));
    }
```

## **步骤五：调用项目管理相关API**

1. 创建自由任务：

   1. 调用服务端API-[创建自由任务](/document/development/create-a-free-task)接口，实现自由任务创建，获取自由任务ID。

      ```java
      public void createFreeMission() throws Exception {
              Config config = new Config();
              config.protocol = "https";
              config.regionId = "central";
              com.aliyun.dingtalkproject_1_0.Client client = new com.aliyun.dingtalkproject_1_0.Client(config);
              CreateOrganizationTaskHeaders createOrganizationTaskHeaders = new CreateOrganizationTaskHeaders();
              createOrganizationTaskHeaders.xAcsDingtalkAccessToken = "accessToken";
              CreateOrganizationTaskRequest createOrganizationTaskRequest = new CreateOrganizationTaskRequest()
                      .setContent("任务标题：明天12点前完成周报撰写")
                      .setNote("任务备注：任务备注信息")
                      .setPriority(1)
                      .setInvolveMembers(java.util.Arrays.asList(
                              "01472825524039877041","manager7675"
                      ))
                      .setExecutorId("01472825524039877041")
                      .setDueDate("2022-11-30T00:00:00Z")
                      .setCreateTime("2022-11-29T00:00:00Z")
                      .setVisible("involves")
                      .setDisableNotification(false)
                      .setDisableActivity(false);
              try {
      ```
2. 自由任务管理相关操作：

   * 根据自由任务ID，调用服务端API-[更新自由任务的优先级](/document/development/change-free-task-priority)接口，实现自由任务优先级更新操作。

     ```java
      public void updateFreeMissionPriorities() throws Exception {
             Config config = new Config();
             config.protocol = "https";
             config.regionId = "central";
             com.aliyun.dingtalkproject_1_0.Client client = new com.aliyun.dingtalkproject_1_0.Client(config);
             UpdateOrganizationTaskPriorityHeaders updateOrganizationTaskPriorityHeaders = new UpdateOrganizationTaskPriorityHeaders();
             updateOrganizationTaskPriorityHeaders.xAcsDingtalkAccessToken = "accessToken";
             UpdateOrganizationTaskPriorityRequest updateOrganizationTaskPriorityRequest = new UpdateOrganizationTaskPriorityRequest()
                     .setPriority(2)
                     .setDisableActivity(false)
                     .setDisableNotification(false);
             try {
                 UpdateOrganizationTaskPriorityResponse updateOrganizationTaskPriorityResponse = client.updateOrganizationTaskPriorityWithOptions("63856f*****ea3e77f", "manager7675", updateOrganizationTaskPriorityRequest, updateOrganizationTaskPriorityHeaders, new RuntimeOptions());
                 System.out.println(JSON.toJSONString(updateOrganizationTaskPriorityResponse.getBody()));
             } catch (TeaException err) {
                 if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                     // err 中含有 code 和 message 属性，可帮助开发定位问题
                     System.out.println(err.code);
                     System.out.println(err.message);
                 }
             } catch (Exception _err) {
     ```
   * 根据自由任务ID，调用服务端API-[更新自由任务标题](/document/development/change-free-task-title)接口，实现自由任务标题更新操作。

     ```java
     public void updateFreeMissionContent() throws Exception {
             Config config = new Config();
             config.protocol = "https";
             config.regionId = "central";
             com.aliyun.dingtalkproject_1_0.Client client = new com.aliyun.dingtalkproject_1_0.Client(config);
             UpdateOrganizationTaskContentHeaders updateOrganizationTaskContentHeaders = new UpdateOrganizationTaskContentHeaders();
             updateOrganizationTaskContentHeaders.xAcsDingtalkAccessToken = "accessToken";
             UpdateOrganizationTaskContentRequest updateOrganizationTaskContentRequest = new UpdateOrganizationTaskContentRequest()
                     .setContent("修改后的文档标题：后天12点前完成周报撰写")
                     .setDisableActivity(false)
                     .setDisableNotification(false);
             try {
                 UpdateOrganizationTaskContentResponse updateOrganizationTaskContentResponse = client.updateOrganizationTaskContentWithOptions("63856f*****ea3e77f", "manager7675", updateOrganizationTaskContentRequest, updateOrganizationTaskContentHeaders, new RuntimeOptions());
                 System.out.println(JSON.toJSONString(updateOrganizationTaskContentResponse.getBody()));
             } catch (TeaException err) {
                 if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                     // err 中含有 code 和 message 属性，可帮助开发定位问题
                     System.out.println(err.code);
                     System.out.println(err.message);
                 }
             } catch (Exception _err) {
     ```
   * 根据自由任务ID，调用服务端API-[更新自由任务截止时间](/document/development/change-free-task-deadline)接口，实现自由任务截止时间更新操作。

     ```java
     public void  updateFreeMissionDueDates() throws Exception {
             Config config = new Config();
             config.protocol = "https";
             config.regionId = "central";
             com.aliyun.dingtalkproject_1_0.Client client = new com.aliyun.dingtalkproject_1_0.Client(config);
             UpdateOrganizationTaskDueDateHeaders updateOrganizationTaskDueDateHeaders = new UpdateOrganizationTaskDueDateHeaders();
             updateOrganizationTaskDueDateHeaders.xAcsDingtalkAccessToken = "accessToken";
             UpdateOrganizationTaskDueDateRequest updateOrganizationTaskDueDateRequest = new UpdateOrganizationTaskDueDateRequest()
                     .setDueDate("2022-12-01T00:00:00Z")
                     .setDisableActivity(false)
                     .setDisableNotification(false);
             try {
                 UpdateOrganizationTaskDueDateResponse updateOrganizationTaskDueDateResponse = client.updateOrganizationTaskDueDateWithOptions("63856f*****ea3e77f", "manager7675", updateOrganizationTaskDueDateRequest, updateOrganizationTaskDueDateHeaders, new RuntimeOptions());
                 System.out.println(JSON.toJSONString(updateOrganizationTaskDueDateResponse.getBody()));
             } catch (TeaException err) {
                 if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                     // err 中含有 code 和 message 属性，可帮助开发定位问题
                     System.out.println(err.code);
                     System.out.println(err.message);
                 }
             } catch (Exception _err) {
     ```
   * 根据自由任务ID，调用服务端API-[更新自由任务执行者](/document/development/change-free-task-executor)接口，实现自由任务执行者更新操作。

     ```java
     public void updateFreeMissionExecutors() throws Exception {
             Config config = new Config();
             config.protocol = "https";
             config.regionId = "central";
             com.aliyun.dingtalkproject_1_0.Client client = new com.aliyun.dingtalkproject_1_0.Client(config);
             UpdateOrganizationTaskExecutorHeaders updateOrganizationTaskExecutorHeaders = new UpdateOrganizationTaskExecutorHeaders();
             updateOrganizationTaskExecutorHeaders.xAcsDingtalkAccessToken = "accessToken";
             UpdateOrganizationTaskExecutorRequest updateOrganizationTaskExecutorRequest = new UpdateOrganizationTaskExecutorRequest()
                     .setExecutorId("01472825524039877041")
                     .setDisableActivity(false)
                     .setDisableNotification(false);
             try {
                 UpdateOrganizationTaskExecutorResponse updateOrganizationTaskExecutorResponse = client.updateOrganizationTaskExecutorWithOptions("63856f*****ea3e77f", "manager7675", updateOrganizationTaskExecutorRequest, updateOrganizationTaskExecutorHeaders, new RuntimeOptions());
                 System.out.println(JSON.toJSONString(updateOrganizationTaskExecutorResponse.getBody()));
             } catch (TeaException err) {
                 if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                     // err 中含有 code 和 message 属性，可帮助开发定位问题
                     System.out.println(err.code);
                     System.out.println(err.message);
                 }
     ```
   * 根据自由任务ID，调用服务端API-[增加或删除自由任务的参与者](/document/development/change-task-participant)接口，实现自由任务参与者更新操作。

     ```java
     public void  updateFreeMissionInvolveMembers() throws Exception {
             Config config = new Config();
             config.protocol = "https";
             config.regionId = "central";
             com.aliyun.dingtalkproject_1_0.Client client = new com.aliyun.dingtalkproject_1_0.Client(config);
             UpdateOrganizationTaskInvolveMembersHeaders updateOrganizationTaskInvolveMembersHeaders = new UpdateOrganizationTaskInvolveMembersHeaders();
             updateOrganizationTaskInvolveMembersHeaders.xAcsDingtalkAccessToken = "accessToken";
             UpdateOrganizationTaskInvolveMembersRequest updateOrganizationTaskInvolveMembersRequest = new UpdateOrganizationTaskInvolveMembersRequest()
                     .setAddInvolvers(java.util.Arrays.asList(
                             "08521816421284272"
                     ))
                     .setDisableActivity(false)
                     .setDisableNotification(false);
             try {
                 UpdateOrganizationTaskInvolveMembersResponse updateOrganizationTaskInvolveMembersResponse = client.updateOrganizationTaskInvolveMembersWithOptions("63856f*****ea3e77f", "manager7675", updateOrganizationTaskInvolveMembersRequest, updateOrganizationTaskInvolveMembersHeaders, new RuntimeOptions());
                 System.out.println(JSON.toJSONString(updateOrganizationTaskInvolveMembersResponse.getBody()));
             } catch (TeaException err) {
                 if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                     // err 中含有 code 和 message 属性，可帮助开发定位问题
                     System.out.println(err.code);
                     System.out.println(err.message);
     ```
   * 根据自由任务ID，调用服务端API-[更新自由任务备注](/document/development/update-free-task-notes)接口，实现自由任务备注更新操作。

     ```java
     public void updateFreeMissionNotes() throws Exception {
             Config config = new Config();
             config.protocol = "https";
             config.regionId = "central";
             com.aliyun.dingtalkproject_1_0.Client client = new com.aliyun.dingtalkproject_1_0.Client(config);
             UpdateOrganizationTaskNoteHeaders updateOrganizationTaskNoteHeaders = new UpdateOrganizationTaskNoteHeaders();
             updateOrganizationTaskNoteHeaders.xAcsDingtalkAccessToken = "accessToken";
             UpdateOrganizationTaskNoteRequest updateOrganizationTaskNoteRequest = new UpdateOrganizationTaskNoteRequest()
                     .setNote("备注：更新后的备注信息")
                     .setDisableActivity(false)
                     .setDisableNotification(false);
             try {
                 UpdateOrganizationTaskNoteResponse updateOrganizationTaskNoteResponse = client.updateOrganizationTaskNoteWithOptions("63856f*****ea3e77f", "manager7675", updateOrganizationTaskNoteRequest, updateOrganizationTaskNoteHeaders, new RuntimeOptions());
                 System.out.println(JSON.toJSONString(updateOrganizationTaskNoteResponse.getBody()));
             } catch (TeaException err) {
                 if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                     // err 中含有 code 和 message 属性，可帮助开发定位问题
                     System.out.println(err.code);
                     System.out.println(err.message);
                 }
             } catch (Exception _err) {
     ```
   * 根据自由任务ID，调用服务端API-[更新自由任务状态](/document/development/change-free-task-status)接口，实现完成自由任务。

     ```java
     public void updateFreeMissionStates() throws Exception {
             Config config = new Config();
             config.protocol = "https";
             config.regionId = "central";
             com.aliyun.dingtalkproject_1_0.Client client = new com.aliyun.dingtalkproject_1_0.Client(config);
             UpdateOrganizationTaskStatusHeaders updateOrganizationTaskStatusHeaders = new UpdateOrganizationTaskStatusHeaders();
             updateOrganizationTaskStatusHeaders.xAcsDingtalkAccessToken = "accessToken";
             UpdateOrganizationTaskStatusRequest updateOrganizationTaskStatusRequest = new UpdateOrganizationTaskStatusRequest()
                     .setIsDone(true)
                     .setDisableActivity(false)
                     .setDisableNotification(false);
             try {
                 UpdateOrganizationTaskStatusResponse updateOrganizationTaskStatusResponse = client.updateOrganizationTaskStatusWithOptions("63856f*****ea3e77f", "manager7675", updateOrganizationTaskStatusRequest, updateOrganizationTaskStatusHeaders, new RuntimeOptions());
                 System.out.println(JSON.toJSONString(updateOrganizationTaskStatusResponse.getBody()));
             } catch (TeaException err) {
                 if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                     // err 中含有 code 和 message 属性，可帮助开发定位问题
                     System.out.println(err.code);
                     System.out.println(err.message);
                 }
             } catch (Exception _err) {
     ```
3. 自由任务查询相关操作：

   * 根据自由任务ID，调用服务端API-[获取自由任务详情](/document/development/queries-free-task-details)接口，实现获取单个自由任务的详细信息。

     ```java
     public void FreeMissionInfo() throws Exception {
             Config config = new Config();
             config.protocol = "https";
             config.regionId = "central";
             com.aliyun.dingtalkproject_1_0.Client client = new com.aliyun.dingtalkproject_1_0.Client(config);
             GetOrganizationTaskHeaders getOrganizationTaskHeaders = new GetOrganizationTaskHeaders();
             getOrganizationTaskHeaders.xAcsDingtalkAccessToken = "accessToken";
             try {
                 GetOrganizationTaskResponse getOrganizationTaskResponse = client.getOrganizationTaskWithOptions("63856f*****ea3e77f", "manager7675", getOrganizationTaskHeaders, new RuntimeOptions());
                 System.out.println(JSON.toJSONString(getOrganizationTaskResponse.getBody()));
             } catch (TeaException err) {
                 if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                     // err 中含有 code 和 message 属性，可帮助开发定位问题
                     System.out.println(err.code);
                     System.out.println(err.message);
                 }

             } catch (Exception _err) {
                 TeaException err = new TeaException(_err.getMessage(), _err);
                 if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                     // err 中含有 code 和 message 属性，可帮助开发定位问题
     ```
   * 根据自由任务ID，调用服务端API-[批量获取自由任务详情](/document/development/obtains-details-about-multiple-free-tasks)接口，实现获取多个自由任务的详细信息。

     ```java
     public void FreeMissionInfoBatch() throws Exception {
             Config config = new Config();
             config.protocol = "https";
             config.regionId = "central";
             com.aliyun.dingtalkproject_1_0.Client client = new com.aliyun.dingtalkproject_1_0.Client(config);
             GetOrganizatioTaskByIdsHeaders getOrganizatioTaskByIdsHeaders = new GetOrganizatioTaskByIdsHeaders();
             getOrganizatioTaskByIdsHeaders.xAcsDingtalkAccessToken = "accessToken";
             GetOrganizatioTaskByIdsRequest getOrganizatioTaskByIdsRequest = new GetOrganizatioTaskByIdsRequest()
                     .setTaskIds("63856f*****ea3e77f,63857b4d*****f97cb4ee");
             try {
                 GetOrganizatioTaskByIdsResponse getOrganizatioTaskByIdsResponse = client.getOrganizatioTaskByIdsWithOptions("manager7675", getOrganizatioTaskByIdsRequest, getOrganizatioTaskByIdsHeaders, new RuntimeOptions());
                 System.out.println(JSON.toJSONString(getOrganizatioTaskByIdsResponse.getBody()));
             } catch (TeaException err) {
                 if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                     // err 中含有 code 和 message 属性，可帮助开发定位问题
                     System.out.println(err.code);
                     System.out.println(err.message);
                 }

             } catch (Exception _err) {
                 TeaException err = new TeaException(_err.getMessage(), _err);
     ```