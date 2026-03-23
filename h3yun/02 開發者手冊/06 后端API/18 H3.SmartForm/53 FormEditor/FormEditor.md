---
title: "FormEditor"
source: "https://help.h3yun.com/contents/613/800.html"
category: "開發者手冊 / 后端API / H3.SmartForm / FormEditor"
updated: 2025-12-20
tags:
  - h3yun
  - 開發者手冊
---
类名 : FormEditor
说明 : 表单HTML操作类 属性 : 

| 名称 | 说明 |
| --- | --- |
| ControlProperties | 属性集合 |



成员 : 

| 名称 | 说明 |
| --- | --- |
| PropertyName\_ControlKey | 控件类型 |
| PropertyName\_DisplayRule | 显示规则 |
| PropertyName\_ConputationRule | 计算规则 |
| PropertyName\_DataMode | 显示模式【邮箱，身份证，电话号码】 |
| PropertyName\_InputByScan | 是否扫码录入 |
| PropertyName\_ScanUpdateEnable | 是否允许扫码更新 |
| PropertyName\_BoSchemacode | 关联表单 |
| PropertyName\_MappingControls | 映射属性 |
| PropertyName\_AssociationFilter | 关联过滤条件 |
| PropertyName\_DecimalChecked | 小数点检查 |
| PropertyName\_DecimalPlaces | 小数点位数 |
| PropertyName\_UserVisible | 是否可以选择用户属性(兼容旧版) |
| PropertyName\_OrgUnitVisible | 是否可以选择部门属性(兼容旧版) |
| PropertyName\_DataSource | 下拉框的数据源,自定义/关联表单 |
| PropertyName\_DataField | 拥有者,所属部门 |
| PropertyName\_DateTimeModel | 日期控件格式属性 |
| PropertyName\_AreaMode | 地址控件格式属性 |


方法名称 : ExistControl(H3.SmartForm.FormSetting,System.String)

| 参数 | 说明 |
| --- | --- |
| "formSetting" | 表单配置 |
| "datafield" | 字段编码 |
| 返回值 |  |
| 是否存在 |  |


方法名称 : GetControl(H3.SmartForm.FormSetting,System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "formSetting" | 表单配置 |
| "datafield" | 字段编码 |
| "isRunTimeContent" | 是获取运行时内容还是设计内容 |
| 返回值 |  |
| 获取的控件HTML |  |


方法名称 : GetControlProperties(H3.SmartForm.FormSetting,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "formSetting" | |
| "isRunTimeContent" | |
| 返回值 |  |
| |  |


方法名称 : AddControl(H3.SmartForm.FormSetting,System.String,System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "formSetting" | 表单设置 |
| "preDataField" | 主表字段或子表字段，控件插入到主表或子表的最后位置 |
| "controlHtml" | 新增控件HTML |
| "isRuntimeContent" | 是否是更新运行时内容 |
| 返回值 |  |
| |  |


方法名称 : RemoveControl(H3.SmartForm.FormSetting,System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "formSetting" | 表单配置 |
| "datafield" | 字段编码 |
| "isUpdateRuntimeContent" | 是更新运行时html还是更新设计时HTML |
| 返回值 |  |
| |  |


方法名称 : UpdateControlProperty(H3.SmartForm.FormSetting,System.String,System.String,System.String)

| 参数 | 说明 |
| --- | --- |
| "formSetting" | 表单配置 |
| "datafield" | 字段编码 |
| "propertyName" | 属性编码 |
| "propertyValue" | 属性值 |
| 返回值 |  |
| 是否已经更新 |  |


方法名称 : GetControlProperty(H3.SmartForm.FormSetting,System.String,System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "formSetting" | 表单配置信息 |
| "datafield" | 字段编码 |
| "propertyName" | 属性编码 |
| "isRuntimeContent" | 是否获取运行时的html |
| 返回值 |  |
| 返回对应的html代码 |  |


方法名称 : ParserNodes(Winista.Text.HtmlParser.Util.NodeList)

| 参数 | 说明 |
| --- | --- |
| "htmlNodes" | 节点NodeList |
| 返回值 |  |
| 数据项与NodeList的字典 |  |


方法名称 : ParseHtml(System.String)

| 参数 | 说明 |
| --- | --- |
| "html" | html代码 |
| 返回值 |  |
| 解析HTML后的树节点 |  |


方法名称 : UpdateHtml(Winista.Text.HtmlParser.INode,System.String,Winista.Text.HtmlParser.INode,System.Boolean,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "htmlNode" | html节点 |
| "datafield" | 数据项编码 |
| "newNode" | 新节点 |
| "siblingRequired" | 是否更新兄弟节点 |
| "removeNode" | 是否删除节点 |
| 返回值 |  |
| 是否更新成功 |  |


方法名称 : GetPreControlName(H3.SmartForm.FormSetting,System.String,System.Boolean)

| 参数 | 说明 |
| --- | --- |
| "formSetting" | |
| "addCrotrolName" | |
| "isRuntimeContent" | |
| 返回值 |  |
| |  |


方法名称 : GetPreNode(Winista.Text.HtmlParser.Util.NodeList,System.String)

| 参数 | 说明 |
| --- | --- |
| "nodeList" | |
| "datafield" | |
| 返回值 |  |
| |  |


方法名称 : GetPreNodeStr(Winista.Text.HtmlParser.INode,System.String,System.Collections.Generic.List{System.String})

| 参数 | 说明 |
| --- | --- |
| "node" | |
| "datafield" | |
| "listDataField" | |
| 返回值 |  |
| |  |


方法名称 : AddControlByPreDataField(H3.SmartForm.FormSetting,System.String,System.String,System.Boolean,System.Int32)

| 参数 | 说明 |
| --- | --- |
| "formSetting" | 表单设置 |
| "preDataField" | 主表字段或子表字段，控件插入到主表或子表的最后位置 |
| "controlHtml" | 新增控件HTML |
| "isRuntimeContent" | 是否是更新运行时内容 |
| "insertInfo" | 添加到主表第一个值为1 |
| 返回值 |  |
| |  |