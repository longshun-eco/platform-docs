---
title: "自定义MYSQL"
source: "https://help.h3yun.com/contents/890/1007.html"
category: "開發者手冊 / 后端常用接口示例 / 自定义MYSQL"
updated: 2025-12-25
tags:
  - h3yun
  - 開發者手冊
---
MYSQL的执行（MYSQL版本：5.6.16）

通过Engine.Query()方法查询SQL,返回DataTable表格。

本接口只能执行增删改查sql语句，但是增删改请尽量使用业务对象操作，以防sql对数据操作不当，导致数据错乱。

表单对应数据库表名：i\_表单编码

氚云系统表表名请参考《氚云系统表》

不带Parameter   sql执行示例：

|
string mysql = "SELECT ObjectId,Status FROM i\_D00001ABC where ObjectId='eea54861-b22e-445b-89e2-e7f16a03b07d'"; System.Data.DataTable dtAccount = this.Request.Engine.Query.QueryTable(mysql, null); if(dtAccount != null && dtAccount.Rows != null && dtAccount.Rows.Count > 0) {     //循环数据行     foreach(System.Data.DataRow row in dtAccount.Rows)     {         //获取查询结果 当前行ObjectId字段值         string ObjectId = row\["ObjectId"\] + string.Empty;
        //获取查询结果 当前行Status字段值         int Status = Convert.ToInt32(row\["Status"\]);     } } else {     //查询结果为空 }
 |
| --- |

带Parameter   sql执行示例：

| //本sql中@name即参数名，与H3.Data.Database.Parameter参数对象一一对应 string sql = "SELECT ObjectId FROM h\_user WHERE Name=@name";
//定义参数集合 List < H3.Data.Database.Parameter > parameters = new List<H3.Data.Database.Parameter>();
//创建一个参数 H3.Data.Database.Parameter param = new H3.Data.Database.Parameter(             "@name", //参数名（与sql中的@name一致）             System.Data.DbType.String, //参数值类型             "张三" //参数值     );
//将参数添加到参数集合 parameters.Add(param);
//传入sql和参数查询结果 System.Data.DataTable dt = this.Engine.Query.QueryTable(sql, parameters.ToArray());
/\* 常用参数值类型： System.Data.DbType.String：字符串，对应string System.Data.DbType.Int32：整数，对应int System.Data.DbType.Double：双精度浮点数，对应double System.Data.DbType.Decimal：高精度浮点数，对应decimal System.Data.DbType.Date：日期，对应DateTime System.Data.DbType.DateTime：日期，对应DateTime System.Data.DbType.Boolean：布尔，对应bool \*/ |
| --- |

自定义表单必要说明

表单数据表名：i\_表单编码（注：如果该表单是模板表单或者标准版表单，表单编码应去掉“D00xxx”）

| 序号 | 字段中文名 | 字段英文名 | 特别值说明 |
| --- | --- | --- | --- |
| 1 | 数据Id | ObjectId | |
| 2 | 主表数据标题 | Name | |
| 3 | 数据创建人Id | CreatedBy | |
| 4 | 数据归属人Id | OwnerId | |
| 5 | 数据归属部门Id | OwnerDeptId | |
| 6 | 数据创建时间 | CreatedTime | |
| 7 | 对数据进行最后一次修改的人员id | ModifiedBy | |
| 8 | 对数据进行最后一次修改的时间 | ModifiedTime | |
| 9 | 数据流程id | WorkflowInstanceId | |
| 10 | 数据状态 | Status | 值为0表示 草稿； 值为1表示 生效/流程结束； 值为2表示 流程进行中； 值为3表示 作废。 |
| ... | “表单内控件的值” | 表单中控件的编码 | 控件值未填，数据库存储null |

子表数据表

子表数据表名：i\_子表控件编码

| 序号 | 字段中文名 | 字段英文名 | 特别值说明 |
| --- | --- | --- | --- |
| 1 | 子表数据Id | ObjectId | |
| 2 | 该数据所属主表的数据Id（根据此字段值关联主表数据） | ParentObjectId | |
| 3 | 子表编码 | ParentPropertyName | |
| 4 | 本条数据处在子表第几行 | ParentIndex | 第一行下标：0 第二行下标：1 ... |
| 5 | 子表数据标题 | Name | |
| ... | “子表内控件的值” | 子表中控件的编码（除去子表编码的部分） | 控件值未填，数据库存储null |