---
title: "阿里云ECS服务器部署"
source: "https://open.dingtalk.com/document/dingstart/deployment-alibaba-cloud-ecs-server"
category: "新手指南 / 实践教程 / OpenClaw / OpenClaw常用部署方式"
updated: 
tags:
  - dingtalk
  - 新手指南
---
![[dingstart-deployment-alibaba-cloud-ecs-server_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[dingstart-deployment-alibaba-cloud-ecs-server_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-03-12

## **前提条件**

* 已经完成了钉钉应用和机器人的创建与发布。
* 已经获取了钉钉应用的Client ID和Client Secret，用于后续使用。
* 通过快捷方式创建的OpenClaw机器人已自动获得`Card.Streaming.Write`、`Card.Instance.Write`和`qyapi_robot_sendmsg`权限点。

## **操作步骤**

### **获取 API Key**

为了在体验初期避免产生超出预期的费用，可以使用[Coding Plan](https://help.aliyun.com/zh/model-studio/coding-plan)，每 5 小时刷新指定额度。

1. 访问 [Coding Plan 购买页](https://www.aliyun.com/benefit/scene/codingplan)，选择 Lite 基础套餐（体验推荐），完成购买。
2. 购买成功后，访问[Coding Plan API Key 管理页](https://bailian.console.aliyun.com/cn-beijing/?spm=a2c4g.29338759.0.0.725130b3A7p8mc&tab=model#/efm/coding_plan)，生成并保存 API Key。

   ![[dingstart-deployment-alibaba-cloud-ecs-server_p1055499.png]]

### **购买 ECS服务器**

**推荐套餐**：e 实例，2 核 2 GB，99 元/年起，个人开发者首选。新用户也可领取 [ECS 免费试用](https://free.aliyun.com/)。

1. 访问 [阿里云 ECS 产品页](https://www.aliyun.com/product/ecs?spm=a2c4g.29338759.0.0.3d8130b3stFgzt)，找到 **e 实例** 套餐，单击**立即购买**。
2. 配置以下参数，其他参数保持默认即可。

   |  |  | | --- | --- | | 参数 | 说明 | | 地域 | 选择离您最近的地域，例如华东1（杭州） | | 镜像 | 选择 Alibaba Cloud Linux 3 |
3. 确认订单并完成支付，等待实例创建完成。

   **说明**

   如果希望使用其他方式创建的 ECS 实例，请确保为该实例分配了公网 IP 或绑定了弹性公网 IP。

### **连接服务器**

1. 进入 [ECS 管理控制台](https://ecs.console.aliyun.com/)，找到目标实例，单击操作列的远程连接。

   ![[dingstart-deployment-alibaba-cloud-ecs-server_p1055500.png]]
2. 选择 **Workbench 远程连接**，单击**立即登录**，选择免密登录进入终端。

   ![[dingstart-deployment-alibaba-cloud-ecs-server_p1055501.png]]

### **部署并验证**

1. 在 Workbench 终端中执行部署脚本：

   ```bash
   curl -fsSL https://help-static-aliyun-doc.aliyuncs.com/file-manage-files/zh-CN/20260225/vdwoyc/openclaw_installer.sh -o openclaw_installer.sh && bash openclaw_installer.sh
   ```
2. 执行部署脚本后会出现以下选项，选择“安装 `Openclaw（Install）`”，脚本会开始安装过程，此过程预计持续 10 分钟。

   ![[dingstart-deployment-alibaba-cloud-ecs-server_p1055333.png]]

   出现“安装完成”提示后，说明`OpenClaw`及其运行环境安装成功。

   ![[dingstart-deployment-alibaba-cloud-ecs-server_p1055334.png]]
3. 安装完成后进入配置向导，请根据提示依次输入以下信息：

   * **选择渠道**：钉钉（DingTalk）
   * **钉钉 Client ID**：步骤二获取的 Client ID
   * **钉钉 Client Secret**：步骤二获取的 Client Secret
   * **百炼 Base URL**：直接回车使用默认值
   * **百炼 API Key**：提前获取的 Coding Plan API Key
   * **AI 模型**：直接回车使用默认值
4. 完成上述配置后，脚本会自动完成以下操作：

   * 生成配置文件~/.openclaw/openclaw.json
   * 启动服务，并生成openclaw的后台管理界面的链接：http://127.0.0.1:18789/?token=your\_gateway\_token

     **说明**

     如需从本地计算机访问`openclaw`的后台管理界面，参见[如何访问 OpenClaw Control UI](https://www.aliyun.com/solution/tech-solution/clawdbot/3018681#4175799beeg8k)。
5. 看到配置完成的总结框后，请保存脚本输出的 Gateway Token，后续维护可能需要使用。

   ![[dingstart-deployment-alibaba-cloud-ecs-server_p1055335.png]]
6. 验证服务状态：选择“查看状态 (Status)”，如果部署成功，将显示各个组件的状态为：

   ```
    核心组件
     └─ Openclaw     ✓ yyyy.m.dd (最新)

     渠道插件
     └─ 钉钉         ✓ x.y.z (最新) [clawdbot-dingtalk]

     服务状态
     └─ Gateway      ✓ 运行中

     配置文件
     └─ 配置文件     ✓ ~/.openclaw/openclaw.json
   ```

## **常见问题**

### **机器人不回复消息怎么办？**

1. 检查容器是否正常运行：

   执行部署脚本，选择“查看状态 (Status)”。

   ```
   bash openclaw_installer.sh
   ```

   确保各个组件处于正常状态。
2. 继续在脚本中选择“修复问题 (Repair)”，运行自动诊断，查看是否存在配置问题。
3. 查看日志：

   日志路径：

   ```
   openclaw logs
   ```

   常见错误及解决方法：

   |  |  |  | | --- | --- | --- | | 错误信息 | 原因 | 解决方法 | | invalid client\_id | Client ID 错误 | 运行 `bash openclaw_installer.sh` 重新配置钉钉凭证 | | invalid client\_secret | Client Secret 错误 | 运行 `bash openclaw_installer.sh` 重新配置钉钉凭证 | | unauthorized | API Key 无效 | 运行 `bash openclaw_installer.sh` 重新配置 API Key |
4. 确认钉钉应用已发布且机器人已添加到群聊。