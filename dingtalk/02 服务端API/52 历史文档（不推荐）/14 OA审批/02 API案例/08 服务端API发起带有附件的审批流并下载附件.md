---
title: "服务端API发起带有附件的审批流并下载附件"
source: "https://open.dingtalk.com/document/development/initiate-an-approval-flow-with-attachments"
category: "服务端API / 历史文档（不推荐） / OA审批 / API案例"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-initiate-an-approval-flow-with-attachments_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-initiate-an-approval-flow-with-attachments_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-08教程介绍了如何通过官方OA审批API和存储API实现发起带附件的审批流。

**说明**

* 本文档以企业内部应用为例，第三方企业应用实现流程类似。
* 本文档介绍仅调用服务端API实现审批附件的操作流程，不需要调用客户端JSAPI。

## **预期效果**

![[development-initiate-an-approval-flow-with-attachments_p500681.png]]

## **接入流程简介**

本文档展示了，创建一个企业内部应用，实现使用**官方**OA审批发起带附件的审批流程：

步骤一：登录[开发者后台](https://open-dev.dingtalk.com/#/)，点击**应用开发-企业内部开发**，创建[企业内部应用](/document/orgapp/create-orgapp)。

步骤二：单击**基础信息 > 应用信息**，获取应用AppKey和AppSecret。

步骤三：[添加接口调用权限](/document/orgapp/permission-application-and-basic-concepts)。单击“OA审批”，申请OA审批对应的权限。

步骤四：获取应用访问凭证[获取企业内部应用的accessToken](/document/orgapp/obtain-the-access_token-of-an-internal-app)。调用接口时，通过accessToken鉴权调用者身份。

步骤五：调用存储和OA审批相关API：

1. 调用服务端API-[获取审批钉盘空间信息](/document/orgapp/obtains-the-information-about-approval-nail-disk)接口，获取审批空间`spaceId`。
2. 调用服务端API-[获取文件上传信息](/document/orgapp/obtain-storage-upload-information)接口，获取审批空间文件上传信息并执行上传。
3. 调用服务端API-[提交文件](/document/orgapp/submit-documents)接口，完成文件上传。
4. 调用服务端API-[创建或更新审批表单模板](/document/orgapp/create-an-approval-form-template)接口，创建带附件的OA审批模板。
5. 调用服务端API-[发起审批实例](/document/orgapp/create-an-approval-instance)接口，获取审批实例`instanceId`。
6. 审批附件操作：

   1. 下载审批附件

      1. 调用服务端API-[授权下载审批钉盘文件](/document/orgapp/download-the-approval-nail-file)接口，进行审批钉盘文件的授权操作。
      2. 调用服务端API-[下载审批附件](/document/orgapp/download-an-approval-attachment)接口，获取文件的链接`downloadUri`实现下载。目前不支持第三方企业应用调用。
   2. 预览审批附件：

      1. 调用服务端API-[授权预览审批附件](/document/orgapp/preview-authorization-attachment-pop)接口，实现钉盘文件的预览操作。
      2. 调用客户端JSAPI-[预览钉盘文件](/document/orgapp/preview-nail-plate-file)接口，实现预览钉盘文件。

## 步骤一：创建企业内部应用

**说明**

如果已有企业内部应用，可直接使用已有应用，可忽略此步骤。

1. 登录[开发者后台](https://open-dev.dingtalk.com/#/)，创建[企业内部应用](/document/orgapp/create-orgapp)。

   * 应用类型：选择H5微应用。
   * 开发方式：选择企业自主开发。

     ![[development-initiate-an-approval-flow-with-attachments_p477411.png]]

## 步骤二：获取AppKey和AppSecret

获取应用AppKey和AppSecret信息。

![[development-initiate-an-approval-flow-with-attachments_p527110.png]]

## 步骤三：添加接口权限

[添加接口调用权限](/document/orgapp/permission-application-and-basic-concepts)。单击“OA审批”和“存储”，申请OA审批和存储对应的权限。

![[development-initiate-an-approval-flow-with-attachments_p527418.png]]

![[development-initiate-an-approval-flow-with-attachments_p527428.png]]

## 步骤四：获取应用访问凭证accessToken

**重要**

服务端API差异详情参见[新旧版规范服务端API区别](/document/orgapp/differences-between-server-apis-and-new-server-apis)。

* 服务端API接口SDK下载，详情参见[服务端SDK下载](/document/orgapp/download-the-server-side-sdk)。
* 新版服务端API接口SDK下载，详情参见[新版服务端SDK下载](/document/orgapp/sdk-download)。

以下接口均使用新版服务端API接口，SDK下载详情参见[新版服务端SDK下载](/document/orgapp/sdk-download)。

根据步骤二中的AppKey和AppSecret，获取应用访问凭[获取企业内部应用的accessToken](/document/orgapp/obtain-the-access_token-of-an-internal-app)。

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

## **步骤五：调用存储和OA审批相关API**

1. 调用服务端API-[获取审批钉盘空间信息](/document/orgapp/obtains-the-information-about-approval-nail-disk)接口，获取审批空间`spaceId`。

   ```java
   public class Test{
     public static com.aliyun.dingtalkworkflow_1_0.Client createClient() throws Exception {
           Config config = new Config();
           config.protocol = "https";
           config.regionId = "central";
           return new com.aliyun.dingtalkworkflow_1_0.Client(config);
       }
     @Test
     public void GetAttachmentSpace() throws Exception {
           com.aliyun.dingtalkworkflow_1_0.Client client = ProcessTest.createClient();
           com.aliyun.dingtalkworkflow_1_0.models.GetAttachmentSpaceHeaders getAttachmentSpaceHeaders = new com.aliyun.dingtalkworkflow_1_0.models.GetAttachmentSpaceHeaders();
           getAttachmentSpaceHeaders.xAcsDingtalkAccessToken = accessToken;
           com.aliyun.dingtalkworkflow_1_0.models.GetAttachmentSpaceRequest getAttachmentSpaceRequest = new com.aliyun.dingtalkworkflow_1_0.models.GetAttachmentSpaceRequest()
                   .setUserId("user001")
                   .setAgentId(2620xxxL);
           try {
               GetAttachmentSpaceResponse attachmentSpaceWithOptions = client.getAttachmentSpaceWithOptions(getAttachmentSpaceRequest, getAttachmentSpaceHeaders, new RuntimeOptions());
               System.out.println(JSON.toJSONString(attachmentSpaceWithOptions));
           } catch (TeaException err) {
               if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                   // err 中含有 code 和 message 属性，可帮助开发定位问题
   ```
2. 调用服务端API-[获取文件上传信息](/document/orgapp/obtain-storage-upload-information)接口，获取存储空间文件上传信息并执行上传。

   ```java
   public class Test{
     public static com.aliyun.dingtalkstorage_1_0.Client createClient() throws Exception {
           Config config = new Config();
           config.protocol = "https";
           config.regionId = "central";
           return new com.aliyun.dingtalkstorage_1_0.Client(config);
       }
     @Test
    public void GetFileUploadInfo() throws Exception {
           com.aliyun.dingtalkstorage_1_0.Client client = Test.createClient();
           GetFileUploadInfoHeaders getFileUploadInfoHeaders = new GetFileUploadInfoHeaders();
           getFileUploadInfoHeaders.xAcsDingtalkAccessToken = accessToken;
           GetFileUploadInfoRequest.GetFileUploadInfoRequestOptionPreCheckParam optionPreCheckParam = new GetFileUploadInfoRequest.GetFileUploadInfoRequestOptionPreCheckParam()
                   .setSize(512L)
                   .setParentId("0")
                   .setName("API总览1.xls");
           GetFileUploadInfoRequest.GetFileUploadInfoRequestOption option = new GetFileUploadInfoRequest.GetFileUploadInfoRequestOption()
                   .setStorageDriver("DINGTALK")
                   .setPreCheckParam(optionPreCheckParam)
                   .setPreferRegion("SHANGHAI");
           GetFileUploadInfoRequest getFileUploadInfoRequest = new GetFileUploadInfoRequest()
   ```
3. 调用服务端API-[提交文件](/document/orgapp/submit-documents)接口，完成文件上传。

   ```java
   public class Test{
     public static com.aliyun.dingtalkstorage_1_0.Client createClient() throws Exception {
           Config config = new Config();
           config.protocol = "https";
           config.regionId = "central";
           return new com.aliyun.dingtalkstorage_1_0.Client(config);
       }
     @Test
    public void commit() throws Exception {
           com.aliyun.dingtalkstorage_1_0.Client client = Test.createClient();
           com.aliyun.dingtalkstorage_1_0.models.CommitFileHeaders commitFileHeaders = new com.aliyun.dingtalkstorage_1_0.models.CommitFileHeaders();
           commitFileHeaders.xAcsDingtalkAccessToken = accessToken;
           com.aliyun.dingtalkstorage_1_0.models.CommitFileRequest.CommitFileRequestOptionAppProperties optionAppProperties0 = new com.aliyun.dingtalkstorage_1_0.models.CommitFileRequest.CommitFileRequestOptionAppProperties()
                   .setName("属性1")
                   .setValue("属性值1")
                   .setVisibility("PUBLIC");
           com.aliyun.dingtalkstorage_1_0.models.CommitFileRequest.CommitFileRequestOption option = new com.aliyun.dingtalkstorage_1_0.models.CommitFileRequest.CommitFileRequestOption()
                   .setSize(1024L)
                   .setConflictStrategy("AUTO_RENAME")
                   .setAppProperties(java.util.Arrays.asList(
                           optionAppProperties0
   ```
4. 调用服务端API-[创建或更新审批表单模板](/document/orgapp/create-an-approval-form-template)接口，创建带附件的OA审批模板，获取审批模板的processCode。

   **说明**

   如果已有带附件组件的审批模板，获取模板processCode，可参考[名词解释-processCode](/document/orgapp/workflow-overview)。

   ```java
   public class Test{
   public static com.aliyun.dingtalkworkflow_1_0.Client createClient() throws Exception {
           Config config = new Config();
           config.protocol = "https";
           config.regionId = "central";
           return new com.aliyun.dingtalkworkflow_1_0.Client(config);
       }
     @Test
     public void CreatForms() throws Exception {
           com.aliyun.dingtalkworkflow_1_0.Client client = Test.createClient();
           FormCreateHeaders formCreateHeaders = new FormCreateHeaders();
           formCreateHeaders.xAcsDingtalkAccessToken = accessToken;
           // 附件控件
           FormComponentProps formComponentProps = new FormComponentProps()
                   .setComponentId("DDAttachment-abcd")
                   .setLabel("附件");
           FormComponent formComponent = new FormComponent()
                   .setComponentType("DDAttachment")
                   .setProps(formComponentProps);
           FormCreateRequest formCreateRequest = new FormCreateRequest()
                   .setName("测试审批")
   ```
5. 调用服务端API-[发起审批实例](/document/orgapp/create-an-approval-instance)接口，获取审批实例`instanceId`。

   ```java
   public class Test{
   public static com.aliyun.dingtalkworkflow_1_0.Client createClient() throws Exception {
           Config config = new Config();
           config.protocol = "https";
           config.regionId = "central";
           return new com.aliyun.dingtalkworkflow_1_0.Client(config);
       }
     @Test
       public void processInstances() throws Exception {
           com.aliyun.dingtalkworkflow_1_0.Client client = ProcessTest.createClient();
           StartProcessInstanceHeaders startProcessInstanceHeaders = new StartProcessInstanceHeaders();
           startProcessInstanceHeaders.xAcsDingtalkAccessToken = accessToken;
           // 封装附件组件的值
           JSONObject attachmentJson = new JSONObject();
           attachmentJson.put("fileId", "提交文件接口返回的文件id");
           attachmentJson.put("fileName", "提交文件接口返回的name");
           attachmentJson.put("fileType", "提交文件接口返回的extension");
           attachmentJson.put("spaceId", "提交文件接口返回的spaceId");
           attachmentJson.put("fileSize", "提交文件接口返回的size");
           StartProcessInstanceRequest.StartProcessInstanceRequestFormComponentValues formComponentValues0 = new StartProcessInstanceRequest.StartProcessInstanceRequestFormComponentValues()
                   .setId("DDAttachment-abcd")
   ```
6. 审批附件操作：

   1. 下载审批附件：

      1. 调用服务端API-[授权下载审批钉盘文件](/document/orgapp/download-the-approval-nail-file)接口，进行审批钉盘文件的授权操作。

         ```java
          public void spaceAuthDownload() throws Exception {
                 com.aliyun.teaopenapi.models.Config config = new com.aliyun.teaopenapi.models.Config();
                 config.protocol = "https";
                 config.regionId = "central";
                 com.aliyun.dingtalkworkflow_1_0.Client client = new com.aliyun.dingtalkworkflow_1_0.Client(config);
                 com.aliyun.dingtalkworkflow_1_0.models.AddApproveDentryAuthHeaders addApproveDentryAuthHeaders = new com.aliyun.dingtalkworkflow_1_0.models.AddApproveDentryAuthHeaders();
                 addApproveDentryAuthHeaders.xAcsDingtalkAccessToken = "accessToken";
                 com.aliyun.dingtalkworkflow_1_0.models.AddApproveDentryAuthRequest.AddApproveDentryAuthRequestFileInfos fileInfos0 = new com.aliyun.dingtalkworkflow_1_0.models.AddApproveDentryAuthRequest.AddApproveDentryAuthRequestFileInfos()
                         .setFileId("49*****61")
                         .setSpaceId(47*****86L);
                 com.aliyun.dingtalkworkflow_1_0.models.AddApproveDentryAuthRequest addApproveDentryAuthRequest = new com.aliyun.dingtalkworkflow_1_0.models.AddApproveDentryAuthRequest()
                         .setUserId("manager7675")
                         .setFileInfos(java.util.Arrays.asList(
                                 fileInfos0
                         ));
                 try {
                     AddApproveDentryAuthResponse addApproveDentryAuthResponse = client.addApproveDentryAuthWithOptions(addApproveDentryAuthRequest, addApproveDentryAuthHeaders, new RuntimeOptions());
                     System.out.println(JSON.toJSONString(addApproveDentryAuthResponse.getBody()));
                 } catch (TeaException err) {
                     if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                         // err 中含有 code 和 message 属性，可帮助开发定位问题
         ```
      2. 调用服务端API-[下载审批附件](/document/orgapp/download-an-approval-attachment)接口，获取文件的链接`downloadUri`实现下载。目前不支持第三方企业应用调用。

         ```java
         public void processFileDownload() throws Exception {
                 com.aliyun.teaopenapi.models.Config config = new com.aliyun.teaopenapi.models.Config();
                 config.protocol = "https";
                 config.regionId = "central";
                 com.aliyun.dingtalkworkflow_1_0.Client client = new com.aliyun.dingtalkworkflow_1_0.Client(config);
                 com.aliyun.dingtalkworkflow_1_0.models.GrantProcessInstanceForDownloadFileHeaders grantProcessInstanceForDownloadFileHeaders = new com.aliyun.dingtalkworkflow_1_0.models.GrantProcessInstanceForDownloadFileHeaders();
                 grantProcessInstanceForDownloadFileHeaders.xAcsDingtalkAccessToken = "accessToken";
                 com.aliyun.dingtalkworkflow_1_0.models.GrantProcessInstanceForDownloadFileRequest grantProcessInstanceForDownloadFileRequest = new com.aliyun.dingtalkworkflow_1_0.models.GrantProcessInstanceForDownloadFileRequest()
                         .setProcessInstanceId("Ay9***************199")
                         .setFileId("68********11");
                 try {
                     GrantProcessInstanceForDownloadFileResponse grantProcessInstanceForDownloadFileResponse = client.grantProcessInstanceForDownloadFileWithOptions(grantProcessInstanceForDownloadFileRequest, grantProcessInstanceForDownloadFileHeaders, new RuntimeOptions());
                     System.out.println(JSON.toJSONString(grantProcessInstanceForDownloadFileResponse.getBody()));
                 } catch (TeaException err) {
                     if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                         // err 中含有 code 和 message 属性，可帮助开发定位问题
                         System.out.println(err.code);
                         System.out.println(err.message);
                     }
                 } catch (Exception _err) {
                     TeaException err = new TeaException(_err.getMessage(), _err);
         ```
   2. 预览审批附件：

      1. 调用服务端API-[授权预览审批附件](/document/orgapp/preview-authorization-attachment-pop)接口，实现钉盘文件的预览操作。

         ```java
          public void authPreview() throws Exception {
                 com.aliyun.teaopenapi.models.Config config = new com.aliyun.teaopenapi.models.Config();
                 config.protocol = "https";
                 config.regionId = "central";
                 com.aliyun.dingtalkworkflow_1_0.Client client = new com.aliyun.dingtalkworkflow_1_0.Client(config);
                 com.aliyun.dingtalkworkflow_1_0.models.GetSpaceWithDownloadAuthHeaders getSpaceWithDownloadAuthHeaders = new com.aliyun.dingtalkworkflow_1_0.models.GetSpaceWithDownloadAuthHeaders();
                 getSpaceWithDownloadAuthHeaders.xAcsDingtalkAccessToken = "accessToken";
                 com.aliyun.dingtalkworkflow_1_0.models.GetSpaceWithDownloadAuthRequest getSpaceWithDownloadAuthRequest = new com.aliyun.dingtalkworkflow_1_0.models.GetSpaceWithDownloadAuthRequest()
                         .setUserId("ma*****75")
                         .setAgentId(118****5L)
                         .setProcessInstanceId("yIYiVlR3R***********4433")
                         .setFileId("495******61");
                 try {
                     GetSpaceWithDownloadAuthResponse spaceWithDownloadAuthWithOptions = client.getSpaceWithDownloadAuthWithOptions(getSpaceWithDownloadAuthRequest, getSpaceWithDownloadAuthHeaders, new RuntimeOptions());
                     System.out.println(JSON.toJSONString(spaceWithDownloadAuthWithOptions.getBody()));
                 } catch (TeaException err) {
                     if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                         // err 中含有 code 和 message 属性，可帮助开发定位问题
                         System.out.println(err.code);
                         System.out.println(err.message);
                     }
         ```
      2. 调用客户端JSAPI-[预览钉盘文件](/document/orgapp/preview-nail-plate-file)接口，实现预览钉盘文件。可通过访问[JSAPI Explorer](https://open-dev.dingtalk.com/apiExplorer?spm=ding_open_doc.document.0.0.7dad15a7B5FCFQ#/jsapi?api=biz.cspace.preview)在线调试该接口。

         **说明**

         每一次预览审批附件前，都需要调用[授权预览审批附件](/document/orgapp/preview-authorization-attachment-pop)接口实现授权操作。

         ![[development-initiate-an-approval-flow-with-attachments_p499205.png]]