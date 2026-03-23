---
title: "宜搭 Open API (旧)"
source: "https://docs.aliwork.com/docs/yida_support/lbtl0t/rrwdug/agb8im"
category: "用戶手冊 / 开发者功能（需有代码基础） / 宜搭 Open API 开放接口"
updated: 
tags:
  - yida
  - 用戶手冊
---

目前，宜搭已经将 OpenAPI 全部上架到了钉钉开放平台, 但是仍然会保留[宜搭OpenAPI调用(旧)](agb8im) （**后续会逐步移除epaas宜搭OpenAPI说明文档，注意: 仅仅是移除说明文档**）。**通过钉钉开放平台调用宜搭 OpenAPI 是更好的选择**。

**当前文档是 epaas 宜搭 OpenAPI，不再建议通过 epaas 访问宜搭 OpenAPI**。

通过钉钉开放平台调用宜搭 OpenAPI 请参考 宜搭Open API开放接口

手把手教程：

[宜搭调用外部接口后将数据回传到宜搭中](../../../yida_qalist/lmvsctyt7rxtgsrq/kkcdu6/ezyvpb "宜搭调用外部接口后将数据回传到宜搭中")

## 1. 准备工作

#### 第一步：申请秘钥授权

目前宜搭已接入钉钉开放平台，优先走 [钉钉开放平台接口](https://open.dingtalk.com/document/orgapp-server/dingtalk-openapi-overview)，无需申请秘钥授权。

#### 第二步：参考案例完成请求调用

demo 参考：下载样例项目 [📎call-yidaapi-demo.7z](https://www.yuque.com/attachments/yuque/0/2021/7z/400515/1629352521888-e3c38702-afa8-4c75-9fb2-36a244b7835e.7z) 获取的应用 accessKey 和 secretKey 填入gateway.properties 配置文件中。样例项目是独立的 Spring boot 项目，用户根据需求做取舍。

#### 1.1 Java调用方式

##### (1)引入依赖

###### 手动JAR包依赖

[📎xxpt.gateway.shared.client.zip](https://www.yuque.com/attachments/yuque/0/2021/zip/137701/1615595155423-1b82f6f2-e210-4430-91f3-cb5301d36a67.zip)

###### 其他依赖

```xml
<dependency><groupId>org.apache.httpcomponents</groupId><artifactId>httpclient</artifactId><version>4.5.2</version></dependency><dependency><groupId>joda-time</groupId><artifactId>joda-time</artifactId><version>2.9.4</version></dependency><dependency><groupId>org.apache.commons</groupId><artifactId>commons-lang3</artifactId><version>3.4</version></dependency>
```

说明：

上述需要引入的 maven 配置是网关调用的依赖项，如果和您本地的 jar 包版本冲突，请进行排包处理

##### (2)参数配置

例自定义配置文件：aecpgateway.properties

**xxpt.gateway.protocal**=**https**

**xxpt.gateway.domainName**=**s-api.alibaba-inc.com**

**xxpt.gateway.accessKey**=自己的 accessKey

**xxpt.gateway.secretKey**=自己的 secretKey

通过 XML 定义 bean

```xml
<?xml version="1.0" encoding="UTF-8" ?><beansxmlns="http://www.springframework.org/schema/beans"xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"xmlns:context="http://www.springframework.org/schema/context"xmlns:tx="http://www.springframework.org/schema/tx"xmlns:util="http://www.springframework.org/schema/util"xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsdhttp://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-2.5.xsdhttp://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-2.5.xsdhttp://www.springframework.org/schema/util http://localhost:8080/schema/www.springframework.org/schema/util/spring-util-2.0.xsd "default-autowire="byName"><beanid="propertyConfigurer"class="org.springframework.beans.factory.config.PropertyPlaceholderConfigurer"><propertyname="locations"><list><value>classpath:aecpgateway.properties</value></list></property></bean><beanid="executableClient"class="com.alibaba.xxpt.gateway.shared.client.http.ExecutableClient"factory-method="getInstance"init-method="init"destroy-method="destroy"><propertyname="protocal"value="${xxpt.gateway.protocal}"/><propertyname="domainName"value="${xxpt.gateway.domainName}"/><propertyname="accessKey"value="${xxpt.gateway.accessKey}"/><propertyname="secretKey"value="${xxpt.gateway.secretKey}"/></bean></beans>
```

出于安全性考虑，上文中的 ${accessKey} 和 ${secretKey} 请联系宜搭开发人员获取。

说明：

-   上述需要配置的 XML 需要自行通过 spring 进行加载，文件名没有要求，sdk 中不会自动加载
-   配置 bean 后，通过 ExecutableClient.getInstance() 获取的对象是单例，请知晓
-   如果项目框架不是 spring，可以自行通过 new ExecutableClient() 的方式创建对象，对象有设置上述属性的set 方法，属性设置完成后，请务必调用该对象的 init 方法初始化对象内部的其他属性

##### (3)调用示例

简单的单元测试：

```java
@Testpublic void postYidaOutTest() {    String api = "/yida_vpc/form/searchFormDatas.json";    PostClient postClient = ExecutableClient.getInstance().newPostClient(api);    postClient.addParameter("appType", "APP_XXX");    postClient.addParameter("systemToken", "XXX");    postClient.addParameter("formUuid", "XXX");    postClient.addParameter("userId", "yida_pub_account");    String apiResult = postClient.post();    Assert.notNull(apiResult);}
```

工程中实际使用：

```java
import com.alibaba.fastjson.JSON;import com.alibaba.xxpt.gateway.shared.client.http.ExecutableClient;import com.alibaba.xxpt.gateway.shared.client.http.PostClient;import org.springframework.util.CollectionUtils;import java.util.HashMap;import java.util.Map;/** aecp网关服务请求工具* @Author: weimeng(shanyu)* @Date: 2019/2/28 下午2:50*/public class AecpGatewayRequestUtil { /**    * 请求aecp网关    * @param param 请求参数    * @param url 网关地址, 在aecp网关服务（https://epaas.alibaba-inc.com）查看    * @return 请求结果    */    public static AecpGatewayResult baseRequest(Map<String, String> param, String url) {        try {            PostClient postClient = ExecutableClient.getInstance().newPostClient(url);            if (!CollectionUtils.isEmpty(param)) {                for (Map.Entry<String, String> entry : param.entrySet()) {                    postClient.addParameter(entry.getKey(), entry.getValue());                }            }            String result = postClient.post();            return JSON.parseObject(result, AecpGatewayResult.class);        }catch(Throwable e){            AecpGatewayResult result= new AecpGatewayResult();            result.setSuccess(false);            result.setResult("false");            return result;        }    }}
```

```java
/*** aecp网关服务请求的返回结果类* @Author: weimeng(shanyu)* @Date: 2019/2/28 下午2:52*/public class AecpGatewayResult {    private boolean success;    private String content;    private String result;    private String errorCode;    private String errorMsg;    public boolean isSuccess() {        return success;    }    public void setSuccess(boolean success) {        this.success = success;    }    public String getResult() {        if (result == null) {            return content;        } else {            return result;        }    }    public void setResult(String result) {        this.result = result;    }    public String getErrorCode() {        return errorCode;    }    public void setErrorCode(String errorCode) {        this.errorCode = errorCode;    }    public String getErrorMsg() {        return errorMsg;    }    public void setErrorMsg(String errorMsg) {        this.errorMsg = errorMsg;    }    public String getContent() {        if (content == null) {            return result;        } else {            return content;        }    }    public void setContent(String content) {        this.content = content;    }    @Override    public String toString() {        return "AecpGatewayResult{" +            "success=" + success +            ", result='" + getResult() + ''' +            ", errorCode='" + errorCode + ''' +            ", errorMsg='" + errorMsg + ''' +            '}';    }}
```

```java
/**    * 获取授权用户账号列表    */    public static final String GET_USER_LIST = "/yida_vpc/corp/getAliyunAuthInfo.json";try {    Map<String, String> param = new HashMap<String, String>();    param.put(AecpHsfConstants.CURRENT_PAGE, request.getCurrentPage()+"");    param.put(AecpHsfConstants.PAGE_SIZE, request.getPageSize()+"");    param.put(AecpHsfConstants.ACCOUNT_NAME, request.getAccountName());    // 调用注册在aecp网关服务上的宜搭接口    	AecpGatewayResult result = AecpGatewayRequestUtil.baseRequest(param, GET_USER_LIST);    // 请求成功    	if(result.isSuccess()){	 // 解析数据，用户列表        	response = JSON.parseObject(result.getResult(), ConsoleUserListResponse.class);        if(response.getEmployee() != null && response.getEmployee().getTotalCount() != null){            response.setTotal(response.getEmployee().getTotalCount().longValue());        }        return response;    }} catch (Exception e) {	// TODO}
```

## 2. 表单接口

### 2.1 新增表单实例

-   接口：[/yida_vpc/form/saveFormData.json](https://s-api.alibaba-inc.com/yida_vpc/form/saveFormData.json)
-   参数：

| 参数名 | 描述 | 是否必填 | 示例 | 备注 |
| --- | --- | --- | --- | --- |
| appType | 应用ID | 是 | APP_PBKT0MFBEBTDO8T7SLVP | |
| systemToken | 应用秘钥 | 是 | hexxxx | 在[应用数据](https://www.yuque.com/yida/support/ydihkw#Cf3yb)中获取。 |
| userId | 钉钉的userId | 是 | |
 |
| language | 语言 | 否 | zh_CN | 可选值：zh_CN/en_US 默认：zh_CN |
| formUuid | 表单ID | 是 | FORM-NJYJZELV8YZRDEI2N5IQ7L6VEDMR1VE9GMPCJB | |
| formDataJson | 表单数据 | 是 | {"textField_jcpm6agt": "单行","employeeField_jcos0sar": \["workno"\]} | 参考：附录1保存/更新 表单数据格式说明 |

-   返回值：

-   success: 请求是否成功
-   result：实例 ID
-   errorMsg: 错误信息
-   errorCode：错误码

-   返回值demo：{"result":"FINST-EF6Y93URN2UZ1SBPLIP9NAV6HR2GEO1Z4ZCHSCJ0","success":true}

---

### 2.2 更新表单中指定组件值

-   接口：[/yida_vpc/form/updateFormData.json](https://s-api.alibaba-inc.com/yida_vpc/form/updateFormData.json)
-   参数：

| 参数名 | 描述 | 是否必填 | 示例 | 备注 |
| --- | --- | --- | --- | --- |
| appType | 应用ID | 是 | APP_PBKT0MFBEBTDO8T7SLVP | |
| systemToken | 应用秘钥 | 是 | helxxx | 在[应用数据](https://www.yuque.com/yida/support/ydihkw#Cf3yb)中获取。 |
| userId | 钉钉的userId | 是 | |
 |
| language | 语言 | 否 | zh_CN | 可选值：zh_CN/en_US 默认：zh_CN |
| formInstId | 要更新的表单数据ID | 是 | 33f6d221-17f8-42b7-836a-682b95a046c2 | |
| useLatestVersion | 使用最新的表单版本进行更新 | 否 | false | 默认为false |
| updateFormDataJson | 要更新的表单组件值，必填 | 是 | {"employeeField_jcpm5gy2": \["workno"\]} | 参考：附录1保存/更新 表单数据格式说明。 参数有的组件更新，没有的组件保持不变。 明细的值只能统一更新，无法只更新明细下某个组件的值 |

-   返回值：

-   success: 请求是否成功
-   errorMsg: 错误信息
-   errorCode：错误码

-   返回值 demo：{"success":true}

---

### 2.3 删除表单实例

-   接口：[/yida_vpc/form/deleteFormData.json](https://s-api.alibaba-inc.com/yida_vpc/form/deleteFormData.json)
-   参数：

| 参数名 | 描述 | 是否必填 | 示例 | 备注 |
| --- | --- | --- | --- | --- |
| appType | 应用ID | 是 | APP_PBKT0MFBEBTDO8T7SLVP | |
| systemToken | 应用秘钥 | 是 | helxxx | 在[应用数据](https://www.yuque.com/yida/support/ydihkw#Cf3yb)中获取。 |
| userId | 钉钉的userId | 是 | |
 |
| language | 语言 | 否 | zh_CN | 可选值：zh_CN/en_US 默认：zh_CN |
| formInstId | 要删除的表单数据ID | 是 | 33f6d221-17f8-42b7-836a-682b95a046c2 | |

-   返回值：

-   success: 请求是否成功
-   errorMsg: 错误信息
-   errorCode：错误码

-   返回值 demo：{"success":true}

---

### 2.4 根据表单 ID 查询实例详情

-   接口：[/yida_vpc/form/getFormDataById.json](https://s-api.alibaba-inc.com/yida_vpc/form/getFormDataById.json)
-   参数：

| 参数名 | 描述 | 是否必填 | 示例 | 备注 |
| --- | --- | --- | --- | --- |
| appType | 应用ID | 是 | APP_PBKT0MFBEBTDO8T7SLVP | |
| systemToken | 应用秘钥 | 是 | helxx | 在[应用数据](https://www.yuque.com/yida/support/ydihkw#Cf3yb)中获取。 |
| userId | 钉钉的userId | 是 | |
 |
| language | 语言 | 否 | zh_CN | 可选值：zh_CN/en_US 默认：zh_CN |
| formInstId | 要查询的实例的实例ID | 是 | 33f6d221-17f8-42b7-836a-682b95a046c2 | |

-   返回值

-   success:请求是否成功
-   errorMsg: 错误信息
-   errorCode：错误码
-   result：单据实例详情。参见附录5. 单据实例详情对象格式说明

---

### 2.5 根据条件搜索表单实例 ID 列表

-   接口：[/yida_vpc/form/searchFormDataIds.json](https://s-api.alibaba-inc.com/yida_vpc/form/searchFormDataIds.json)
-   说明：只有应用管理员才能使用这个接口
-   参数：

| 参数名 | 描述 | 是否必填 | 示例 | 备注 |
| --- | --- | --- | --- | --- |
| appType | 应用ID | 是 | APP_PBKT0MFBEBTDO8T7SLVP | |
| systemToken | 应用秘钥 | 是 | hexxx | 在[应用数据](https://www.yuque.com/yida/support/ydihkw#Cf3yb)中获取。 |
| userId | 钉钉的userId | 是 | |
 |
| language | 语言 | 否 | zh_CN | 可选值：zh_CN/en_US 默认：zh_CN |
| formUuid | 表单ID | 是 | FORM-EF6Y4G8WO2FN0SUB43TDQ3CGC3FMFQ1G9400RCJ3 | |
| searchFieldJson | 根据表单内组件值查询 | 否 | | 格式见附录2：根据组件值进行条件搜索，组件值格式说明 |
| currentPage | 当前页 | 否 | 1 | 必须大于0 默认1 |
| pageSize | 每页记录数 | 否 | 10 | 必须大于0 默认10 不能大于100 |
| originatorId | 根据数据提交人工号查询 | 否 | |
 |
| createFrom | createFrom和createTo两个时间构造一个时间段。查询在该时间段创建的数据列表 | 否 | 2018-01-01 | 字符串格式，且为yyyy-MM-DD格式 |
| createTo | createFrom和createTo两个时间构造一个时间段。查询在该时间段创建的数据列表。 | 否 | 2018-02-01 | 字符串格式，且为yyyy-MM-DD格式。 和createFrom一起，相当于查询在 2018-01-01到2018-01-31之间(包含01和31号)创建的数据。 |
| modifiedFrom | modifiedFrom和modifiedTo构成一个时间段，查询在该时间段有修改的数据列表 | 否 | 2018-01-01 | 字符串格式，且为yyyy-MM-DD格式 |
| modifiedTo | modifiedFrom和modifiedTo构成一个时间段，查询在该时间段有修改的数据列表。 | 否 | 2018-02-01 | 字符串格式，且为yyyy-MM-DD格式。 和modifiedFrom一起，相当于查询在 2018-01-01到2018-01-31之间(包含01和31号)被修改的数据。 |

-   返回值

-   success : 请求是否成功;
-   errorCode : 错误码;
-   errorMsg : 错误信息;
-   result :

-   currentPage : 当前页
-   totalCount : 符合条件的实例总数
-   data : 实例ID列表

-   返回值 demo：{"result":{"data":\["FINST-EF6Y93URN2F02S745LTMW2D2G4WVDS16O17ISCJ0"\],"totalCount":1,"currentPage":1},"success":true}

### 2.6 根据条件搜索表单实例详情列表

-   接口：[/yida_vpc/form/searchFormDatas.json](https://s-api.alibaba-inc.com/yida_vpc/form/searchFormDatas.json)
-   说明：只有应用管理员才能使用这个接口
-   参数

| 参数名 | 描述 | 是否必填 | 示例 | 备注 |
| --- | --- | --- | --- | --- |
| appType | 应用ID | 是 | APP_PBKT0MFBEBTDO8T7SLVP | |
| systemToken | 应用秘钥 | 是 | hellxxx | 在[应用数据](https://www.yuque.com/yida/support/ydihkw#Cf3yb)中获取。 |
| userId | 钉钉的userId | 是 | |
 |
| language | 语言 | 否 | zh_CN | 可选值：zh_CN/en_US 默认：zh_CN |
| formUuid | 表单ID | 是 | FORM-EF6Y4G8WO2FN0SUB43TDQ3CGC3FMFQ1G9400RCJ3 | |
| searchFieldJson | 根据表单内组件值查询 | 否 | | 格式见附录2：根据组件值进行条件搜索，组件值格式说明 |
| currentPage | 当前页 | 否 | 1 | 必须大于0，默认1 |
| pageSize | 每页记录数 | 否 | 10 | 必须大于0 默认10 不能大于100 |
| originatorId | 根据数据提交人工号查询 | 否 | |
 |
| createFrom | createFrom和createTo两个时间构造一个时间段。查询在该时间段创建的数据列表 | 否 | 2018-01-01 | 字符串格式，且为yyyy-MM-DD格式 （或者精确到秒 yyyy-MM-DD HH:mm:ss） |
| createTo | createFrom和createTo两个时间构造一个时间段。查询在该时间段创建的数据列表。 | 否 | 2018-02-01 | 字符串格式，且为yyyy-MM-DD格式（或者精确到秒 yyyy-MM-DD HH:mm:ss） 和createFrom一起，相当于查询在 2018-01-01到2018-01-31之间(包含01和31号)创建的数据。 |
| modifiedFrom | modifiedFrom和modifiedTo构成一个时间段，查询在该时间段有修改的数据列表 | 否 | 2018-01-01 | 字符串格式，且为yyyy-MM-DD格式（或者精确到秒 yyyy-MM-DD HH:mm:ss） |
| modifiedTo | modifiedFrom和modifiedTo构成一个时间段，查询在该时间段有修改的数据列表。 | 否 | 2018-02-01 | 字符串格式，且为yyyy-MM-DD格式。 （或者精确到秒 yyyy-MM-DD HH:mm:ss）和modifiedFrom一起，相当于查询在 2018-01-01到2018-01-31之间(包含01和31号)被修改的数据。 |
| dynamicOrder | 指定排序字段 | 否 | {"numberField_1ac":"+"} | 表示按照字段numberField_1ac升序排列 |

**解决方案：**如何使用上表中`dynamicOrder`参数实现对一个或多个字段进行自定义排序?以JAVA为例，详见下方代码。

```java
Map dynamicOrdern = new HashMap();dynamicOrdern.put("textField_ky1av3w7","+");SearchFormDatasRequest searchFormDatasRequest = new SearchFormDatasRequest().setDynamicOrder(JSON.toJSONString(dynamicOrdern));
```

-   返回值

-   success : 请求是否成功;
-   errorCode : 错误码;
-   errorMsg : 错误信息;
-   result :

-   currentPage : 当前页
-   totalCount : 符合条件的实例总数
-   data : 实例详情列表。每个实例详情格式参见 附录 4 作为返回值的表单数据的格式说明

### 2.7 获取表单定义

-   接口：[/yida_vpc/formDesign/getFormComponentDefinationList.json](https://s-api.alibaba-inc.com/yida_vpc/formDesign/getFormComponentDefinationList.json)
-   参数：

| 参数名 | 描述 | 是否必填 | 示例 | 备注 |
| --- | --- | --- | --- | --- |
| appType | 应用ID | 是 | APP_PBKT0MFBEBTDO8T7SLVP | |
| systemToken | 应用秘钥 | 是 | hexxxx | 在[应用数据](https://www.yuque.com/yida/support/ydihkw#Cf3yb)中获取。 |
| userId | 钉钉的userId | 是 | |
 |
| language | 语言 | 否 | zh_CN | 可选值：zh_CN/en_US 默认：zh_CN |
| formUuid | 表单ID | 是 | FORM-NJYJZELV8YZRDEI2N5IQ7L6VEDMR1VE9GMPCJB | |
| version | 表单版本 | 否 | 1 | 可以传入formData中的version字段。 为空时返回最新的版本定义 |

-   返回值：

-   success: 请求是否成功
-   result：\[\]
-   errorMsg: 错误信息
-   errorCode：错误码

-   返回格式

```json
{"success":true,"content":[{"label":"{"en_US":"CheckBox Field","zh_CN":"多选","type":"i18n"}","key":"checkboxField_jiwvhkdi"},{"label":"{"en_US":"Textarea Field","zh_CN":"多行输入框","type":"i18n"}","key":"textareaField_jiwvhkdh"},{"label":"{"en_US":"Select Field","zh_CN":"下拉单选","type":"i18n"}","key":"selectField_jiwvhkdg"}]}
```

### 2.8 获取子表单数据

-   接口：[/yida_vpc/form/listTableDataByFormInstIdAndTableId.json](yida_vpc/form/listTableDataByFormInstIdAndTableId.json)
-   参数

| 参数名 | 描述 | 是否必填 | 示例 | 备注 |
| --- | --- | --- | --- | --- |
| appType | 应用ID | 是 | APP_PBKT0MFBEBTDO8T7SLVP | |
| formUuid | 表单ID | 是 | FORM-EF6Y4G8WO2FN0SUB43TDQ3CGC3FMFQ1G9400RCJ3 | |
| formInstanceId | 要查询的实例的实例ID | 是 | FINST-NJYJZELVVYZRVGJHR7M6FJW3ESJN1P1TCNPCJ9 | |
| tableFieldId | 需要查找的子表单组件的唯一标识 | 是 | tableField_ksyaujq1 | |
| currentPage | 当前页 | 否 | 10 | 必须大于0，默认1 |
| pageSize | 每页记录数 | 否 | 50 | 大于0并且小于50，默认10 |
| systemToken | 应用秘钥 | 是 | hexxxx | 在[应用数据](https://www.yuque.com/yida/support/ydihkw#Cf3yb)中获取。 |
| userId | 钉钉的userId | 是 | |
 |

## 3. 流程接口

### 3.1 发起新的流程实例

-   接口: [/yida_vpc/process/startInstance.json](https://s-api.alibaba-inc.com/yida_vpc/process/startInstance.json)

-   参数

| 参数名 | 描述 | 是否必填 | 示例 | 备注 |
| --- | --- | --- | --- | --- |
| appType | 应用ID | 是 | APP_PBKT0MFBEBTDO8T7SLVP | |
| systemToken | 应用秘钥 | 是 | hexxxx | 在[应用数据](https://www.yuque.com/yida/support/ydihkw#Cf3yb)中获取。 |
| userId | 钉钉的userId | 是 | |
 |
| language | 语言环境 | 否 | zh_CN | 可选值：zh_CN/en_US |
| processCode | 流程code | 是 | TPROC--EF6Y4G8WO2FN0SUB43TDQ3CGC3FMFQ1G9400RCJ4 | 单独发起页链接上可查 |
| formUuid | 表单ID | 是 | FORM-EF6Y4G8WO2FN0SUB43TDQ3CGC3FMFQ1G9400RCJ3 | 单独发起页链接上可查 |
| formDataJson | 表单数据 | 是 | | 参考：附录1保存/更新 表单数据格式说明 |
| deptId | 发起人所在部门号 | 否 | 18295 | 不填，默认发起人主职部门 |

-   返回值：

-   result : 实例 ID;

-   success : 请求是否成功;

-   errorMsg : 错误信息;

-   errorCode : 错误码;

-   返回值 demo： {"result":"f30233fb-72e1-4af4-8cb8-c7e0ea9ee530","success":true}

---

### 3.2 根据条件搜索流程实例 ID

-   接口：[/yida_vpc/process/getInstanceIds.json](https://s-api.alibaba-inc.com/yida_vpc/process/getInstanceIds.json)

-   说明：只有应用管理员才能使用这个接口

-   参数

| 参数名 | 描述 | 是否必填 | 示例 | 备注 |
| --- | --- | --- | --- | --- |
| appType | 应用ID | 是 | APP_PBKT0MFBEBTDO8T7SLVP | |
| systemToken | 应用秘钥 | 是 | hexxxx | 在[应用数据](https://www.yuque.com/yida/support/ydihkw#Cf3yb)中获取。 |
| userId | 钉钉的userId | 是 | |
 |
| language | 语言 | 否 | zh_CN | 可选值：zh_CN/en_US 默认：zh_CN |
| formUuid | 表单ID | 是 | FORM-EF6Y4G8WO2FN0SUB43TDQ3CGC3FMFQ1G9400RCJ3 | |
| searchFieldJson | 根据表单内组件值查询 | 否 | | 格式见附录2：根据组件值进行条件搜索，组件值格式说明 |
| taskId | 任务ID | 否 | 2199132092 | 一般用不到。 |
| instanceStatus | 实例状态 | 否 | RUNNING | 可选值为：RUNNING,TERMINATED,COMPLETED,ERROR。 分别代表：运行中，已终止，已完成，异常。 |
| approvedResult | 流程审批结果 | 否 | agree | 可选值为：agree, disagree。 分别表示：同意， 拒绝。 |
| currentPage | 当前页 | 否 | 1 | 必须大于0 默认1 |
| pageSize | 每页记录数 | 否 | 10 | 必须大于0 默认10 不能大于100 |
| originatorId | 根据流程发起人工号查询 | 否 | |
 |
| createFrom | createFrom和createTo两个时间构造一个时间段。查询在该时间段创建的数据列表 | 否 | 2018-01-01 | 字符串格式，且为yyyy-MM-DD格式 yyyy-MM-DD  |
| createTo | createFrom和createTo两个时间构造一个时间段。查询在该时间段创建的数据列表。 | 否 | 2018-02-01 | 字符串格式，且为yyyy-MM-DD格式。 和createFrom一起，相当于查询在 2018-01-01到2018-01-31之间(包含01和31号)创建的数据。 |
| modifiedFrom | modifiedFrom和modifiedTo构成一个时间段，查询在该时间段有修改的数据列表 | 否 | 2018-01-01 | 字符串格式，且为yyyy-MM-DD格式 |
| modifiedTo | modifiedFrom和modifiedTo构成一个时间段，查询在该时间段有修改的数据列表。 | 否 | 2018-02-01 | 字符串格式，且为yyyy-MM-DD格式。 和modifiedFrom一起，相当于查询在 2018-01-01到2018-01-31之间(包含01和31号)被修改的数据。 |

-   返回

-   result : 实例 ID 列表;

-   success : 请求是否成功;

-   errorMsg : 错误信息;

-   errorCode : 错误码;

-   返回值 demo： {"result":{"data":\["f30233fb-72e1-4af4-8cb8-c7e0ea9ee530","bc0950a3-fe1b-459c-b6ba-282be38523ab","f540cbd7-43eb-40de-b915-6716578a2802"\],"totalCount":3,"currentPage":1},"success":true}

---

### 3.3 根据搜索条件获取实例详情

-   接口： [/yida_vpc/process/getInstances.json](https://s-api.alibaba-inc.com/yida_vpc/process/getInstances.json)

-   说明：只有应用管理员才能使用这个接口

-   参数

| 参数名 | 描述 | 是否必填 | 示例 | 备注 |
| --- | --- | --- | --- | --- |
| appType | 应用ID | 是 | APP_PBKT0MFBEBTDO8T7SLVP | |
| systemToken | 应用秘钥 | 是 | helxxxy | 在[应用数据](https://www.yuque.com/yida/support/ydihkw#Cf3yb)中获取。 |
| userId | 钉钉的userId | 是 | |
 |
| language | 语言 | 否 | zh_CN | 可选值：zh_CN/en_US 默认：zh_CN |
| formUuid | 表单ID | 是 | FORM-EF6Y4G8WO2FN0SUB43TDQ3CGC3FMFQ1G9400RCJ3 | |
| searchFieldJson | 根据表单内组件值查询 | 否 | | 格式见附录2：根据组件值进行条件搜索，组件值格式说明 |
| taskId | 任务ID | 否 | 2199132092 | 一般用不到。 |
| instanceStatus | 实例状态 | 否 | RUNNING | 可选值为：RUNNING,TERMINATED,COMPLETED,ERROR。 分别代表：运行中，已终止，已完成，异常。 |
| approvedResult | 流程审批结果 | 否 | agree | 可选值为：agree, disagree。 分别表示：同意， 拒绝。 |
| currentPage | 当前页 | 否 | 1 | 必须大于0 默认1 |
| pageSize | 每页记录数 | 否 | 10 | 必须大于0 默认10 不能大于100 |
| originatorId | 根据流程发起人工号查询 | 否 | |
 |
| createFrom | createFrom和createTo两个时间构造一个时间段。查询在该时间段创建的数据列表 | 否 | 2018-01-01 | 字符串格式，且为yyyy-MM-DD格式 |
| createTo | createFrom和createTo两个时间构造一个时间段。查询在该时间段创建的数据列表。 | 否 | 2018-02-01 | 字符串格式，且为yyyy-MM-DD格式。 和createFrom一起，相当于查询在 2018-01-01到2018-01-31之间(包含01和31号)创建的数据。 |
| modifiedFrom | modifiedFrom和modifiedTo构成一个时间段，查询在该时间段有修改的数据列表 | 否 | 2018-01-01 | 字符串格式，且为yyyy-MM-DD格式 |
| modifiedTo | modifiedFrom和modifiedTo构成一个时间段，查询在该时间段有修改的数据列表。 | 否 | 2018-02-01 | 字符串格式，且为yyyy-MM-DD格式。 和modifiedFrom一起，相当于查询在 2018-01-01到2018-01-31之间(包含01和31号)被修改的数据。 |

-   返回值

-   errorCode : 错误码;

-   success : 请求是否成功;

-   errorMsg : 错误信息;

-   result :

-   currentPage : 当前页

-   totalCount : 符合条件的实例总数

-   data : 实例详情列表，实例详情格式 参见 附录 3- 流程实例详情对象格式说明

---

### 3.4 根据实例 ID 获取流程实例详情

-   接口：[/yida_vpc/process/getInstanceById.json](https://s-api.alibaba-inc.com/yida_vpc/process/getInstanceById.json)

-   参数

| 参数名 | 描述 | 是否必填 | 示例 | 备注 |
| --- | --- | --- | --- | --- |
| appType | 应用ID | 是 | APP_PBKT0MFBEBTDO8T7SLVP | |
| systemToken | 应用秘钥 | 是 | hexxyy | 在[应用数据](https://www.yuque.com/yida/support/ydihkw#Cf3yb)中获取。 |
| userId | 钉钉的userId | 是 | |
 |
| language | 语言 | 否 | zh_CN | 可选值：zh_CN/en_US 默认：zh_CN |
| processInstanceId | 流程实例ID | 是 | f30233fb-72e1-4af4-8cb8-c7e0ea9ee530 | 不限制字符串长度，但processInstanceIds 包含的流程实例 ID 数不能超过100个。 |

-   返回值

-   result : 实例详情，参见附录 3- 流程实例详情对象格式说明

-   success : 请求是否成功;

-   errorMsg : 错误信息;

-   errorCode : 错误码;

---

### 3.5 根据实例 ID 列表批量获取流程实例详情

-   接口：[/yida_vpc/process/getInstancesByIds.json](https://s-api.alibaba-inc.com/yida_vpc/process/getInstancesByIds.json)
-   参数

| 参数名 | 描述 | 是否必填 | 示例 | 备注 |
| --- | --- | --- | --- | --- |
| appType | 应用ID | 是 | APP_PBKT0MFBEBTDO8T7SLVP | |
| systemToken | 应用秘钥 | 是 | hexxyy | 在[应用数据](https://www.yuque.com/yida/support/ydihkw#Cf3yb)中获取。 |
| userId | 钉钉的userId | 是 | |
 |
| language | 语言 | 否 | zh_CN | 可选值：zh_CN/en_US 默认：zh_CN |
| processInstanceIds | 流程实例ID列表，多个用,分割 | 是 | f30233fb-72e1-4af4-8cb8-c7e0ea9ee530,d230233fb-72e1-4af4-8cb8-c7e0ea9ee530 | 不限制字符串长度，但processInstanceIds 包含的流程实例 ID 数不能超过100个。 |

-   返回值

-   result : 实例详情列表，参见附录 3- 流程实例详情对象格式说明
-   success : 请求是否成功;
-   errorMsg : 错误信息;
-   errorCode : 错误码;

---

### 3.6 更新流程实例

-   接口: /yida_vpc/process/updateInstance.json
-   参数

| 参数名 | 描述 | 是否必填 | 示例 | 备注 |
| --- | --- | --- | --- | --- |
| appType | 应用ID | 是 | APP_PBKT0MFBEBTDO8T7SLVP | |
| systemToken | 应用秘钥 | 是 | hello1234 | 在[应用数据](https://www.yuque.com/yida/support/ydihkw#Cf3yb)中获取。 |
| userId | 钉钉的userId | 是 | | 会校验userId是否有流程发起权限 |
| language | 语言环境 | 否 | zh_CN | 可选值：zh_CN/en_US |
| processInstanceId | 实例ID | 是 | | 不限制字符串长度，但processInstanceIds 包含的流程实例 ID 数不能超过100个。 |
| updateFormDataJson | 更新的表单数据 | 是 | | 参考：附录1保存/更新 表单数据格式说明 |

-   返回值：

-   success : 是否成功
-   errorMsg : 错误信息;
-   errorCode : 错误码;

-   返回值 demo： {"success":true}

---

### 3.7 删除流程实例

-   接口：[/yida_vpc/process/deleteInstance.json](https://s-api.alibaba-inc.com/yida_vpc/process/deleteInstance.json)

-   说明：只有应用管理员才能使用这个接口

-   参数

| 参数名 | 描述 | 是否必填 | 示例 | 备注 |
| --- | --- | --- | --- | --- |
| appType | 应用ID | 是 | APP_PBKT0MFBEBTDO8T7SLVP | |
| systemToken | 应用秘钥 | 是 | hexxxx | 在[应用数据](https://www.yuque.com/yida/support/ydihkw#Cf3yb)中获取。 |
| userId | 钉钉的userId | 是 | |
 |
| language | 语言 | 否 | zh_CN | 可选值：zh_CN/en_US 默认：zh_CN |
| processInstanceId | 流程实例ID | 是 | f30233fb-72e1-4af4-8cb8-c7e0ea9ee530 | 不限制字符串长度，但processInstanceIds 包含的流程实例 ID 数不能超过100个。 |

-   返回值

-   success : 请求是否成功;

-   errorMsg : 错误信息;

-   errorCode : 错误码;

---

### 3.8 终止流程实例

-   接口：[/yida_vpc/process/terminateInstance.json](https://s-api.alibaba-inc.com/yida_vpc/process/terminateInstance.json)

-   参数

| 参数名 | 描述 | 是否必填 | 示例 | 备注 |
| --- | --- | --- | --- | --- |
| appType | 应用ID | 是 | APP_PBKT0MFBEBTDO8T7SLVP | |
| systemToken | 应用秘钥 | 是 | hexxxx | 在[应用数据](https://www.yuque.com/yida/support/ydihkw#Cf3yb)中获取。 |
| userId | 钉钉的userId | 是 | |
 |
| language | 语言 | 否 | zh_CN | 可选值：zh_CN/en_US 默认：zh_CN |
| processInstanceId | 流程实例ID | 是 | f30233fb-72e1-4af4-8cb8-c7e0ea9ee530 | 不限制字符串长度，但processInstanceIds 包含的流程实例 ID 数不能超过100个。 |

-   返回值

-   success : 请求是否成功;

-   errorMsg : 错误信息;

-   errorCode : 错误码;

---

### 3.9 执行审批任务

-   接口：[/yida_vpc/task/executeTask.json](https://s-api.alibaba-inc.com/yida_vpc/task/executeTask.json)

-   参数

| 参数名 | 描述 | 是否必填 | 示例 | 备注 |
| --- | --- | --- | --- | --- |
| appType | 应用ID | 是 | APP_PBKT0MFBEBTDO8T7SLVP | |
| systemToken | 应用秘钥 | 是 | hexxyy | 在[应用数据](https://www.yuque.com/yida/support/ydihkw#Cf3yb)中获取。 |
| userId | 钉钉的userId | 是 | | 需要传任务实际处理人的 userId |
| language | 语言 | 否 | zh_CN | 可选值：zh_CN/en_US 默认：zh_CN |
| taskId | 任务ID | 是 | 12002575 | |
| procInstId | 实例ID | 是 | f30233fb-72e1-4af4-8cb8-c7e0ea9ee530 | |
| outResult | 审批结果 | 是 | AGREE | AGREE(同意)、DISAGREE(不同意) |
| remark | 审批意见 | 是 | 确认同意 | |
| formDataJson | 更新的表单值 | 否 | | 参考：附录1保存/更新 表单数据格式说明。 参数有的组件更新，没有的组件保持不变。 明细的值只能统一更新，无法只更新明细下某个组件的值 |
| noExecuteExpressions | 是否不执行校验&关联操作 | 否 | y | 本任务节点有绑定校验规则或者关联操作时， y -> 不执行校验规则&关联操作 n -> 执行校验规则&关联操作 不传默认为n，即会执行校验规则&关联操作 |

-   返回值

-   success : 请求是否成功;

-   errorMsg : 错误信息;

-   errorCode : 错误码;

---

### 3.10 执行转交任务

-   接口: /yida_vpc/task/redirectTask.json
-   参数

| 参数名 | 描述 | 是否必填 | 示例 | 备注 |
| --- | --- | --- | --- | --- |
| appType | 应用ID | 是 | APP_PBKT0MFBEBTDO8T7SLVP | |
| systemToken | 验权token | 是 | | 在[应用数据](https://www.yuque.com/yida/support/ydihkw#Cf3yb)中获取。 |
| language | 语言环境 | 否 | zh_CN | 可选值：zh_CN/en_US |
| processInstanceId | 实例ID | 是 | | 不限制字符串长度，但processInstanceIds 包含的流程实例 ID 数不能超过100个。 |
| byManager | 是否应用管理员进行转交 | 否 | y |
-   可选项 : y/n
-   y,则userId必须传应用管理员工号，或者yida\_pub\_account
-   n, userId必须传任务的当前执行人

 |
| userId | 钉钉的userId | 是 | |
 |
| nowActionerId | 新的任务处理人工号 | 是 | |
 |
| remark | 转交备注 | 是 | |
 |
| taskId | 任务ID | 是 | |
 |

-   返回值：

-   success : 请求是否成功;
-   errorMsg : 错误信息;
-   errorCode : 错误码;
-   errorLevel : 错误级别;

-   返回格式

成功：

```json
{"success":true}
```

---

### 3.11 执行宜搭平台的审批任务

-   接口: /yida_vpc/process/executePlatformTask.json
-   参数

| 参数名 | 描述 | 是否必填 | 示例 | 备注 |
| --- | --- | --- | --- | --- |
| appType | 应用ID | 是 | APP_PBKT0MFBEBTDO8T7SLVP | |
| systemToken | 应用秘钥 | 是 | hexxyyddd | 在[应用数据](https://www.yuque.com/yida/support/ydihkw#Cf3yb)中获取。 |
| userId | 钉钉的userId | 是 | yida_pub_account | 写死 yida_pub_account |
| language | 语言 | 否 | zh_CN | 可选值：zh_CN/en_US 默认：zh_CN |
| procInstId | 流程实例ID | 是 | f30233fb-72e1-4af4-8cb8-c7e0ea9ee530 | |
| outResult | 审批结果 | 是 |
-   agree

-   disagree

 | |
| formDataJson | 更新的表单数据 | 否 | | 参考：附录1保存/更新 表单数据格式说明。 |
| remark | 审批意见 | 是 | 确认同意 | |
| noExecuteExpressions | 是否不执行校验&关联操作 | 否 | y | 本任务节点有绑定校验规则或者关联操作时， y -> 不执行校验规则&关联操作 n -> 执行校验规则&关联操作 不传默认为n，即会执行校验规则&关联操作 |

下面举一个具体的使用示例：

新建一个流程

![[yida_support-lbtl0t-rrwdug-agb8im_1606721991627-d3cc3a56-54bf-4773-8562-8d7409e64aff.png]]

前置审批人根据用户需求设置，需要程序回调执行的审批人需要选择使用角色中的虚拟角色「宜搭平台」，选择完成之后点击「保存」按钮，保存当前最新添加的流程节点。

![[yida_support-lbtl0t-rrwdug-agb8im_1606721991629-bc341dc8-95c0-4667-a309-7c5a14529026.png]]

回到流程设置的最外层，点击「保存并发布」按钮，将整个流程发布

![[yida_support-lbtl0t-rrwdug-agb8im_1606721991814-3a07d8b9-b7c6-42bf-bd3b-a6abb28a66a9.png]]

发起流程之后，一路处理，直到审批流到达「宜搭平台」，此时整个流程会卡主，等待这一虚拟角色的审批

![[yida_support-lbtl0t-rrwdug-agb8im_1606721991838-d976d5cf-c4e9-455a-a42d-b031de57ba79.png]]

可以调用宜搭暴露的「执行虚拟节点任务」的接口 [/yida/process/executePlatformTask.json](https://yuque.antfin-inc.com/docs/share/32c9d578-8aad-4a59-a1b0-71f53e7cccf9?#evqcsm) 来更新该审批节点的处理结果。

相关参数调用 Demo 如下：

![[yida_support-lbtl0t-rrwdug-agb8im_1606721991664-2aa9e870-1be0-47b1-b710-f50cd9bf92f3.png]]

这里重点介绍一下其中的流程实例Id参数proInstId，它表示的是一个审批流的实例，获取方式之一为根据「根据条件搜索流程实例Id」的接口 [/yida/process/getInstanceIds.json](https://yuque.antfin-inc.com/docs/share/32c9d578-8aad-4a59-a1b0-71f53e7cccf9?#9erusv) 接口，设置查询字段 instanceStatus 为RUNNING 以及 searchFieldJson 中某个字段值来搜索到达「宜搭平台」处理的审批节点。

使用虚拟节点而不是某一个真实存在的审批人是保证该审批处理一定是接口侧发起的，系统中的登录人是无法直接执行该审批，提供一个安全性的保障。

---

### 3.12 获取审批记录

-   接口：/yida_vpc/process/getOperationRecords.json

-   参数

| 参数名 | 描述 | 是否必填 | 示例 | 备注 |
| --- | --- | --- | --- | --- |
| appType | 应用ID | 是 | APP_PBKT0MFBEBTDO8T7SLVP | |
| systemToken | 应用秘钥 | 是 | hexxyy | 在[应用数据](https://www.yuque.com/yida/support/ydihkw#Cf3yb)中获取。 |
| userId | 钉钉的userId | 是 | |
 |
| language | 语言 | 否 | zh_CN | 可选值：zh_CN/en_US 默认：zh_CN |
| processInstanceId | 流程实例ID | 是 | f30233fb-72e1-4af4-8cb8-c7e0ea9ee530 | 不限制字符串长度，但processInstanceIds 包含的流程实例 ID 数不能超过100个。 |

-   返回值

-   result :

-   success : 请求是否成功;

-   errorMsg : 错误信息;

-   errorCode : 错误码;

-   返回格式

```json
{"success":true,"content":[{"operateTime":"2018-06-22 14:35:40","remark":"","taskHoldTime":0,"type":"HISTORY","operatorName":"王许川","operator":"WB260752","activityId":"sid-restartevent","action":"提交申请","actionExt":"submit","id":2846866118,"operatorPhotoUrl":"//work.alibaba-inc.com/photo/WB260752.128x128.jpg","processInstanceId":"8c124808-82e7-473b-9a7a-43c29b310837","showName":"提交申请","operateType":"NEW_PROCESS","domains":[],"operatorStatus
