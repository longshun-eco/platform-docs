---
title: "微应用调试工具-IDE"
source: "https://open.dingtalk.com/document/download/micro-application-debugging-tools-ide"
category: "工具与资源 / 历史工具（不推荐） / 微应用调试工具"
updated: 
tags:
  - dingtalk
  - 工具与资源
---
![[download-micro-application-debugging-tools-ide_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[download-micro-application-debugging-tools-ide_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-11-17本文介绍了如何使用IDE在钉钉端内调试正在开发或已开发完成的H5微应用。

**重要**

请正在使用微应用调试工具-IDE的各开发者注意：后续该工具将不再维护且不再支持新用户下载，开发H5微应用可以使用[Visual Studio Code](https://code.visualstudio.com/)，开发小程序可以使用[小程序开发工具](/document/download/miniapp-tool)，若需调试可使用[微应用四端调试工具—网页版](/document/download/micro-application-four-terminal-debugging-tool-web-edition)或[vConsole](https://www.kancloud.cn/york_web/web_node_plugin_document/2232008)代替。

## **使用流程**

1. 登录已下载的钉钉开发者工具。

   ![[download-micro-application-debugging-tools-ide_p551289.png]]
2. 打开H5微应用，有两种打开方式，任选其一。

   * 通过应用管理打开H5微应用，鼠标悬停在需要打开的H5微应用上，点击打开按钮。填写备份目录，**该目录填写微应用在本地的项目代码目录**。

     ![[download-micro-application-debugging-tools-ide_p551291.png]]
   * 通过右上角打开H5微应用在本地的项目目录。

     ![[download-micro-application-debugging-tools-ide_p551292.png]]
3. 启动项目，点击右上角模拟器按钮。

   ![[download-micro-application-debugging-tools-ide_p551425.png]]
4. 点击模拟器内的编译设置按钮。

   ![[download-micro-application-debugging-tools-ide_p551426.png]]
5. 填写模拟器设置信息，填写项目的启动配置后，点击保存。

   **说明**

   编译功能依赖当前机器环境，请确保配置的命令和端口可在当前环境下运行，否则将无法运行。

   ![[download-micro-application-debugging-tools-ide_p558428.png]]
6. 点击启动编译按钮。

   **说明**

   编译进行时，可点击**查看日志**。

   ![[download-micro-application-debugging-tools-ide_p558433.png]]

   ![[download-micro-application-debugging-tools-ide_p558369.png]]
7. 开始调试，点击编译器的预览按钮，选择**在钉钉工作台打开**的方式。

   ![[download-micro-application-debugging-tools-ide_p558374.png]]
8. 跳转到钉钉客户端内工作台，打开该微应用页面，并点击右下角按钮可进入调试。

   ![[download-micro-application-debugging-tools-ide_p558432.png]]
9. 调试效果如下图所示。

   ![[download-micro-application-debugging-tools-ide_p558431.png]]

## **常见问题**

### **Q：模拟器启动时报JSAPI相关错误**

A：模拟器内暂不支持本地调试JSAPI，需要使用钉钉客户端打开本地页面后才能调试（如何打开可查看上述文档的第8步）。

### **Q：模拟器安装npm包失败**

A：由于存在系统环境差异，可以打开终端手动执行npm install，成功安装npm包后，再使用模拟器启动编译。