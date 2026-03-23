---
title: "SaaS应用开发指南"
source: "https://docs.aliwork.com/docs/yida_support/_9/ch41p3rm3may1smg/chrmgzrsthf55vp9"
category: "用戶手冊 / 酷应用 / 酷SaaS工厂"
updated: 
tags:
  - yida
  - 用戶手冊
---
[📎627钉钉（宜搭）酷SaaS工厂应用开发指南大纲.pdf](https://www.yuque.com/attachments/yuque/0/2023/pdf/5376772/1687837298944-cab5ea65-83a2-4220-9ad2-21b6831c320e.pdf)

## 1. 低代码开发SaaS应用全链路流程说明

参考![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_O1CN01nxYKcl24UxehoQlC8_!!6000000007395-2-tps-192-192.png]][合作全流程指引 - 开放平台](https://open.dingtalk.com/document/operation-specification/isv-cooperation-guide?spm=a2q3v.21449185.0.0.7e676febWCbVi1)

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673930331856-7b6003f4-443f-4f70-b214-7dcc2f14845d.png]]

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673930294251-18495078-8c03-430b-8758-8574cb3ad55a.png]]

### 1.1 前置准备

1. 申请钉钉产品服务商资质[](https://open.dingtalk.com/document/isvapp/become-an-application-service-provider)
2. 了解并知悉[钉钉开放平台ISV帮助中心](https://alidocs.dingtalk.com/i/p/KrwmPQ5g4OEAG79n/docs/3KLw95QMzkb8gGOpYEk78AjrymPeEN2q?dontjump=true)的全链路内容
3. SaaS应用必须具备酷应用形态，如何酷化可参考[低代码构建钉钉酷应用开发设计指南](https://alidocs.dingtalk.com/i/p/Y7kmbokZp3pgGLq2/docs/7Y36k14mK9AV35vAPyg185NqapjblR2D)

### 1.2 如何进入SaaS研发工作台

当前组织具备[产品方案商](https://open.dingtalk.com/document/operation-specification/isv-cooperation-guide?spm=a2q3v.21449185.0.0.7e676febWCbVi1)身份认证时，登录宜搭，可在顶部菜单看到"进入SaaS研发工作台"的入口，直接访问。

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673931301424-f2aff83a-62a2-4dc0-90f3-83021c3e620f.png]]

进入SaaS应用工作台，您可以创建SaaS应用。

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673931313546-f1aa721d-14e1-43d7-a666-637f6fee9c7d.png]]

### 1.3 aPaaS底座功能支持范围

钉钉SaaS工厂研发工作台的能力和宜搭现有交互模式基本保持一致，本期发布的版本将会具备以下核心功能点**：**

- 平台功能：

- 表单（数据联动、自定义页面（页面js）、关联列表、二维码、流水号等）
- 流程（消息通知、待办等）
- 报表（元数据、数据集）
- 公式&业务规则
- 权限
- 集成自动化（一方、三方连接器、定时触发等）
- 消息通知&待办
- 酷应用化
- 打印
- 页面js数据源的openAPI
- 门户
- 数据卡片搭建（主应用不支持数据卡片投放>数据播报配置 但支持子应用个性化定制数据播报能力）
- ...等

特殊说明：自定义连接器、数据准备、DataV大屏、自定义组件等扩展增强功能，暂不支持，后续将会持续迭代。

## 2. 主应用设计

在完成前置准备工作后，您可以研发SaaS应用，如果您在现有其他宜搭组织下已经有完备的解决方案，希望直接切换成SaaS模式，可联系宜搭产研[申请应用迁移至SaaS环境](https://www.aliwork.com/o/saasApp_transfer)。

1. 您可以基于SaaS研发工作台并且根据目前平台提供的能力，按照业务诉求设计您的应用，如设计：

   1. 表单
   2. 流程
   3. 报表
   4. 门户
   5. 数据卡片搭建（主应用不支持数据卡片投放>数据播报配置 但支持子应用个性化定制数据播报能力）
   6. 集成自动化
   7. 酷应用
   8. ...

目前以上功能开发流程和宜搭企业自建应用开发功能保持一致，如有问题，请查看![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_TB1Ctzd3VP7gK0jSZFjXXc5aXXa-152-152.png]][找不到页面 | 钉钉宜搭·帮助中心](https://docs.aliwork.com/docs/yida_support/ytzzua)

2. 如果您的SaaS品有相关业务底表数据且希望用户在订阅SaaS应用后，能看到相关示例数据，请录入"基础数据"并统一维护至一个目录文件夹内，文件命名"**基础业务数据**"（示例如下图）

   - 届时该文件夹的**各普通表单**TOP100的数据将会随着客户订阅应用时加载到对应的组织应用内，目前仅支持一级目录携带数据，暂不支持多级目录。

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673931688744-a50f6f68-8eb0-4f01-8b45-3c9f61fb0ff2.png]]

