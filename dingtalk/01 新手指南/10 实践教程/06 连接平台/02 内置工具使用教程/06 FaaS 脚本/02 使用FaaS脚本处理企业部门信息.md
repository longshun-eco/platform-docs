---
title: "使用FaaS脚本处理企业部门信息"
source: "https://open.dingtalk.com/document/dingstart/enterprise-department-information"
category: "新手指南 / 实践教程 / 连接平台 / 内置工具使用教程 / FaaS 脚本"
updated: 
tags:
  - dingtalk
  - 新手指南
---
![[dingstart-enterprise-department-information_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[dingstart-enterprise-department-information_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-01-22

## **前提条件**

1. 拥有所在钉钉组织开发者后台的[开发者权限](/document/dingstart/get-developer-permissions)。
2. 已开通钉钉专业版。

## 操作步骤

1. 登录[钉钉开发者后台](https://open-dev.dingtalk.com/)。
2. 单击**开放能力** > **连接平台** > **我的连接** > **我的连接流** > **创建连接流**。
3. 配置触发事件，选择**内置工具** > **webhook** > **当接受到数据时触发，**无需配置参数。
4. 配置执行动作（节点2），选择**官方连接器** > **通讯录** > **获取部门列表**，无需配置参数。
5. 配置执行动作（节点3），选择**内置工具 > FaaS脚本 > Python脚本**，并配置参数：

   ![[dingstart-enterprise-department-information_p754334.png]]

   |  |  | | --- | --- | | **配置项** | **值** | | 设置脚本入参变量（deptInfos） | 选择**引用值** > **节点2：查询结果**。 | | Python脚本代码 | 编写如下脚本代码，遍历通讯录查询到的部门列表，将部门名称和对应的部门 ID 拼接到字符串 result 中，最终添加到 output 输出变量中作为出参字段：  ``` # 从节点2返回的deptInfos中获取部门列表deptList deptList = input["deptInfos"].get("result")  # 遍历deptList，将部门名称开头为连接器的部门name和ID添加到result字符串中 result = "部门名称及对应ID: \n" for dept in deptList:     name = dept.get("name")     deptId = dept.get("dept_id")     if name.startswith("连接器"):         result += "    " + name + ": "+ str(deptId) +"\n"      # 将遍历结果添加到输出output中 output = {"result": result} ```  **说明**  相同业务逻辑的Nodejs脚本如下，执行动作选择为**Nodejs脚本**时可用。  ``` var deptList = input.deptInfos.result; var result = ""; deptList   .filter((dept) => dept.name.startsWith("连接器"))   .forEach((dept) => {     result = result + "    " + dept.name + ": " + dept.dept_id + "\n";   }); output.result = result; ``` |
6. 配置执行动作（节点4），选择**官方连接器 > 机器人 > 发送机器人消息到群[文本消息]**，并配置参数：

   |  |  | | --- | --- | | **配置项** | **值** | | accessToken | 选择输入值，机器人添加入群后，机器人webhook地址的access\_token的值，可参考[机器人（access\_token）](/document/connection/official-connector-generic-field-acquisition-1#bab98990ffdym)。 | | 文本消息 | 选择**引用值**，设置**节点3：出参.result**。 |
7. 单击**保存草稿** > **调试**，查看调试效果。

   1. 保存并调试：

      ![[dingstart-enterprise-department-information_p754347.png]]
   2. 查看调试效果：

      ![[dingstart-enterprise-department-information_p754349.png]]
8. 调试完成后，单击**发布**。