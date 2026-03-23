---
title: "Android应用授权登录接入流程"
source: "https://open.dingtalk.com/document/dingstart/mini-app-android-platform-application-authorization-login-access"
category: "新手指南 / 移动客户端接入 / 接入钉钉登录"
updated: 
tags:
  - dingtalk
  - 新手指南
---
![[dingstart-mini-app-android-platform-application-authorization-login-access_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[dingstart-mini-app-android-platform-application-authorization-login-access_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-03

## 准备工作

在使用移动应用接入钉钉登录之前，你需要完成以下准备工作：

* 搭建Android开发环境。
* Demo参考 [钉钉OAuthSDKDemo.zip](https://help-static-aliyun-doc.aliyuncs.com/file-manage-files/zh-CN/20250408/wlsvef/%E9%92%89%E9%92%89OAuthSDKDemo.zip)

## 实现流程

![[dingstart-mini-app-android-platform-application-authorization-login-access_p481496.png]]

## 步骤一：创建**钉钉**应用

1. 登录[开发者后台](https://open-dev.dingtalk.com/#/shareMan)，打开应用列表页，点击应用进入应用详情页。

   ![[dingstart-mini-app-android-platform-application-authorization-login-access_p386713.png]]
2. 在应用信息页面，获取应用的AppKey和AppSecret。

   ![[dingstart-mini-app-android-platform-application-authorization-login-access_p481671.png]]
3. 在应用详情页，单击**钉钉登录与分享**，进入登录与分享页面。

   ![[dingstart-mini-app-android-platform-application-authorization-login-access_p386717.png]]
4. 在**接入登录**栏，添加回调域名。

   **说明**

   在授权登录过程中，钉钉会校验授权接口的参数redirectUri，与此处配置的域名是否一致。

   ![[dingstart-mini-app-android-platform-application-authorization-login-access_p481462.png]]
5. 在**接入分享**栏，打开Android分享，填入包名及签名。

![[dingstart-mini-app-android-platform-application-authorization-login-access_p676009.png]]

## 步骤二：搭建开发环境

**说明**

使用本SDK，即表示您已阅读并同意《[钉钉开放平台隐私权政策](/document/services/open-latform-privacy-policy)》、《[钉钉开放平台开发者服务协议](/document/services/open-platform-developer-service-agreement)》。

Android Studio 环境下：

1. 在build.gradle文件中，指定仓库并添加如下依赖：

   * 指定仓库：

     ```
     repositories {
        mavenCentral()
     }
     ```
   * 添加依赖：

     ```
     dependencies {
      implementation 'com.alibaba.android:ddopenauth:1.5.0.10'
     }
     ```
2. 在工程AndroidManifest.xml中添加声明：

   ```

   ```

   如需混淆，建议混淆文件中增加：

   ```
   -keep class com.android.dingtalk.openauth.**{*;}
   ```

## 步骤三：发送请求到钉钉

```
AuthLoginParam.AuthLoginParamBuilder builder = AuthLoginParam.AuthLoginParamBuilder.newBuilder();
builder.appId(yourAppId);
builder.redirectUri(yourRedirectUri);
builder.responseType(responseType);
builder.scope(scope);
builder.nonce(nonce);
builder.state(state);
builder.prompt(prompt);
IDDAuthApi authApi = DDAuthApiFactory.createDDAuthApi(context, builder.build());
authApi.authLogin()
```

**参数说明：**

|  |  |  |
| --- | --- | --- |
| 参数 | 是否必填 | 备注 |
| appId | 是 | 钉钉开放平台应用标识，即第一步中获取的AppKey。 |
| redirectUri | 是 | 创建应用时填写的回调域名，仅用于校验域名是否一致，不会跳转。  **说明**  需要与创建应用时填写的回调域名保持一致。 |
| responseType | 是 | 当前只支持固定值code，授权通过后返回authCode。 |
| scope | 是 | 应用授权作用域。授权页面显示的授权信息以应用注册时配置的为准  当前只支持两种输入：   * openid：授权后可获得用户oepnid。 * openid%20corpid：授权后可获得用户openid和登录过程中用户选择的组织corpId。 |
| nonce | 否 | 字段值任意填写，授权登录后原样返回。 |
| state | 否 | 用于保持请求和回调的状态，授权请求后原样带回给第三方。  **说明**  该参数可用于防止csrf攻击（跨站请求伪造攻击），建议第三方带上该参数，可设置为简单的随机数加session进行校验。 |
| prompt | 是 | 固定值为consent，会进入授权确认页。 |

### 当前用户已安装钉钉，则跳转钉钉APP拉起授权登录页

**说明**

第三步截图只在首次授权登录时出现。

![[dingstart-mini-app-android-platform-application-authorization-login-access_p481471.png]]

### 当前用户未安装钉钉时，通过H5登录并授权

**说明**

第三步截图只在首次授权登录时出现。

![[dingstart-mini-app-android-platform-application-authorization-login-access_p481475.png]]

## 步骤四：接收授权结果

1. 在包名相应目录下新建ddauth，并新增DDAuthActivity：

   ![[dingstart-mini-app-android-platform-application-authorization-login-access_p481481.png]]
2. 在工程AndroidManifest.xml中添加声明：

   ```

   ```
3. 在DDAuthActivity中接收回调：

   ```java
   public class DDAuthActivity extends AppCompatActivity {

      @Override
      protected void onCreate(@Nullable Bundle savedInstanceState) {
       super.onCreate(savedInstanceState);

       Intent intent = getIntent();
       String authCode = intent.getStringExtra(DDAuthConstant.CALLBACK_EXTRA_AUTH_CODE);
       String state = intent.getStringExtra(DDAuthConstant.CALLBACK_EXTRA_STATE);
       String error = intent.getStringExtra(DDAuthConstant.CALLBACK_EXTRA_ERROR);

       if(!TextUtils.isEmpty(authCode)) {
       // 授权成功
       } else {
       // 授权失败
       }
       finish();
      }
   }
   ```

**返回值说明**：

|  |  |
| --- | --- |
| 返回值 | 说明 |
| error | 取值：   * ERR\_OK = 0（用户同意） * ERR\_AUTH\_DENIED = -4（用户角色授权） * ERR\_USER\_CANCEL = -2（用户取消） |
| authCode | 授权码，可换取个人用户accessToken的凭证。  **说明**  authCode只能使用一次。 |
| state | 调用方标识其请求的唯一性的标志，state字符串长度不能超过1K。 |

## 步骤五：获取用户个人access\_token

使用步骤四返回的authCode，调用[获取用户token](/document/development/obtain-user-token)接口，换取用户个人access\_token。

```java
public class Test {
    public static com.aliyun.dingtalkoauth2_1_0.Client createClient() throws Exception {
        Config config = new Config();
        config.protocol = "https";
        config.regionId = "central";
        return new com.aliyun.dingtalkoauth2_1_0.Client(config);
    }
    public void getUserToken() throws Exception {
        com.aliyun.dingtalkoauth2_1_0.Client client = Test.createClient();
        GetUserTokenRequest getUserTokenRequest = new GetUserTokenRequest()
                .setClientId("dingzxxxx") //第一步创建应用时获取的AppKey。
                .setClientSecret("XyJONrxxxxx") //第一步创建应用时获取的AppSecret。
                .setCode("18ec1db4xxxxx") //第四步获取的authCode。
                .setGrantType("authorization_code");
        try {
            GetUserTokenResponse userToken = client.getUserToken(getUserTokenRequest);
            System.out.println(JSON.toJSONString(userToken));
        } catch (TeaException err) {
            if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                // err 中含有 code 和 message 属性，可帮助开发定位问题
                System.out.println(JSON.toJSONString(err));
```

## 步骤六：获取用户个人信息

使用步骤五获取的用户个人access\_token，调用[获取用户通讯录个人信息](/document/development/dingtalk-retrieve-user-information)接口，获取用户个人手机号、用户的钉钉昵称、头像URL、用户的个人邮箱等信息。

```java
public class Test {
    public static com.aliyun.dingtalkcontact_1_0.Client createClient() throws Exception {
        Config config = new Config();
        config.protocol = "https";
        config.regionId = "central";
        return new com.aliyun.dingtalkcontact_1_0.Client(config);
    }

    public void getUserInfo() throws Exception {
        com.aliyun.dingtalkcontact_1_0.Client client = Test.createClient();
        GetUserHeaders getUserHeaders = new GetUserHeaders();
        getUserHeaders.xAcsDingtalkAccessToken = "17e756exxxx";//第五步获取的个人用户Token。
        try {
            GetUserResponse response = client.getUserWithOptions("me", getUserHeaders, new RuntimeOptions());
            System.out.println(JSON.toJSON(response));
        } catch (TeaException err) {
            if (!com.aliyun.teautil.Common.empty(err.code) && !com.aliyun.teautil.Common.empty(err.message)) {
                // err 中含有 code 和 message 属性，可帮助开发定位问题
                System.out.println(JSON.toJSONString(err));
            }
```