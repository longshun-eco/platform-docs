---
title: "webservice"
source: "https://help.h3yun.com/contents/1126/2234.html"
category: "開發者手冊 / 系统集成接口 / 氚云调用第三方接口 / webservice"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
1.  氚云后端代码，做个中间层webservice，通过webservice去调用第三方返回数据，在将数据转义为JSON字符串，以SOAP协议回传给氚云。

总体业务流程图如下：

![[2234_947457bdf546b256.png]]

  2. webservice规范性：只能有4个同名接口，大小写都要一致，返回类型都为JSON字符串。对应关系如下表:

| 序号 | 函数 |
| --- | --- |
| 1 | GetSchema(string schemaCode) |
| 2 | GetSchemaList() |
| 3 | GetList(string userCode, string   schemaCode, string filter) |
| 4 | Invoke(string userCode, string   schemaCode, string methodName, string param) |

示例（C#）：

| namespace   DingtalkWebService {       /// <summary>       /// DingWebService 的摘要说明       /// </summary>       \[WebService(Namespace = "http://tempuri.org/")\]       \[WebServiceBinding(ConformsTo = WsiProfiles.BasicProfile1\_1)\]       \[System.ComponentModel.ToolboxItem(false)\]       // 若要允许使用 ASP.NET AJAX 从脚本中调用此 Web 服务，请取消注释以下行。       // \[System.Web.Script.Services.ScriptService\]       public class DingWebService :   System.Web.Services.WebService       {           \[WebMethod\]           public string   GetSchema(string schemaCode)           {             return string.Empty;//返回JSON字符串           }           \[WebMethod\]           public string   GetSchemaList()           {             return string.Empty;//返回JSON字符串           }             \[WebMethod\]           public string   GetList(string userCode, string   schemaCode, string filter)           {             return string.Empty;//返回JSON字符串           }             \[WebMethod\] //氚云后端调用的方法名           public string   Invoke(string userCode, string   schemaCode, string methodName, string   param)           { //书写调用第三方接口方法               return string.Empty;//返回JSON字符串           }       } } |
| --- |

Invoke方法返回的JSON字符串格式

| {"ResultCode":"0",   "Message":"",   "Schema":{"Code":"Student","Items":\[{"Name":"Name","DisplayName":"学生姓名","DataType":"String"},{"Name":"Age","DisplayName":"学生年龄","DataType":"Int"},{"Name":"ReturnData","DisplayName":"子表数据","DataType":"BizStructureArray","ChildSchema":{"Code":"ResultObject","Items":\[{"Name":"ResultCode","DisplayName":"执行结果代码","DataType":"Int"},{"Name":"ErrorMessage","DisplayName":"异常原因","DataType":"String"}\]}}\]},   "Data":{"Name":"张三","Age":"10","ReturnData":\[{"ResultCode":"0","ErrorMessage":"0"},{"ResultCode":"1","ErrorMessage":"1"}\]}} |
| --- |

  3.  氚云系统集成-接入第三方系统的配置：将书写好的webservice挂载到服务器上，发布访问的webservice地址（外网要能访问）,在将该地址配置‘接入通用系统 ’，如下图所示：

![[2234_478fb0472b42b256.png "image.png"]]

![[2234_634f7321799e5989.png "157cc53471ff2aa.png"]]

![[2234_5578a5d2344412a8.png]]

![[2234_d7157dad78392923.png]]

注意若webservice书写的不规范，则会显示连接失败。

  4. 氚云后端调用webservice方法：Invoke

示例：

|           //定义传输结构-主表           H3.BizBus.BizStructureSchema paramSchema = new   H3.BizBus.BizStructureSchema();           paramSchema.Add(new H3.BizBus.ItemSchema("BillsCustomer",   "客户", H3.Data.BizDataType.ShortString, 200,   null));           paramSchema.Add(new H3.BizBus.ItemSchema("TotalMoney",   "总计", H3.Data.BizDataType.Double, 200,   null));           //定义传输结构-子表           H3.BizBus.BizStructureSchema detailsSchema = new   H3.BizBus.BizStructureSchema();           detailsSchema.Add(new H3.BizBus.ItemSchema("Type", "收款类型", H3.Data.BizDataType.ShortString, 200, null));           detailsSchema.Add(new H3.BizBus.ItemSchema("Money", "金额", H3.Data.BizDataType.Double, 200, null));           //主表赋值           paramSchema.Add(new H3.BizBus.ItemSchema("details", "明细", H3.Data.BizDataType.BizStructureArray, detailsSchema));//子表添加到主表           H3.BizBus.BizStructure paramData = new   H3.BizBus.BizStructure(paramSchema);           paramData\["BillsCustomer"\] = "chen";           paramData\["TotalMoney"\] = 123;           //子表赋值           List < H3.BizBus.BizStructure > detailsDatas=new   List<H3.BizBus.BizStructure>();           for(int k = 0;k < 2; k++)           {             H3.BizBus.BizStructure   detailsData = new H3.BizBus.BizStructure(detailsSchema);             detailsData\["Type"\] =   "氚云";             detailsData\["Money"\] =   11;             detailsDatas.Add(detailsData);           }           //子表的值赋值给主表           paramData\["details"\] = detailsDatas.ToArray();             //调用Invoke接口，系统底层访问第三方WebService接口的Invoke方法           H3.BizBus.InvokeResult InResult = this.Engine.BizBus.Invoke(H3.Organization.User.SystemUserId,   H3.BizBus.AccessPointType.Legacy, this.Request.SchemaCode, "自定义参数", paramData);           if(InResult != null)           {             int Code = InResult.Code; //调用是否成功             if(Code == 0)               {                 //获取返回数据                 H3.BizBus.BizStructure Obj =   InResult.Data;             }             else             {                 //获取错误信息                 string ErrorMessage =   InResult.Message;             }           } |
| --- |