## 3. 酷应用设计

基于SaaS研发工作台，您可以在应用层：卡片管理/集成自动化流 内 配置酷应用的卡片样式及卡片的发送及更新逻辑。具体设计可参考如下文档：

[](https://docs.aliwork.com/docs/yida_support/ub4y1n/tspkdk/pqnynb)

[](https://docs.aliwork.com/docs/yida_support/ub4y1n/tspkdk/fq0oar)

## 4. 应用发布

1. 主应用和酷应用都开发完毕后，您可以进入"发布&上架"界面，创建一个新的版本，用于SaaS应用的功能测试，测试完毕后申请上架。

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673756688412-efcc865d-d552-4914-a537-31f4842a883f.png]]

2. 点击新建版本，填写SaaS应用的版本信息，包括版本号、版本描述内容。

   1. 版本号不可修改
   2. 版本创建后，您可以点击"描述设置"修改版本描述

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673932094724-dec56ef0-b8f8-4243-825d-908990dcbefc.png]]

### 4.1 应用版本管理

- 应用功能发生变化之后，您可以随时创建一个新的版本，默认版本状态为"未发布"状态。可以点击发布，发布该版本。

- ⚠️未来用户在应用市场或自有渠道购买SaaS应用时，默认下单购买的版本为当前主应用已发布的最新版本，未发布的版本用户无法购买。

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673932137804-a2d01c85-73b0-4394-a653-39b4f69bbab2.png]]

### 4.2 应用申请上架-关联第三方应用

#### step1 关联第三方应用

| **SaaS研发工作台** | **钉钉开放平台>企业第三方应用** |
| --- | --- |
|
![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673932549849-96cb84e9-5815-4aa0-84e7-2b4267ad276b.png]]

1. 创建完至少一个应用版本后，可在 上架到钉钉应用中心内 提交上架申请
2. 选择在开放平台注册的第三方应用，在此关联选择即可。

   1. ⚠️ 一旦关联无法修改，请确认清楚后再进行绑定，如果关联错误，请联系宜搭官方。

 |

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673932555002-c9405a16-b3e0-444d-99d2-89693ee8cee9.png]]

1. 在钉钉开放平台内 > 企业第三方应用 类目下 创建H5微应用，填写应用基础信息
2. 生成应用凭证

   1. ⚠️ 凭证里的字段信息涉及隐私请妥善保管

 |

#### step2 填写SaaS应用开发信息

复制SaaS应用地址，进行应用信息配置

| **SaaS研发工作台** | **钉钉开放平台>企业第三方应用** |
| --- | --- |
|
![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673932648303-fca0354b-0a58-409e-bb31-ff02eb556c9e.png]]

1. 完成步骤1后，点击"复制"，将上述链接复制到开放平台，如右图

 |

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673932652816-f4801a08-fd3e-46d2-afa2-a8aada1aa7ab.png]]

1. 在钉钉开放平台内 > 企业第三方应用 选择注册的三方应用，点击"开发管理"，填写：

   1. 服务器出口IP：填写127.0.0.1
   2. 应用首页地址/PC端首页地址：直接粘贴链接即可（请务必填写左图生成的"复制"链接！！非应用URL链接）

 |

#### step3 检查SaaS应用配置项

##### （1）确认应用开发信息

1. 在钉钉开放平台内 > 企业第三方应用 选择注册的三方应用，如上图确认功能配置项是否均已完成，遗漏的需要继续配置。

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1727314165322-1523aaa4-d245-420e-ae1e-b0e38e93af1c.png]]

##### （2）权限管理配置

为保障SaaS品的数据安全，应用在开通时需要向用户确认授权信息，因此需要ISV自行配置需要授权的权限点。

1. 选择"权限管理"菜单，标准SaaS品均需要勾选以下权限信息，勾选后点击"批量申请"。

| **权限分类** | **权限点** |
| --- | --- |
| 卡片 | 互动卡片实例写权限 |
| 个人权限 | 通讯录个人信息读权限 |
| 通讯录管理 | 通讯录部门信息读权限 通讯录部门成员读权限 查询行业通讯录信息权限 成员信息读权限 |
| 待办任务 | 待办应用中待办写权限 待办应用中待办读权限 |
| 应用授权 | 调用ISV专有API时需要具备的权限 |
| 身份验证 | 企业微应用后台免登接口的访问权限 |
| 场景群 | chat相关接口的管理权限 chat相关接口的读取权限 |
| 宜搭 | **全部勾选** |
| 机器人 | 企业内机器人发送消息权限 |
| 存储 | 企业存储空间读权限 企业存储文件写权限 企业存储文件读权限 |

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1675337334809-e4cf364e-a678-432a-a0c7-2d0a67ed2999.png]]

