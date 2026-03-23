---
title: "CRM联系人数据操作流程"
source: "https://open.dingtalk.com/document/development/crm-contact-data-operation-process"
category: "服务端API / 客户管理（官方CRM） / 使用教程"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-crm-contact-data-operation-process_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-crm-contact-data-operation-process_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-23本文档介绍了CRM联系人数据操作流程。

## 流程简介

本文档介绍了如何调用客户管理接口创建CRM联系人数据等流程。首先创建一个企业内部应用，再使用客户管理提供的API，实现获取联系人对象的元数据、创建CRM联系人数据、更新CRM联系人数据、删除CRM联系人数据、批量获取联系人数据流程。

步骤一：登录[开发者后台](https://open-dev.dingtalk.com/#/)，创建[企业内部应用](/document/orgapp/create-orgapp)。

步骤二：获取AppKey和AppSecret。

步骤三：[申请客户管理接口权限](/document/orgapp/apply-for-crm-api-permission)。搜索“CRM”，申请相应的权限。

步骤四：获取应用访问凭证[获取企业内部应用的accessToken](/document/orgapp/obtain-the-access_token-of-an-internal-app)。

步骤五：调用服务端联系人相关API。

1. 调用服务端API-[获取联系人的元数据](/document/orgapp/gets-the-metadata-description-of-a-crm-contact-object)接口，获取客户管理联系人元数据信息。
2. 调用服务端API-[批量新增联系人数据](/document/orgapp/add-contact-data-in-batches)接口，进行联系人数据的创建，获取联系人数据`instanceId`（部分接口可能定义为relationId或data\_id，含义相同）。
3. 根据联系人数据`instanceId`进行联系人数据管理操作。

   * 根据联系人数据`instanceId`，调用服务端API-[批量修改联系人数据](/document/orgapp/modify-contact-data-in-batches)接口，进行更新联系人数据。
   * 根据联系人数据`instanceId`，调用服务端API-[删除联系人数据](/document/orgapp/delete-crm-contact)接口，进行删除联系人数据。
   * 根据联系人数据`instanceId`，调用服务端API-[按照ID列表批量获取联系人数据](/document/orgapp/retrieves-contact-data-in-batches-based-on-the-id-list)接口，进行批量获取联系人数据信息。
4. 调用服务端API-[根据指定条件查询联系人数据](/document/orgapp/dingtalk-the-contact-data-query-api)接口，查询符合指定条件的联系人数据。

## 步骤一：创建企业内部应用

**说明**

如果已有企业内部应用，可直接使用已有应用，可忽略此步骤。

1. 登录[开发者后台](https://open-dev.dingtalk.com/#/)，创建[企业内部应用](/document/orgapp/create-orgapp)。

   ![[development-crm-contact-data-operation-process_p477411.png]]
2. 填写应用的基本信息，然后单击**确定创建**。

   * 应用类型：选择**H5微应用**
   * 开发方式：选择**企业自主开发**

   ![[development-crm-contact-data-operation-process_p522020.png]]

## 步骤二：获取AppKey和AppSecret

获取AppKey和AppSecret。

![[development-crm-contact-data-operation-process_p477413.png]]

## 步骤三：添加接口权限

[申请客户管理接口权限](/document/orgapp/apply-for-crm-api-permission)。搜索“CRM”，申请相应的权限。

![[development-crm-contact-data-operation-process_p499403.png]]

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

## 步骤五：调用服务端联系人相关API

1. 调用服务端API-[获取联系人的元数据](/document/orgapp/gets-the-metadata-description-of-a-crm-contact-object)接口，获取客户管理联系人元数据信息。

   **说明**

   本接口使用服务端API接口，SDK下载详情参见[服务端SDK下载](/document/orgapp/download-the-server-side-sdk)。

   ```java
   public void getContactObjectMeta() throws Exception {
           DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/topapi/crm/objectmeta/contact/describe");
           OapiCrmObjectmetaContactDescribeRequest req = new OapiCrmObjectmetaContactDescribeRequest();
           OapiCrmObjectmetaContactDescribeResponse rsp = client.execute(req, accessToken);
           System.out.println(rsp.getBody());
   }
   ```
2. 调用服务端API-[批量新增联系人数据](/document/orgapp/add-contact-data-in-batches)接口，进行联系人数据的创建，获取联系人数据`instanceId`（部分接口可能定义为relationId或data\_id，含义相同）。

   **说明**

   本接口使用新服务端API接口，SDK下载详情参见[新版服务端SDK下载](/document/orgapp/sdk-download)。

   ```java
   public void batchAddContacts() throws Exception {
           Config config = new Config();
           config.protocol = "https";
           config.regionId = "central";
           com.aliyun.dingtalkcrm_1_0.Client client = new com.aliyun.dingtalkcrm_1_0.Client(config);
           BatchAddContactsHeaders batchAddContactsHeaders = new BatchAddContactsHeaders();
           batchAddContactsHeaders.xAcsDingtalkAccessToken = "";
           java.util.Map relationList0BizExtMap = TeaConverter.buildMap(
                   new TeaPair("key", "{}")
           );
           BatchAddContactsRequest.BatchAddContactsRequestRelationListBizDataList relationList0BizDataList0 = new BatchAddContactsRequest.BatchAddContactsRequestRelationListBizDataList()
                   .setKey("contact_name")
                   .setValue("XX有限公司");
           BatchAddContactsRequest.BatchAddContactsRequestRelationListBizDataList relationList0BizDataList1 = new BatchAddContactsRequest.BatchAddContactsRequestRelationListBizDataList()
                   .setKey("contact_related_customer")
                   .setValue("[\"XX公司\"]")
                   .setExtendValue("{\"list\":[{\"instanceId\":\"customerInstanceId\"}]}");
           BatchAddContactsRequest.BatchAddContactsRequestRelationListBizDataList relationList0BizDataList2 = new BatchAddContactsRequest.BatchAddContactsRequestRelationListBizDataList()
                   .setKey("contact_phone")
                   .setValue("185xxxxxxxx");
           BatchAddContactsRequest.BatchAddContactsRequestRelationList relationList0 = new BatchAddContactsRequest.BatchAddContactsRequestRelationList()
   ```
3. 根据联系人数据`instanceId`进行联系人数据管理操作。

   * 根据联系人数据instanceId，调用服务端API-[批量修改联系人数据](/document/orgapp/modify-contact-data-in-batches)接口，进行更新联系人数据。

     **说明**

     本接口使用新服务端API接口，SDK下载详情参见[新版服务端SDK下载](/document/orgapp/sdk-download)。

     ```java
      public void  batchUpdateContacts() throws Exception {
             Config config = new Config();
             config.protocol = "https";
             config.regionId = "central";
             com.aliyun.dingtalkcrm_1_0.Client client = new com.aliyun.dingtalkcrm_1_0.Client(config);
             BatchUpdateContactsHeaders batchUpdateContactsHeaders = new BatchUpdateContactsHeaders();
             batchUpdateContactsHeaders.xAcsDingtalkAccessToken = "";
             java.util.Map relationList0BizExtMap = TeaConverter.buildMap(
                     new TeaPair("key", "{}")
             );
             BatchUpdateContactsRequest.BatchUpdateContactsRequestRelationListBizDataList relationList0BizDataList0 = new BatchUpdateContactsRequest.BatchUpdateContactsRequestRelationListBizDataList()
                     .setKey("TextField_71U51A")
                     .setValue("XX有限公司")
                     .setExtendValue("{}");
             BatchUpdateContactsRequest.BatchUpdateContactsRequestRelationList relationList0 = new BatchUpdateContactsRequest.BatchUpdateContactsRequestRelationList()
                     .setBizDataList(java.util.Arrays.asList(
                             relationList0BizDataList0
                     ))
                     .setBizExtMap(relationList0BizExtMap)
                     .setRelationId("fasdg8i814-0afsd");
             BatchUpdateContactsRequest batchUpdateContactsRequest = new BatchUpdateContactsRequest()
     ```
   * 根据联系人数据`instanceId`，调用服务端API-[删除联系人数据](/document/orgapp/delete-crm-contact)接口，进行删除联系人数据。

     **说明**

     本接口使用服务端API接口，SDK下载详情参见[服务端SDK下载](/document/orgapp/download-the-server-side-sdk)。

     ```java
      public void deleteContact() throws Exception {
             DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/topapi/crm/objectdata/contact/delete");
             OapiCrmObjectdataContactDeleteRequest req = new OapiCrmObjectdataContactDeleteRequest();
             req.setOperatorUserid("user01");
             req.setDataId("INST_XX");
             OapiCrmObjectdataContactDeleteResponse rsp = client.execute(req, access_token);
             System.out.println(rsp.getBody());
      }
     ```
   * 根据联系人数据`instanceId`，调用服务端API-[按照ID列表批量获取联系人数据](/document/orgapp/retrieves-contact-data-in-batches-based-on-the-id-list)接口，进行批量获取联系人数据信息。

     **说明**

     本接口使用服务端API接口，SDK下载详情参见[服务端SDK下载](/document/orgapp/download-the-server-side-sdk)。

     ```java
      public void getContactsByInstanceIds() throws Exception {
             DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/topapi/crm/objectdata/contact/list");
             OapiCrmObjectdataContactListRequest req = new OapiCrmObjectdataContactListRequest();
             req.setCurrentOperatorUserid("manager1");
             req.setDataIdList("nst_Id1, inst_Id2");
             OapiCrmObjectdataContactListResponse rsp = client.execute(req, access_token);
             System.out.println(rsp.getBody());
      }
     ```
4. 调用服务端API-[根据指定条件查询联系人数据](/document/orgapp/dingtalk-the-contact-data-query-api)接口，查询符合指定条件的联系人数据。

   **说明**

   本接口使用服务端API接口，SDK下载详情参见[服务端SDK下载](/document/orgapp/download-the-server-side-sdk)。

   ```java
   public void queryContacts() throws Exception {
           DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/topapi/crm/objectdata/contact/query");
           OapiCrmObjectdataContactQueryRequest req = new OapiCrmObjectdataContactQueryRequest();
           req.setCurrentOperatorUserid("user01");
           req.setCursor("0");
           req.setPageSize(100L);
           req.setProviderCorpid("dingxxx");
           req.setQueryDsl("{\"queryGroupList\":[{\"logicType\":\"AND\",\"queryObjectList\":[{\"fieldId\":\"contact_phone\",\"filterType\":\"EQ\",\"value\":\"18000****000\"},{\"fieldId\":\"contact_related_customer\",\"filterType\":\"EQ\",\"value\":\"INST-XXX\"}]}]}");
           OapiCrmObjectdataContactQueryResponse rsp = client.execute(req, access_token);
           System.out.println(rsp.getBody());
   }
   ```