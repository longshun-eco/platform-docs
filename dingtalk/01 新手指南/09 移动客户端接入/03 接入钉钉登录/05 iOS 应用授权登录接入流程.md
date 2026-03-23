---
title: "iOS 应用授权登录接入流程"
source: "https://open.dingtalk.com/document/dingstart/mini-app-procedures-for-authorized-logon-to-ios-applications"
category: "新手指南 / 移动客户端接入 / 接入钉钉登录"
updated: 
tags:
  - dingtalk
  - 新手指南
---
![[dingstart-mini-app-procedures-for-authorized-logon-to-ios-applications_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[dingstart-mini-app-procedures-for-authorized-logon-to-ios-applications_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-23

## 准备工作

在使用移动应用接入钉钉登录之前，你需要完成以下准备工作：

* 搭建 iOS 开发环境。
* 下载 [ADTOpenAuthSDK\_0.0.1.29.zip](https://help-static-aliyun-doc.aliyuncs.com/file-manage-files/zh-CN/20250710/ipmytb/ADTOpenAuthSDK_0.0.1.29.zip)
* Demo参考[ADTOpenAuthDemo .zip](https://help-static-aliyun-doc.aliyuncs.com/file-manage-files/zh-CN/20250103/jbjajn/ADTOpenAuthDemo%2B.zip)
* 安装钉钉客户端。

**说明**

* ADTOpenAuthSDK 部署系统版本为 iOS 12.0 及以上。
* 下载并使用本 SDK ，即表示您已阅读并同意《[钉钉开放平台隐私权政策](/document/services/open-latform-privacy-policy)》、《[钉钉开放平台开发者服务协议](/document/services/open-platform-developer-service-agreement)》。
* 请将钉钉版本升级到 7.1.16 及以上。

## 业务流程

![[dingstart-mini-app-procedures-for-authorized-logon-to-ios-applications_p899369.png]]

## 步骤一：**创建并配置钉钉应用**

* 进入[开放平台-开发者后台](https://open-dev.dingtalk.com/)，单击**应用开发**，选择需要接入登录的应用。

  ![[dingstart-mini-app-procedures-for-authorized-logon-to-ios-applications_p740485.png]]
* 在**凭证与基础信息**中，记录应用的 **Client ID** 。

  ![[dingstart-mini-app-procedures-for-authorized-logon-to-ios-applications_p740486.png]]
* 在**分享设置-接入登录**中，填写自定义重定向 URL 。

  ![[dingstart-mini-app-procedures-for-authorized-logon-to-ios-applications_p740487.png]]

  **说明**

  1、在授权登录过程中，钉钉会校验授权接口的参数redirectUri，与此处配置的域名是否一致。

  2、回调地址中不要带#号，否则会导致钉钉无法回调。比如下面链接不建议填写：

  https://www.dingtalk.com/auth/#/

  建议填写成

  https://www.dingtalk.com/auth
* 在**分享设置-接入分享**中，如果启用iOS分享，则需要填写iOS BundleId, 务必和正式版保持一致

  ![[dingstart-mini-app-procedures-for-authorized-logon-to-ios-applications_p745935.png]]

## 步骤二：搭建开发环境

* 将已下载的文件解压，在对应 target 的 Build Phases 中点加号把 xcframework 导入到工程中

  ![[dingstart-mini-app-procedures-for-authorized-logon-to-ios-applications_p748680.png]]

  ![[dingstart-mini-app-procedures-for-authorized-logon-to-ios-applications_p748702.png]]
* 修改 info.plist：

  + CFBundleURLType 下新增项：

    - URL identifier 填 dingtalk 。
    - URL scheme 新增项，值为开放平台对应应用的 **Client ID**，用于鉴权后跳回业务方 app
  + （可选）LSApplicationQueriesSchemes 下添加白名单 dingtalk、dingtalk-openauth、dingtalk-openauth2 ，用于检测钉钉安装状态。

    **说明**

    iOS系统限制 LSApplicationQueriesSchemes 最多只能有50个，超出部分有可能不生效。尤其是 Xcode 13 打包，iOS 15.0 及以上，超出部分不生效。

  ![[dingstart-mini-app-procedures-for-authorized-logon-to-ios-applications_p745939.png]]
* 相关方法实现

  + 在 app 启动阶段，调用`registerApp:identifier:`方法注册业务方基本信息。

    **说明**

    其中 appId 为开放平台对应应用的 **Client ID**，identifier 为保证独一无二，填写 app 的 **bundleId。**

    ```
    @interface AppDelegate ()

    @end

    @implementation AppDelegate

    - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {

        [ADTOpenAuthAPI registerApp:kOpenAppId
                         identifier:kOpenBundleId];

        //...

        return YES;
    }
    ```

    如果使用SceneDelegate，使用下面回调方法

    ```
    @interface SceneDelegate ()
    @end

    @implementation SceneDelegate

    - (void)scene:(UIScene *)scene willConnectToSession:(UISceneSession *)session options:(UISceneConnectionOptions *)connectionOptions {
        // 创建窗口和根视图控制器
        if ([scene isKindOfClass:[UIWindowScene class]]) {
            [ADTOpenAuthAPI registerApp:kOpenAppIdV2
                             identifier:kOpenBundleIdV2];
            //...
        }
    }
    ```
  + 在 openURL 入口调用 AuthAPI 的`handleOpenURL:delegate:`方法处理授权结果，并将 AppDelegate 设为代理。

    ```
    - (BOOL)application:(UIApplication *)app
                openURL:(NSURL *)url
                options:(NSDictionary *)options {

        if ([ADTOpenAuthAPI handleOpenURL:url
                                 delegate:self]) {
            return YES;
        }

        return NO;
    }
    ```

    如果使用SceneDelegate，使用下面回调方法

    ```
    - (void)scene:(UIScene *)scene openURLContexts:(NSSet *)URLContexts {
        // 处理 URL 打开
        for (UIOpenURLContext *context in URLContexts) {
            NSURL *url = context.URL;
            // 处理 URL 逻辑
            if ([ADTOpenAuthAPI handleOpenURL:url
                                     delegate:self]) {
                NSLog(@"handle success url=%@", url);
            }
        }
    }
    ```
  + AppDelegate或SceneDelegate 实现代理协议方法，SDK 在拿到鉴权结果后会在`onResp:`方法中回调，如果成功会返回 authCode 授权码，用于业务方服务端做 SSO 鉴权。

    ```
    @interface AppDelegate ()

    //...

    #pragma mark ADTOpenAuthAPIDelegate

    - (void)onResp:(ADTBaseResp *)resp {
        if ([resp isKindOfClass:[ADTOpenAuthResp class]]) {
            ADTOpenAuthResp *authResp = (ADTOpenAuthResp *)resp;

            NSString *authCode = authResp.authCode;

            // 将授权码 authCode 交给服务端做SSO鉴权
        }
    }
    ```

## 步骤三：授权登录

* 发起登录鉴权

  + 在需要登录的业务场景调用`sendReq:onViewController:`方法发起登录鉴权，如果在 LSApplicationQueriesSchemes 条目中添加了钉钉跳转白名单，会优先尝试跳转钉钉进行鉴权，否则吊起应用内 H5 页面进行鉴权。请求中的参数 redirectUrl需要与开放平台配置的重定向 URL 保持一致。

    ```
    - (void)tryAuthLogin {
        ADTOpenAuthReq *req = [ADTOpenAuthReq new];
        // 必选参数
        req.redirectUrl = @"https://www.dingtalk.com/auth";
        req.responseType = @"code";
        req.scope = @"openid corpid";
        req.prompt = @"consent";
        // 建议添加一个随机数，作用见下面文档
        //req.state = @"defaultState";

        //当H5授权时，会使用此viewController做present一个网页；如果传nil，会导致无法打开授权H5网页.
        BOOL result = [ADTOpenAuthAPI sendReq:req onViewController:self];
        if (result) {
            NSLog(@"授权登录 发送成功.");
        }
        else {
            NSLog(@"授权登录 发送失败.");
        }
    }
    ```

    **参数说明：**

    |  |  |  | | --- | --- | --- | | 参数 | 是否必填 | 备注 | | appId | 是 | 钉钉开放平台应用标识，即第一步中获取的AppKey。 | | redirectUri | 是 | 创建应用时填写的回调域名，仅用于校验域名是否一致，不会跳转。  **说明**  需要与创建应用时填写的回调域名保持一致。 | | responseType | 是 | 当前只支持固定值code，授权通过后返回authCode。 | | scope | 是 | 应用授权作用域。授权页面显示的授权信息以应用注册时配置的为准  当前只支持两种输入：  - "openid"：授权后可获得用户openid。 - "openid corpid"：授权后可获得用户openid和登录过程中用户选择的组织corpId。 | | nonce | 否 | 字段值任意填写，授权登录后原样返回。 | | state | 否 | 用于保持请求和回调的状态，授权请求后原样带回给第三方。  **说明**  该参数可用于防止csrf攻击（跨站请求伪造攻击），建议第三方带上该参数，可设置为简单的随机数加session进行校验。 | | prompt | 否 | 固定值为consent，会进入授权确认页。 |
* 获取 accessToken，accessToken 是登录用户的访问凭证。

  + 根据 authCode 调用接口获取 accessToken，由业务方服务端接入，可参考[接入文档](/document/development/obtain-user-token)。
  + 客户端本地可以通过[接口调试工具](https://open-dev.dingtalk.com/apiExplorer?spm=ding_open_doc.document.0.0.2bd4492dQuxTUk#/?devType=isv&api=oauth2_1.0%23GetUserToken)进行调试，
* 获取用户通讯录相关信息

  + 根据 accessToken 调用接口获取用户通讯录相关信息，由业务方服务端接入，可参考[接入文档](/document/development/dingtalk-retrieve-user-information)。
  + 客户端本地可以通过[接口调试工具](https://open-dev.dingtalk.com/apiExplorer?spm=ding_open_doc.document.0.0.2e901f874Ka2xN#/?devType=isv&api=contact_1.0%23GetUser)进行调试