（图1 权限配置界面）

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1675338324639-e944384b-0a68-4ec9-92e3-e63af33eee3b.png]]

（图2 授予权限透出说明界面）

2. 如果当前您搭建的SaaS品在"集成自动化>连接器节点"使用了"钉钉官方"连接器，请联系宜搭同学，确认需要勾选一方连接器的权限。

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1675338025562-77d5b76c-e92d-4cd8-b70d-b503ab4cb4ae.png]]

部分连接器与权限的映射如下

| **连接器** | **对应的权限分类** | **对应的权限点** |
| --- | --- | --- |
|
![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1675412937358-a3c9a9af-f535-4f77-b6f0-b7cf35cc1914.png]]

 | 智能会议室 | 视频会议应用会议写权限 |
|

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1675412952359-1285fbc0-a80a-4e82-9cc6-a605f898ef4c.png]]

 | 项目管理 | 项目应用任务写权限 |

#### step4 自助申请跳过安全自检

1. 应用跳过自检，需要设置"事件与回调"，如下图：

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1687836942158-8e3a3630-ea1c-44fa-9e86-bb5852a69db9.png]]

**step1**：加密Aes_key，通过下列的**decrypt**方法对宜搭的**systemToken**进行加密后设置

```java
private static final char[] HEX_ARRAY = "0123456789abcdef".toCharArray();public static String bytesToHex(byte[] bytes) {        char[] hexChars = new char[bytes.length * 2];        for (int i = 0; i < bytes.length; i++) {            int v = bytes[i] & 0xFF;            hexChars[i * 2] = HEX_ARRAY[v >>> 4];            hexChars[i * 2 + 1] = HEX_ARRAY[v & 0x0F];        }        return new String(hexChars);    }private static String decrypt(String input) throws NoSuchAlgorithmException {        MessageDigest digest = MessageDigest.getInstance("SHA-256");        byte[] hash = digest.digest(input.getBytes(StandardCharsets.UTF_8));        // 将散列码转换成43位加密串        return bytesToHex(hash).substring(0, 43);}
```

宜搭的systemToken在宜搭应用设置-部署运维中获取

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1687831981832-9a5a5a1c-3eb4-4800-9795-13fb9af8be13.png]]

**step2**：签名Token，即为上面的宜搭的systemToken

**step3**：回调请求地址（https://www.aliwork.com/saasAppCallback/{appKey}） 其中appKey是宜搭应用的，如"APP_XXX"的应用编码

2. 填写应用自检《安全审核》相关内容，安全准入评估参考[📎宜搭酷SaaS安全准入指南-ISV .pdf](https://www.yuque.com/attachments/yuque/0/2023/pdf/5376772/1690855075267-02eb05df-a8c0-44ff-9454-425db6ab833c.pdf)

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1690854697695-c3796179-7bc9-41d5-9cb4-86ec66c4a763.png]]

### 4.3 体验组织管理

体验组织管理用于ISV自测 已发布/未发布状态下 主应用/酷应用的功能完备性，自测通过后再申请上架到钉钉应用中心和酷应用市场。

1. 选择对应的SaaS应用版本，点击"体验组织管理"，选择体验组织，如果无，可点击["创建"](https://open.dingtalk.com/document/isv/application-development-process-of-third-party-enterprises)，前往开放平台进行创建体验组织。

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673933469943-a1f5a53e-3be8-40b0-b908-23e4401e515c.png]]

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673933681568-382effb4-ad1a-431e-9ece-941485e8a752.png]]

2. 体验组织创建完毕后，可将需要测试的应用版本关联授权到该组织即可，授权成功后，可在该体验组织的工作台>未分组 下查看该应用。

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673933475847-193b02df-c4c2-4502-93c6-5bdcd179150d.png]]

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673933741441-43454b8a-d35b-473d-9aa8-4decb6fa18bf.png]]

#### 4.3.1 体验测试主应用

1. 通过工作台访问该应用后，当体验测试组织人非"通讯录的管理员"或"应用主管理员"时，可联系组织管理员或应用管理员添加进入应用后台的管理权限。

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673933844267-1f0db852-94b2-4d35-836b-9e7ca1c9684e.png]]

2. 拥有进入应用管理后台的权限后，可查看订阅的SaaS应用后台配置，特定功能支持修改。

**以下功能均支持修改：**

1. 应用层：

   1. 角色管理、卡片管理、用户账号授权、数据卡片

2. 页面层：

   1. 页面流程设计、页面权限、门户、表单、报表、自定义页面、集成自动化流等

通用逻辑说明：一旦修改后，后续ISV升级版本后，对应功能有变更，客户侧订阅后将以本地修改的配置为主，不会同步更新主应用的变更到子应用；如果未修改，主应用增量资源变更将会同步至子应用。

