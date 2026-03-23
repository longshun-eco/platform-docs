---
title: "Teambition企业项目任务操作流程"
source: "https://open.dingtalk.com/document/development/team-ambition-project-operation-process"
category: "服务端API / Teambition 项目管理 / 使用教程"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-team-ambition-project-operation-process_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-team-ambition-project-operation-process_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-23本文介绍了Teambition企业项目任务操作流程。

## **流程简介**

本文档展示了，创建一个企业内部应用，使用Teambition项目管理提供的API，实现企业项目的相关操作流程：

步骤一：登录[开发者后台](https://open-dev.dingtalk.com/#/)，点击应用开发-企业内部开发，根据[创建应用](/document/dingstart/create-application)文档，创建企业内部应用。

步骤二：单击基础信息 > 应用信息，获取应用AppKey和AppSecret。

步骤三：根据[添加接口调用权限](/document/development/add-api-permission)文档，搜索“项目”，申请项目管理的接口权限。

步骤四：获取应用访问凭证[获取企业内部应用的accessToken](/document/development/obtain-the-access-token-of-an-internal-app)。调用接口时，通过accessToken鉴权调用者身份。

步骤五：调用项目管理相关API：

1. 根据企业项目模板创建企业项目：

   1. 创建企业项目模板，完成模板创建。
   2. 调用服务端API-[搜索企业项目模板](/document/development/search-for-enterprise-custom-templates-by-project-template-name)接口，获取企业项目模板ID。
   3. 根据企业项目模板ID。调用服务端API-[根据项目模板创建项目](/document/development/create-a-project-from-a-project-template)接口，实现企业项目的创建。获取项目ID。
2. 项目分组创建：

   1. 创建企业项目分组，完成分组创建。
   2. 调用服务端API-[查询员工可见的项目分组](/document/development/query-available-project-groups)接口，实现获取会议室列表内容。获取项目分组ID。
   3. 根据企业项目ID和项目分组ID，调用服务端API-[更新项目所在的分组](/document/development/update-project-grouping)接口，完成企业项目迁移至对应项目分组。
3. 企业项目操作操作流程：

   1. 根据企业项目ID，调用服务端API-[添加项目成员](/document/development/add-project-members)接口，实现企业项目成员添加操作。
   2. 调用服务端API-[查询优先级列表](/document/development/query-a-priority-list)接口，获取优先级内容信息。
   3. 根据企业项目ID，调用服务端API-[创建项目任务](/document/development/create-a-project-task)接口，实现企业项目具体任务创建流程。获取项目任务taskId。
   4. 根据项目任务taskId，调用服务端API-[添加任务的关联内容](/document/development/create-a-linked-object-associated-with-a-task)接口，添加项目任务关联说明。
   5. 根据企业项目ID，调用服务端API-[查询项目中的任务](/document/development/query-tasks-in-a-project)接口，查询项目中的任务信息。
   6. 根据项目任务taskId，调用服务端API-[创建计划工时](/document/development/create-planned-work)接口，完成单个企业项目任务添加计划工时。
   7. 根据项目任务taskId，调用服务端API-[创建实际工时](/document/development/create-actual-work)接口，完成单个企业项目任务添加计划工时。

## 步骤一：创建企业内部应用

**说明**

如果已有企业内部应用，可直接使用已有应用，可忽略此步骤。

1. 登录[开发者后台](https://open-dev.dingtalk.com/#/)，根据[创建应用](/document/dingstart/create-application)文档，创建企业内部应用。

   * 应用类型：选择H5微应用。
   * 开发方式：选择企业自主开发。

     ![[development-team-ambition-project-operation-process_p477411.png]]

## 步骤二：获取AppKey和AppSecret

获取应用AppKey和AppSecret信息。

![[development-team-ambition-project-operation-process_p477413.png]]

## 步骤三：添加接口权限

根据[添加接口调用权限](/document/development/add-api-permission)文档，搜索“项目”，申请项目管理的接口权限。

![[development-team-ambition-project-operation-process_p524594.png]]

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

1. 根据企业项目模板创建企业项目：

   1. 创建企业项目模板，完成模板创建。

      ![[development-team-ambition-project-operation-process_p524570.gif]]
   2. 调用服务端API-[搜索企业项目模板](/document/development/search-for-enterprise-custom-templates-by-project-template-name)接口，获取企业项目模板ID。

      ```java
      public void queryTemplates() throws Exception {
              Config config = new Config();
              config.protocol = "https";
              config.regionId = "central";
              com.aliyun.dingtalkproject_1_0.Client client = new com.aliyun.dingtalkproject_1_0.Client(config);
              SearchProjectTemplateHeaders searchProjectTemplateHeaders = new SearchProjectTemplateHeaders();
              searchProjectTemplateHeaders.xAcsDingtalkAccessToken = "accessToken";
              SearchProjectTemplateRequest searchProjectTemplateRequest = new SearchProjectTemplateRequest()
                      .setKeyword("测试模板");
              try {
                  SearchProjectTemplateResponse searchProjectTemplateResponse = client.searchProjectTemplateWithOptions("manager7675", searchProjectTemplateRequest, searchProjectTemplateHeaders, new RuntimeOptions());
                  System.out.println(JSON.toJSONString(searchProjectTemplateResponse.getBody()));
              } catch (TeaException err) {
                  if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                      // err 中含有 code 和 message 属性，可帮助开发定位问题
                      System.out.println(err.code);
                      System.out.println(err.message);
                  }

              } catch (Exception _err) {
                  TeaException err = new TeaException(_err.getMessage(), _err);
      ```
   3. 根据企业项目模板ID。调用服务端API-[根据项目模板创建项目](/document/development/create-a-project-from-a-project-template)接口，实现企业项目的创建。获取项目ID。

      ```java
        public void createProjectByTemplates() throws Exception {
              Config config = new Config();
              config.protocol = "https";
              config.regionId = "central";
              com.aliyun.dingtalkproject_1_0.Client client = new com.aliyun.dingtalkproject_1_0.Client(config);
              CreateProjectByTemplateHeaders createProjectByTemplateHeaders = new CreateProjectByTemplateHeaders();
              createProjectByTemplateHeaders.xAcsDingtalkAccessToken = "accessToken";
              CreateProjectByTemplateRequest createProjectByTemplateRequest = new CreateProjectByTemplateRequest()
                      .setName("project_1125测试项目")
                      .setTemplateId("638063f******10f79");
              try {
                  CreateProjectByTemplateResponse createProjectByTemplateResponse = client.createProjectByTemplateWithOptions("manager7675", createProjectByTemplateRequest, createProjectByTemplateHeaders, new RuntimeOptions());
                  System.out.println(JSON.toJSONString(createProjectByTemplateResponse.getBody()));
              } catch (TeaException err) {
                  if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                      // err 中含有 code 和 message 属性，可帮助开发定位问题
                      System.out.println(err.code);
                      System.out.println(err.message);
                  }
              } catch (Exception _err) {
                  TeaException err = new TeaException(_err.getMessage(), _err);
      ```
2. 项目分组创建：

   1. 创建企业项目分组，完成分组创建。

      ![[development-team-ambition-project-operation-process_p524550.png]]
   2. 调用服务端API-[查询员工可见的项目分组](/document/development/query-available-project-groups)接口，实现获取会议室列表内容。获取项目分组ID。

      ```java
      public void projectGroups() throws Exception {
              Config config = new Config();
              config.protocol = "https";
              config.regionId = "central";
              com.aliyun.dingtalkproject_1_0.Client client = new com.aliyun.dingtalkproject_1_0.Client(config);
              GetProjectGroupHeaders getProjectGroupHeaders = new GetProjectGroupHeaders();
              getProjectGroupHeaders.xAcsDingtalkAccessToken = "accessToken";
              GetProjectGroupRequest getProjectGroupRequest = new GetProjectGroupRequest()
                      .setViewerId("manager7675")
                      .setPageSize(10);
              try {
                  GetProjectGroupResponse getProjectGroupResponse = client.getProjectGroupWithOptions("manager7675", getProjectGroupRequest, getProjectGroupHeaders, new RuntimeOptions());
                  System.out.println(JSON.toJSONString(getProjectGroupResponse.getBody()));
              } catch (TeaException err) {
                  if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                      // err 中含有 code 和 message 属性，可帮助开发定位问题
                      System.out.println(err.code);
                      System.out.println(err.message);
                  }
              } catch (Exception _err) {
                  TeaException err = new TeaException(_err.getMessage(), _err);
      ```
   3. 根据企业项目ID和项目分组ID，调用服务端API-[更新项目所在的分组](/document/development/update-project-grouping)接口，完成企业项目迁移至对应项目分组。

      ```java
      public void  updateProjectGroups() throws Exception {
              Config config = new Config();
              config.protocol = "https";
              config.regionId = "central";
              com.aliyun.dingtalkproject_1_0.Client client = new com.aliyun.dingtalkproject_1_0.Client(config);
              UpdateProjectGroupHeaders updateProjectGroupHeaders = new UpdateProjectGroupHeaders();
              updateProjectGroupHeaders.xAcsDingtalkAccessToken = "accessToken";
              UpdateProjectGroupRequest updateProjectGroupRequest = new UpdateProjectGroupRequest()
                      .setAddProjectGroupIds(java.util.Arrays.asList(
                              "项目分组ID"
                      ));
              try {
                  UpdateProjectGroupResponse updateProjectGroupResponse = client.updateProjectGroupWithOptions("manager7675", "企业项目ID", updateProjectGroupRequest, updateProjectGroupHeaders, new RuntimeOptions());
                  System.out.println(JSON.toJSONString(updateProjectGroupResponse.getBody()));
              } catch (TeaException err) {
                  if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                      // err 中含有 code 和 message 属性，可帮助开发定位问题
                      System.out.println(err.code);
                      System.out.println(err.message);
                  }
              } catch (Exception _err) {
      ```
3. 企业项目操作操作流程：

   1. 根据企业项目ID，调用服务端API-[添加项目成员](/document/development/add-project-members)接口，实现企业项目成员添加操作。

      ```java
       public void addProjectUser() throws Exception {
              Config config = new Config();
              config.protocol = "https";
              config.regionId = "central";
              com.aliyun.dingtalkproject_1_0.Client client = new com.aliyun.dingtalkproject_1_0.Client(config);
              AddProjectMemberHeaders addProjectMemberHeaders = new AddProjectMemberHeaders();
              addProjectMemberHeaders.xAcsDingtalkAccessToken = "accessToken";
              AddProjectMemberRequest addProjectMemberRequest = new AddProjectMemberRequest()
                      .setUserIds(java.util.Arrays.asList(
                              "01472825524039877041"
                      ));
              try {
                  AddProjectMemberResponse addProjectMemberResponse = client.addProjectMemberWithOptions("manager7675", "企业项目ID", addProjectMemberRequest, addProjectMemberHeaders, new RuntimeOptions());
                  System.out.println(JSON.toJSONString(addProjectMemberResponse.getBody()));
              } catch (TeaException err) {
                  if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                      // err 中含有 code 和 message 属性，可帮助开发定位问题
                      System.out.println(err.code);
                      System.out.println(err.message);
                  }
              } catch (Exception _err) {
      ```
   2. 调用服务端API-[查询优先级列表](/document/development/query-a-priority-list)接口，获取优先级内容信息。

      ```java
      public void prioritiesList() throws Exception {
              Config config = new Config();
              config.protocol = "https";
              config.regionId = "central";
              com.aliyun.dingtalkproject_1_0.Client client = new com.aliyun.dingtalkproject_1_0.Client(config);
              GetOrganizationPriorityListHeaders getOrganizationPriorityListHeaders = new GetOrganizationPriorityListHeaders();
              getOrganizationPriorityListHeaders.xAcsDingtalkAccessToken = "accessToken";
              try {
                  GetOrganizationPriorityListResponse organizationPriorityListWithOptions = client.getOrganizationPriorityListWithOptions("manager7675", getOrganizationPriorityListHeaders, new RuntimeOptions());
                  System.out.println(JSON.toJSONString(organizationPriorityListWithOptions.getBody()));
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
                      System.out.println(err.code);
      ```
   3. 根据企业项目ID，调用服务端API-[创建项目任务](/document/development/create-a-project-task)接口，实现企业项目具体任务创建流程。获取项目任务taskId。

      ```java
       public void createProjectTask() throws Exception {
              Config config = new Config();
              config.protocol = "https";
              config.regionId = "central";
              com.aliyun.dingtalkproject_1_0.Client client = new com.aliyun.dingtalkproject_1_0.Client(config);
              com.aliyun.dingtalkproject_1_0.models.CreateTaskHeaders createTaskHeaders = new com.aliyun.dingtalkproject_1_0.models.CreateTaskHeaders();
              createTaskHeaders.xAcsDingtalkAccessToken = "accessToken";

              com.aliyun.dingtalkproject_1_0.models.CreateTaskRequest createTaskRequest = new com.aliyun.dingtalkproject_1_0.models.CreateTaskRequest()
                      .setProjectId("638065*********f66469")
                      .setContent("任务标题：1125标题测试")
                      .setExecutorId("01472825524039877041")
                      .setDueDate("2022-11-28T18:30:00Z")
                      .setNote("备注：1125备注测试")
                      .setPriority(1);
              try {
                  CreateTaskResponse createTaskResponse = client.createTaskWithOptions("manager7675", createTaskRequest, createTaskHeaders, new RuntimeOptions());
                  System.out.println(JSON.toJSONString(createTaskResponse.getBody()));
              } catch (TeaException err) {
                  if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                      // err 中含有 code 和 message 属性，可帮助开发定位问题
      ```
   4. 根据项目任务taskId，调用服务端API-[添加任务的关联内容](/document/development/create-a-linked-object-associated-with-a-task)接口，添加项目任务关联说明。

      ```java
      public void addObjectLinks() throws Exception {
              Config config = new Config();
              config.protocol = "https";
              config.regionId = "central";
              com.aliyun.dingtalkproject_1_0.Client client = new com.aliyun.dingtalkproject_1_0.Client(config);
              CreateTaskObjectLinkHeaders createTaskObjectLinkHeaders = new CreateTaskObjectLinkHeaders();
              createTaskObjectLinkHeaders.xAcsDingtalkAccessToken = "accessToken";
              CreateTaskObjectLinkRequest.CreateTaskObjectLinkRequestLinkedData linkedData = new CreateTaskObjectLinkRequest.CreateTaskObjectLinkRequestLinkedData()
                      .setTitle("关联内容标题：标题测试")
                      .setContent("关联内容：内容测试")
                      .setUrl("https://www.dingtalk.com")
                      .setThumbnailUrl("https://example/k/钉钉图片1.png");
              CreateTaskObjectLinkRequest createTaskObjectLinkRequest = new CreateTaskObjectLinkRequest()
                      .setLinkedData(linkedData);
              try {
                  CreateTaskObjectLinkResponse createTaskObjectLinkResponse = client.createTaskObjectLinkWithOptions("manager7675", "项目任务ID", createTaskObjectLinkRequest, createTaskObjectLinkHeaders, new RuntimeOptions());
                  System.out.println(JSON.toJSONString(createTaskObjectLinkResponse.getBody()));
              } catch (TeaException err) {
                  if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                      // err 中含有 code 和 message 属性，可帮助开发定位问题
                      System.out.println(err.code);
      ```
   5. 根据企业项目ID，调用服务端API-[查询项目中的任务](/document/development/query-tasks-in-a-project)接口，查询项目中的任务信息。

      ```java
      public void queryTasks() throws Exception {
              Config config = new Config();
              config.protocol = "https";
              config.regionId = "central";
              com.aliyun.dingtalkproject_1_0.Client client = new com.aliyun.dingtalkproject_1_0.Client(config);
              com.aliyun.dingtalkproject_1_0.models.QueryTaskOfProjectHeaders queryTaskOfProjectHeaders = new com.aliyun.dingtalkproject_1_0.models.QueryTaskOfProjectHeaders();
              queryTaskOfProjectHeaders.xAcsDingtalkAccessToken = "accessToken";
              com.aliyun.dingtalkproject_1_0.models.QueryTaskOfProjectRequest queryTaskOfProjectRequest = new com.aliyun.dingtalkproject_1_0.models.QueryTaskOfProjectRequest()
                      .setMaxResults(10)
                      .setQuery("executorId IN \"01472825524039877041\" ORDER BY priority DESC");
              try {
                  QueryTaskOfProjectResponse queryTaskOfProjectResponse = client.queryTaskOfProjectWithOptions("manager7675", "企业项目ID", queryTaskOfProjectRequest, queryTaskOfProjectHeaders, new RuntimeOptions());
                  System.out.println(JSON.toJSONString(queryTaskOfProjectResponse.getBody()));
              } catch (TeaException err) {
                  if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                      // err 中含有 code 和 message 属性，可帮助开发定位问题
                      System.out.println(err.code);
                      System.out.println(err.message);
                  }
              } catch (Exception _err) {
                  TeaException err = new TeaException(_err.getMessage(), _err);
      ```
   6. 根据项目任务taskId，调用服务端API-[创建计划工时](/document/development/create-planned-work)接口，完成单个企业项目任务添加计划工时。

      ```java
        public void createPlanTimes() throws Exception {
              Config config = new Config();
              config.protocol = "https";
              config.regionId = "central";
              com.aliyun.dingtalkproject_1_0.Client client = new com.aliyun.dingtalkproject_1_0.Client(config);
              com.aliyun.dingtalkproject_1_0.models.CreatePlanTimeHeaders createPlanTimeHeaders = new com.aliyun.dingtalkproject_1_0.models.CreatePlanTimeHeaders();
              createPlanTimeHeaders.xAcsDingtalkAccessToken = "accessToken";
              com.aliyun.dingtalkproject_1_0.models.CreatePlanTimeRequest createPlanTimeRequest = new com.aliyun.dingtalkproject_1_0.models.CreatePlanTimeRequest()
                      .setTenantType("organization")
                      .setExecutorId("01472825524039877041")
                      .setObjectId("6380*********51dfe")
                      .setObjectType("task")
                      .setIsDuration(true)
                      .setIncludesHolidays(true)
                      .setSubmitterId("01472825524039877041")
                      .setStartDate("2022-11-25")
                      .setEndDate("2022-11-25")
                      .setPlanTime(36000000L);
              try {
                  CreatePlanTimeResponse createPlanTimeResponse = client.createPlanTimeWithOptions("manager7675", createPlanTimeRequest, createPlanTimeHeaders, new RuntimeOptions());
                  System.out.println(JSON.toJSONString(createPlanTimeResponse.getBody()));
      ```
   7. 根据项目任务taskId，调用服务端API-[创建实际工时](/document/development/create-actual-work)接口，完成单个企业项目任务添加计划工时。

      ```java
      public void createWorkTimes() throws Exception {
              Config config = new Config();
              config.protocol = "https";
              config.regionId = "central";
              com.aliyun.dingtalkproject_1_0.Client client = new com.aliyun.dingtalkproject_1_0.Client(config);
              com.aliyun.dingtalkproject_1_0.models.CreateWorkTimeHeaders createWorkTimeHeaders = new com.aliyun.dingtalkproject_1_0.models.CreateWorkTimeHeaders();
              createWorkTimeHeaders.xAcsDingtalkAccessToken = "accessToken";
              com.aliyun.dingtalkproject_1_0.models.CreateWorkTimeRequest createWorkTimeRequest = new com.aliyun.dingtalkproject_1_0.models.CreateWorkTimeRequest()
                      .setTenantType("organization")
                      .setExecutorId("01472825524039877041")
                      .setObjectId("63806**********51dfe")
                      .setObjectType("task")
                      .setSubmitterId("01472825524039877041")
                      .setIsDuration(true)
                      .setIncludesHolidays(true)
                      .setStartDate("2022-11-25")
                      .setEndDate("2022-11-25")
                      .setWorkTime(36000000L);
              try {
                  CreateWorkTimeResponse createWorkTimeResponse = client.createWorkTimeWithOptions("manager7675", createWorkTimeRequest, createWorkTimeHeaders, new RuntimeOptions());
                  System.out.println(JSON.toJSONString(createWorkTimeResponse.getBody()));
      ```