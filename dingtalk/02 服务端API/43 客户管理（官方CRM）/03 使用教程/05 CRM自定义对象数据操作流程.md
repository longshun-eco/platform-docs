---
title: "CRM自定义对象数据操作流程"
source: "https://open.dingtalk.com/document/development/crm-custom-object-data-operation-process"
category: "服务端API / 客户管理（官方CRM） / 使用教程"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-crm-custom-object-data-operation-process_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-crm-custom-object-data-operation-process_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-23本文档介绍了CRM自定义对象数据操作流程。

## 流程简介

本文档介绍了如何调用客户管理接口创建CRM自定义对象数据等流程。首先创建一个企业内部应用，再使用客户管理提供的API，实现获取自定义对象对象的元数据、创建CRM自定义对象数据、更新CRM自定义对象数据、删除CRM自定义对象数据、批量获取自定义对象数据、根据指定条件查询自定义对象数据流程。

步骤一：登录[开发者后台](https://open-dev.dingtalk.com/#/)，创建[企业内部应用](/document/orgapp/create-orgapp)。

步骤二：获取AppKey和AppSecret。

步骤三：[申请客户管理接口权限](/document/orgapp/apply-for-crm-api-permission)。搜索“CRM”，申请相应的权限。

步骤四：获取应用访问凭证[获取企业内部应用的accessToken](/document/orgapp/obtain-the-access_token-of-an-internal-app)。

步骤五：调用服务端自定义对象相关API。

1. 调用服务端API-[获取自定义对象的元数据](/document/orgapp/get-metadata-description-of-crm-custom-object)接口，获取客户管理自定义对象的元数据信息。
2. 调用服务端API-[创建CRM自定义对象数据](/document/orgapp/dingtalk-paas-master-create-custom-crm-object-data)接口，进行自定义对象数据的创建，获取自定义对象数据`instanceId`。
3. 根据自定义对象数据`instanceId`进行自定义对象数据管理操作。

   * 根据自定义对象数据`instanceId`，调用服务端API-[更新自定义对象数据](/document/orgapp/crm-master-data-opens-interface-for-updating-custom-object-data)接口，进行更新自定义对象数据。
   * 根据自定义对象数据`instanceId`，调用服务端API-[删除CRM自定义对象数据](/document/orgapp/delete-crm-custom-object-data)接口，进行删除自定义对象数据。
   * 根据自定义对象数据`instanceId`，调用服务端API-[按照ID列表批量获取CRM自定义表单数据](/document/orgapp/retrieves-custom-crm-forms-from-the-id-list)接口，进行批量获取自定义对象数据信息。
4. 调用服务端API-[根据指定条件查询自定义对象数据](/document/orgapp/retrieve-custom-crm-object-data)接口，查询符合指定条件的自定义对象数据。

## 步骤一：创建企业内部应用

**说明**

如果已有企业内部应用，可直接使用已有应用，可忽略此步骤。

1. 登录[开发者后台](https://open-dev.dingtalk.com/#/)，创建[企业内部应用](/document/orgapp/create-orgapp)。

   ![[development-crm-custom-object-data-operation-process_p477411.png]]
2. 填写应用的基本信息，然后单击**确定创建**。

   * 应用类型：选择**H5微应用**
   * 开发方式：选择**企业自主开发**

   ![[development-crm-custom-object-data-operation-process_p522024.png]]

## 步骤二：获取AppKey和AppSecret

获取AppKey和AppSecret。

![[development-crm-custom-object-data-operation-process_p477413.png]]

## 步骤三：添加接口权限

[申请客户管理接口权限](/document/orgapp/apply-for-crm-api-permission)。搜索“CRM”，申请相应的权限。

![[development-crm-custom-object-data-operation-process_p499403.png]]

## 步骤四：获取应用访问凭证accessToken

根据步骤二中的AppKey和AppSecret，获取应用访问凭证[获取企业内部应用的accessToken](/document/orgapp/obtain-the-access_token-of-an-internal-app)。

**说明**

服务端API差异详情参见[新旧版规范服务端API区别](/document/orgapp/differences-between-server-apis-and-new-server-apis)。

* 服务端API接口SDK下载，详情参见[服务端SDK下载](/document/orgapp/download-the-server-side-sdk)。
* 新版服务端API接口SDK下载，详情参见[新版服务端SDK下载](/document/orgapp/sdk-download)。

以下接口均使用新版服务端API接口，SDK下载详情参见[新版服务端SDK下载](/document/orgapp/sdk-download)。

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

## 步骤五：调用服务端自定义对象相关API

1. 调用服务端API-[获取自定义对象的元数据](/document/orgapp/get-metadata-description-of-crm-custom-object)接口，获取客户管理自定义对象的元数据信息。

   **说明**

   本接口均使用服务端API接口，SDK下载详情参见[服务端SDK下载](/document/orgapp/download-the-server-side-sdk)。

   ```java
   public void getCustomizedObjectMeta() throws Exception {
           DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/topapi/crm/objectmeta/describe");
           OapiCrmObjectmetaDescribeRequest req = new OapiCrmObjectmetaDescribeRequest();
           req.setName("PROC-EF1xxxx");
           OapiCrmObjectmetaDescribeResponse rsp = client.execute(req, access_token);
           System.out.println(rsp.getBody());
   }
   ```
2. 调用服务端API-[创建CRM自定义对象数据](/document/orgapp/dingtalk-paas-master-create-custom-crm-object-data)接口，进行自定义对象数据的创建，获取自定义对象数据`instanceId`。

   **说明**

   本接口均使用服务端API接口，SDK下载详情参见[服务端SDK下载](/document/orgapp/download-the-server-side-sdk)。

   ```java
   public void createCustomizedData() throws Exception {
           DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/topapi/crm/objectdata/customobject/create");
           OapiCrmObjectdataCustomobjectCreateRequest req = new OapiCrmObjectdataCustomobjectCreateRequest();
           ObjectDataInstanceVo objectDataInstanceVo = new ObjectDataInstanceVo();
           objectDataInstanceVo.setCreatorUserid("user01");
           objectDataInstanceVo.setData("{\"TextField-xxxxxx\":\"李xx\"}");
           objectDataInstanceVo.setExtendData("{\"field_1\":\"CRM\"}");
           DataPermissionVo dataPermissionVo = new DataPermissionVo();
           dataPermissionVo.setParticipantUserids(Arrays.asList("user01", "user02"));
           objectDataInstanceVo.setPermission(dataPermissionVo);
           objectDataInstanceVo.setFormCode("PROC-A1xxxx");
           req.setInstance(objectDataInstanceVo);
           OapiCrmObjectdataCustomobjectCreateResponse rsp = client.execute(req, access_token);
           System.out.println(rsp.getBody());
   }
   ```
3. 根据自定义对象数据`instanceId`进行自定义对象数据管理操作。

   * 根据自定义对象数据instanceId，调用服务端API-[更新自定义对象数据](/document/orgapp/crm-master-data-opens-interface-for-updating-custom-object-data)接口，进行更新自定义对象数据。

     **说明**

     本接口均使用服务端API接口，SDK下载详情参见[服务端SDK下载](/document/orgapp/download-the-server-side-sdk)。

     ```java
      public void updateCustomizedData() throws Exception {
             DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/topapi/crm/objectdata/customobject/update");
             OapiCrmObjectdataCustomobjectUpdateRequest req = new OapiCrmObjectdataCustomobjectUpdateRequest();
             ObjectDataInstanceVo objectDataInstanceVo = new ObjectDataInstanceVo();
             DataPermissionVo dataPermissionVo = new DataPermissionVo();
             dataPermissionVo.setParticipantUserids(Arrays.asList("user01", "user02"));
             objectDataInstanceVo.setExtendData("{\"field_1\":\"CRM\"}");
             objectDataInstanceVo.setPermission(dataPermissionVo);
             objectDataInstanceVo.setInstanceId("INST_XX");
             objectDataInstanceVo.setFormCode("PROC-EFxxxx");
             objectDataInstanceVo.setModifierUserid("user01");
             objectDataInstanceVo.setModifierNick("张xx");
             req.setInstance(objectDataInstanceVo);
             OapiCrmObjectdataCustomobjectUpdateResponse rsp = client.execute(req, access_token);
             System.out.println(rsp.getBody());
     }
     ```
   * 根据自定义对象数据`instanceId`，调用服务端API-[删除CRM自定义对象数据](/document/orgapp/delete-crm-custom-object-data)接口，进行删除自定义对象数据。

     **说明**

     本接口均使用新服务端API接口，SDK下载详情参见[新版服务端SDK下载](/document/orgapp/sdk-download)。

     ```java
      public void deleteCustomizedData() throws Exception {
             Config config = new Config();
             config.protocol = "https";
             config.regionId = "central";
             com.aliyun.dingtalkcrm_1_0.Client client = new com.aliyun.dingtalkcrm_1_0.Client(config);
             com.aliyun.dingtalkcrm_1_0.models.DeleteCrmCustomObjectDataHeaders deleteCrmCustomObjectDataHeaders = new com.aliyun.dingtalkcrm_1_0.models.DeleteCrmCustomObjectDataHeaders();
             deleteCrmCustomObjectDataHeaders.xAcsDingtalkAccessToken = "";
             com.aliyun.dingtalkcrm_1_0.models.DeleteCrmCustomObjectDataRequest deleteCrmCustomObjectDataRequest = new com.aliyun.dingtalkcrm_1_0.models.DeleteCrmCustomObjectDataRequest()
                     .setFormCode("PROC-EFxxxx");
             try {
                 DeleteCrmCustomObjectDataResponse deleteCrmCustomObjectDataResponse = client.deleteCrmCustomObjectDataWithOptions("INST_XX", deleteCrmCustomObjectDataRequest, deleteCrmCustomObjectDataHeaders, new RuntimeOptions());
                 System.out.println(JSON.toJSONString(deleteCrmCustomObjectDataResponse.getBody()));
             } catch (TeaException err) {
                 if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                     // err 中含有 code 和 message 属性，可帮助开发定位问题
                     System.out.println(err.code);
                     System.out.println(err.message);
                 }
             } catch (Exception _err) {
                 TeaException err = new TeaException(_err.getMessage(), _err);
                 if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
     ```
   * 根据自定义对象数据`instanceId`，调用服务端API-[按照ID列表批量获取CRM自定义表单数据](/document/orgapp/retrieves-custom-crm-forms-from-the-id-list)接口，进行批量获取自定义对象数据信息。

     **说明**

     本接口均使用服务端API接口，SDK下载详情参见[服务端SDK下载](/document/orgapp/download-the-server-side-sdk)。

     ```java
      public void getCustomizedDatasByInstanceIds() throws Exception {
             Config config = new Config();
             config.protocol = "https";
             config.regionId = "central";
             com.aliyun.dingtalkcrm_1_0.Client client = new com.aliyun.dingtalkcrm_1_0.Client(config);
             DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/topapi/crm/objectdata/list");
             OapiCrmObjectdataListRequest req = new OapiCrmObjectdataListRequest();
             req.setCurrentOperatorUserid("user01");
             req.setDataIdList("INST_XX1,INST_XX2");
             req.setName("PROC-EFxxxx");
             OapiCrmObjectdataListResponse rsp = client.execute(req, access_token);
             System.out.println(rsp.getBody());
      }
     ```
4. 调用服务端API-[根据指定条件查询自定义对象数据](/document/orgapp/retrieve-custom-crm-object-data)接口，查询符合指定条件的自定义对象数据。

   **说明**

   本接口均使用服务端API接口，SDK下载详情参见[服务端SDK下载](/document/orgapp/download-the-server-side-sdk)。

   ```java
    public void queryCustomizedDatas() throws Exception {
           Config config = new Config();
           config.protocol = "https";
           config.regionId = "central";
           com.aliyun.dingtalkcrm_1_0.Client client = new com.aliyun.dingtalkcrm_1_0.Client(config);
           QueryAllCustomerHeaders queryAllCustomerHeaders = new QueryAllCustomerHeaders();
           queryAllCustomerHeaders.xAcsDingtalkAccessToken = "";
           QueryAllCustomerRequest queryAllCustomerRequest = new QueryAllCustomerRequest()
                   .setOperatorUserId("ding_userid")
                   .setMaxResults(100L)
                   .setNextToken("")
                   .setObjectType("crm_customer");
           try {
               QueryAllCustomerResponse queryAllCustomerResponse = client.queryAllCustomerWithOptions(queryAllCustomerRequest, queryAllCustomerHeaders, new RuntimeOptions());
               System.out.println(JSON.toJSONString(queryAllCustomerResponse.getBody()));
           } catch (TeaException err) {
               if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                   // err 中含有 code 和 message 属性，可帮助开发定位问题
                   System.out.println(err.code);
                   System.out.println(err.message);
               }
   ```