审批流程修改变更逻辑说明：

1. 如果子应用订阅了V0版本，如果主应用有未发布的V1版本，在子应用历史版本中不予展示
2. 如果子应用订阅了V0版本，并未进行自定义，后续主应用升级到V1版本，子应用也应该按订阅的V0版本进行展示和运行
3. 如果子应用订阅了V0版本，并进行自定义，会创建一份自己内部的V0历史版本，然后创建一份V1的草稿态，同时子应用订阅新版本应用后，当前流程不再跟随主应用升级
4. 以上流程版本包括版本内的所有业务规则和公式

3. 默认会将主应用内"基础业务数据"表单数据携带至子应用，保障底表数据开箱即用，支持修改。

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673933944812-a07465f5-3e91-4c67-8508-65c00f478fab.png]]

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673934302646-de3b63a3-44a0-48a2-942d-0405a9eddba2.png]]

#### 4.3.2 体验测试酷应用

1. 主应用测试通过后，可测试酷应用，首先提交酷应用相关信息。点击"上架到钉钉酷应用市场>提交上架申请"，填写酷应用上架信息，包括酷应用基础信息、访问入口（最多可配置3个）及打开方式、机器人信息等。

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673934973704-0dddc3f6-fe03-46bb-8bc2-e45484bc1d22.png]]

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673935000231-97bc55d0-0c13-4792-89c6-48c90fd90b3f.png]]

2. 相关信息填写完毕后，点击保存并发布，会生成coolappcode

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673935099680-40ebfa93-b8c0-4eb2-b91d-79bda475c1c9.png]]

3. 您可以复制该酷应用的coolappcode，在当前体验组织下创建内部群，前往移动端按照下图进行安装测试。

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673935104822-cdd39dba-7eca-46b2-8c48-8a81ed6e6f74.png]]

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1673935170032-fb6f2dfb-218c-4291-b460-9770330eb21c.png]]

## 5. 应用运维

### 5.1 版本升级

服务商开发的SaaS应用上架到应用市场后，客户付费订阅当前SaaS应用后，ISV如有功能迭代，支持在"宜搭SaaS研发工作台>应用设置>远程运维"针对特定组织进行SaaS应用功能逐个/批量进行版本升级。

功能说明：

1. 默认可升级的版本功能范围为当前已发布之后迭代的最新版本列表
2. 支持针对多个付费组织进行批量版本升级

远程运维敬请期待

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1685015928447-3d92d5c7-5a8d-46c2-88a1-b0058aa13ab7.png]]

### 5.2 应用开通授权背景页设置

当宜搭SaaS应用上架到钉钉开放平台和应用中心后，支持自定义授权开通背景介绍页内容👉[了解更多](https://open.dingtalk.com/document/isvapp/1-product-interaction-process)

配置说明：

- 分别上传PC端/移动端开通授权背景页面（仅支持上传一张）

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1685015734794-d0b13106-301f-4b18-a8ce-3785dc4c2443.png]]

- 上传完毕后复制"试用访问地址"后前往伙伴自运营平台 > 第三方企业应用 > 商品上架管理 > 应用详情 > 管理 "应用内授权设置"信息，接入完成且自行验收通过后（👉[详细了解验收流程](https://open.dingtalk.com/document/isvapp/iv-acceptance)），该SaaS应用可在钉钉线上更多渠道进行推广（如钉钉搜索等场域）

|
![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1685013122224-32d3b1c0-5d9b-4809-aec5-4126fa47438a.png]]

移动端效果 |

![[yida_support-_9-ch41p3rm3may1smg-chrmgzrsthf55vp9_1685012856180-ef8ee7ca-e609-4135-9dfd-1cbd69e0ff1e.png]]

PC端效果 |
| --- | --- |

## 6. 常见FAQ

### Q1：订阅后的SaaS应用如何修改表单字段？

答：表单等功能支持已支持

### Q2：已上线发布的表单能删除组件吗？

答：禁止已上线发布的普通｜流程表单删除组件，包括子表单。

### Q3：发布的自定义页面中可否携带固定的企业CorpId？

答：任意自定义链接中不可携带固定的CorpId

### Q4：酷应用安装失败该如何处理？

答：请在"非主应用组织内新建内部群"安装酷应用进行测试。

### Q5：自定义页面跳转表单页面，如何传递当前群的群id参数？

请参考[酷应用高频FAQ及典型场景设计指南](https://www.yuque.com/yida/support/tog63y#kkDZ6 "酷应用高频FAQ及典型场景设计指南")

### Q6：如何隐藏SaaS应用某页面菜单导航栏？

答：当宜搭页面被集成到其他系统内时，支持配置隐藏顶部导航栏和左侧页面功能导航栏。在被嵌入的页面URL后拼接?isRenderNav=false即可。
