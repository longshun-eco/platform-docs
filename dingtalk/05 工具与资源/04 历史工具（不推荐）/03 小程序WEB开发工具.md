---
title: "小程序WEB开发工具"
source: "https://open.dingtalk.com/document/download/small-program-web-development-tool"
category: "工具与资源 / 历史工具（不推荐）"
updated: 
tags:
  - dingtalk
  - 工具与资源
---
![[download-small-program-web-development-tool_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[download-small-program-web-development-tool_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-11-20为帮助开发者提升开发钉钉小程序的效率，钉钉提供了小程序web开发工具，帮助开发者在浏览器中开发调试小程序，无需再下载小程序开发IDE。欢迎下载体验。

**重要**

请正在使用小程序WEB开发工具的各开发者注意：后续该工具将不再维护，如需开发小程序请使用[小程序开发工具](/document/download/miniapp-tool)。

## 视频教程

[](https://help-static-aliyun-doc.aliyuncs.com/file-manage-files/zh-CN/20220411/kckz/miniappDemo.mp4)

## 准备工作

在正式开发前，请确保你已完成了以下的准备工作：

* 确保安装了项目管理工具Git。若未安装，请访问[Git官网](https://git-scm.com/downloads)下载并安装。
* 确保已经创建小程序。如果未创建，请参考[创建应用](/document/dingstart/create-application)，并选择创建小程序。

## 步骤一：下载工具

通过执行以下命令，安装cli-beta版本。

```bash
npm i dingtalk-design-cli@1.0.0-beta.1 -g
```

## 步骤二：初始化项目

### 若您尚未创建小程序项目。

可以通过执行以下命令初始化小程序项目。

```
ding init
```

项目初始化配置，如下图所示：

![[download-small-program-web-development-tool_p428994.png]]

* **应用类型**：选择**小程序**。
* **选择模板**：默认为**default**。
* **选择开发语言**：默认为**javascript**。

使用DingTalk Design CLI初始化项目后，项目目录下会包含一个`ding.config.json`配置文件。`ding.config.json`包含的字段如下：

|  |  |
| --- | --- |
| 参数 | 说明 |
| type | 应用为mp(小程序)类型。 |
| typesctipt | 是否为一个TypeScript项目。 |
| base | 源代码目录。 |
| outDir | 产出代码目录。  **说明**  一般情况下，JavaScript项目中填`outDir: './'`即可，TypeScript项目中填入构建后的产出目录。 |

### 若您已有小程序项目

可以在项目中新增ding.config.json文件，新增该配置文件后，也可使用web工具调试。参考配置如下：

```json
{
 "type": "mp",
 "typescript": false
}
```

## 步骤三：开始调试

执行以下命令，开始项目的web开发调试。

```
ding dev web
```

## 步骤四：修改项目配置

**说明**

正确配置API Token和miniAppId参数，用于后续上传项目使用。

### 1.获取API Token

（1）登录[开发者后台](https://open-dev.dingtalk.com/)。

（2）如果是首次使用API TOKEN，在开发者后台首页，单击**生成TOKEN**，用于生成持久的API Token。

**说明**

* 重新生成Token之后，之前的Token会失效。
* 同一企业同一时间生效的Token只有一个。

![[download-small-program-web-development-tool_p283653.png]]

（3）生成API Token后，**单击**Token值，进行复制。

![[download-small-program-web-development-tool_p430186.png]]

### 2.获取小程序的miniAppId

![[download-small-program-web-development-tool_p286472.png]]

### 3.修改配置

根据获取API token和miniAppId值，执行以下命令，修改ding.config.json文件。

```
ding dev updateConfig token c7b8fc172007373xxx
```

```
ding dev updateConfig miniAppId 5000000002xxx
```

修改配置文件完成后的内容如下：

```json
{
  "type": "mp",
  "typescript": false,
  "base": "./",
  "outDir": "./",
  "token":"c7b8fc1720073730a230b5762873000d",
  "miniAppId":"5000000002672704"
}
```

## 步骤五：上传小程序

通过执行以下命令，上传小程序版本。

```
ding upload
```

上传项目，如图所示：

![[download-small-program-web-development-tool_p429005.png]]

上传完成后，登录[开发者后台](https://open-dev.dingtalk.com/)，进入miniAppId对应的小程序应用，查看版本管理与发布，可查看上传的版本。

![[download-small-program-web-development-tool_p429007.png]]