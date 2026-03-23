---
title: "家庭Feed同步旧版SDK"
source: "https://open.dingtalk.com/document/development/dingtalk-education-family-feed-synchronization"
category: "服务端API / 行业开放 / 新教育 / 家庭"
updated: 
tags:
  - dingtalk
  - 服务端API
---
![[development-dingtalk-education-family-feed-synchronization_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-dingtalk-education-family-feed-synchronization_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-23调用本接口，同步钉钉教育家庭Feed。

调用本接口，可同步钉钉教育家庭Feed，包括媒体类型、媒体链接、设置同步类型等。

## 权限

服务端API是以应用维度授权的，在调用接口前，确保已经为应用添加了接口权限。

|  |  |  |  |
| --- | --- | --- | --- |
| 应用类型 | 是否支持调用 | 权限申请方式 | API Explorer调试 |
| 企业内部应用 | 否 | — | — |
| 第三方企业应用 | 是 | 钉钉教育Feed数据权限包 | [调试](https://open-dev.dingtalk.com/apiExplorer#/?devType=isv&api=dingtalk.oapi.edu.feed.sync) |
| 第三方个人应用 | 否 | — | — |

## 基本信息

**请求方式**：POST

**请求地址**：`https://oapi.dingtalk.com/topapi/edu/feed/sync`

## Query参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| access\_token | String | 是 | Be3xxxx | 调用该接口的应用凭证，通过[获取第三方企业的access\_token](/document/development/obtain-isvapp-token)接口获取。 |

## Body参数

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| 名称 | 类型 | 是否必填 | 示例值 | 描述 |
| feed\_medias | IndustrySyncFeedMediaReq[] | 是 |  | 媒体list，最多可传入999。 |
| media\_type | Number | 否 | 1 | 媒体类型。   * **1**：图片 * **2**：视频 * **3**：文本 * **4**：直播 |
| media\_url | String | 是 | http://www.aaa.jpg | 媒体链接。 |
| thumbnail\_url | String | 否 | http://www.aaa.jpg | 媒体缩略图链接。 |
| media\_uid | String | 否 | 390898402 | 媒体用户的userId。 |
| fee\_type | Number | 是 | 1 | 同步类型。   * **1**：全量同步 * **2**：单个同步 |
| dept\_id | Number | 否 | 12398 | 部门或班级ID，可调用[获取部门列表](/document/development/obtains-the-department-node-list)接口获取dept\_id参数值。 |
| album\_id | String | 否 | al1342 | 媒体相册ID。 |
| send\_uid | String | 否 | 23428409328 | 媒体发送用户的userId。 |
| op\_userId | String | 否 | 2384082340 | 操作人的userId。 |
| send\_time | Number | 否 | 1605858971991 | 发送时间戳，单位毫秒。 |
| future | String | 否 | kindergarten | 拓展字段。 |

## 返回参数

|  |  |  |  |
| --- | --- | --- | --- |
| 名称 | 类型 | 示例值 | 描述 |
| success | Boolean | true | 请求是否成功。   * **true**：成功 * **false**：失败 |
| errcode | Number | 0 | 返回码。 |
| errmsg | String | ok | 返回码描述。 |

## 示例

**请求示例（HTTP）**

```http
POST https://oapi.dingtalk.com/topapi/edu/feed/sync?access_token=ACCESS_TOKEN
```

请求正文

```json
{
        "send_time":"1605858971991",
        "send_uid":"23428409328",
        "album_id":"al1342",
        "fee_type":"1",
        "feed_medias":{
                "media_type":"1",
                "thumbnail_url":"http://www.aaa.jpg",
                "media_url":"http://www.aaa.jpg"
        },
        "media_uid":"390898402",
        "dept_id":"12398",
        "op_userId":"2384082340"
}
```

**请求示例（JAVA SDK）**

```java
DingTalkClient client = new DefaultDingTalkClient("https://oapi.dingtalk.com/topapi/edu/feed/sync");
OapiEduFeedSyncRequest req = new OapiEduFeedSyncRequest();
List list2 = new ArrayList();
IndustrySyncFeedMediaReq obj3 = new IndustrySyncFeedMediaReq();
list2.add(obj3);
obj3.setMediaType(1L);
obj3.setMediaUrl("http://www.aaa.jpg");
obj3.setThumbnailUrl("http://www.aaa.jpg");
req.setFeedMedias(list2);
req.setMediaUid("390898402");
req.setFeeType(1L);
req.setDeptId(12398L);
req.setAlbumId("al1342");
req.setSendUid("23428409328");
req.setOpUserId("2384082340");
req.setSendTime(1605858971991L);
OapiEduFeedSyncResponse rsp = client.execute(req, access_token);
System.out.println(rsp.getBody());
```

**返回示例**

```json
{
        "errcode":0,
        "success":"true",
        "errmsg":"ok"
}
```