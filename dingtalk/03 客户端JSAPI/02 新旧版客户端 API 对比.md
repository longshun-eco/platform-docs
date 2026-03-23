---
title: "新旧版客户端 API 对比"
source: "https://open.dingtalk.com/document/development/comparison--client-apis"
category: "客户端JSAPI"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-comparison--client-apis_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-comparison--client-apis_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2026-01-22为帮助开发者顺利完成从旧版三段式客户端 API 到新版一段式客户端 API 的升级，本文档系统梳理了新旧 API 的映射关系，并提供背景说明、适用对象、调用指引及典型示例。

> 本文适用于使用钉钉小程序或 H5 微应用的开发者，用于指导客户端 JSAPI 的版本迁移。通过本对照表可快速定位功能对应的新版 API，降低升级成本。

## 背景与优势

钉钉开放平台将客户端 API 调用方式由“三段式”统一升级为“一段式”，旨在简化调用逻辑、提升开发效率并增强跨端一致性。

* **三段式调用（旧版）**：格式为 `namespace.function.action`，如 `biz.util.chooseImage`
* **一段式调用（新版）**：格式为单一函数名，如 `chooseImage`。

**升级优势**：

* 接口命名更简洁直观
* 函数语义更清晰，易于记忆和使用
* 支持更灵活的参数结构和返回值设计
* 更好地支持 TypeScript 类型推导

**参考文档**：

* 新版客户端 API，详情参考新版[客户端 API 总览](https://open.dingtalk.com/document/orgapp/jsapi-overview-client-org)。
* 旧版客户端 API，分为小程序和H5微应用：

  + 小程序详情参考旧版[小程序 API 总览](https://open.dingtalk.com/document/orgapp/mini-program-jsapi-overview)。
  + H5微应用详情参考旧版[H5微应用 API 总览](https://open.dingtalk.com/document/orgapp/jsapi-overview)。

以图片选择为例，展示新版 API 的标准调用方式：

```javascript
// 初始化 dd SDK（省略初始化代码）

dd.chooseImage({
  count: 9, // 最多选择图片数量
  success: function(res) {
    const imageList = res.fileList; // 返回选中的文件列表
    console.log('选中图片：', imageList);
  },
  fail: function(err) {
    console.error('选择失败：', err);
  }
});
```

成功响应示例：

```json
{
  "fileList": [
    {
      "url": "https://example.com/image.jpg",
      "name": "photo.jpg",
      "size": 102400,
      "mediaId": "12345abcde"
    }
  ]
}
```

## 迁移操作指南

为确保平滑迁移至新版一段式 API，请遵循以下五步迁移法：

1. **识别现有三段式调用**

   在代码中查找形如`biz.util.chooseImage`的旧版 API 调用。
2. **查阅本对照表定位对应函数**

   根据类目和功能描述，在表格中找到对应的新版 API 名称，例如`chooseImage`。
3. **替换为一段式语法并调整参数结构**

   将原调用方式替换为`dd.chooseImage({...})`，注意检查参数是否兼容，必要时参考新版文档调整字段。
4. **确保已引入最新版本 dd SDK**

   新版 API 需要依赖较新的`dd`客户端库，请确认已在项目中引入最新版 SDK。
5. **在真机上测试调用结果**

   建议优先在真实设备上进行测试，验证功能可用性与返回数据格式。

# **界面**

用于控制页面导航、弹窗反馈、日期选择等用户界面交互行为。

|  |  |  |
| --- | --- | --- |
| **类目** | **新版客户端API** | **旧版客户端API** |
| **地图** | [chooseDistrict](https://open.dingtalk.com/document/orgapp/jsapi-choose-district) | biz.util.chooseRegion |
| **导航栏** | [setNavigationTitle](https://open.dingtalk.com/document/orgapp/jsapi-set-navigation-title) | biz.navigation.setTitle |
| [setNavigationIcon](https://open.dingtalk.com/document/orgapp/jsapi-set-navigation-icon) | biz.navigation.setIcon |
| [setNavigationLeft](https://open.dingtalk.com/document/orgapp/jsapi-set-navigation-left) | biz.navigation.setLeft |
| [goBackPage](https://open.dingtalk.com/document/orgapp/jsapi-go-back-page) | biz.navigation.goBack |
| [replacePage](https://open.dingtalk.com/document/orgapp/jsapi-replace-page) | biz.navigation.replace |
| [closePage](https://open.dingtalk.com/document/orgapp/jsapi-close-page) | biz.navigation.close |
| [quitPage](https://open.dingtalk.com/document/orgapp/jsapi-quit-page) | biz.navigation.quit |
| **交互反馈** | [alert](https://open.dingtalk.com/document/orgapp/jsapi-alert) | device.notification.alert |
| [confirm](https://open.dingtalk.com/document/orgapp/jsapi-confirm) | device.notification.confirm |
| [showToast](https://open.dingtalk.com/document/orgapp/jsapi-show-toast) | device.notification.toast |
| [hideLoading](https://open.dingtalk.com/document/orgapp/jsapi-hide-loading) | device.notification.hidePreloader |
| [hideToast](https://open.dingtalk.com/document/orgapp/jsapi-hide-toast) | device.notification.hideToast |
| [showLoading](https://open.dingtalk.com/document/orgapp/jsapi-show-loading) | device.notification.showPreloader |
| [showActionSheet](https://open.dingtalk.com/document/orgapp/jsapi-show-action-sheet) | device.notification.actionSheet |
| [showModal](https://open.dingtalk.com/document/orgapp/jsapi-show-modal) | device.notification.extendModal |
| [prompt](https://open.dingtalk.com/document/orgapp/jsapi-prompt) | device.notification.prompt |
| **选择日期** | [datePicker](https://open.dingtalk.com/document/orgapp/jsapi-date-picker) | biz.util.datetimepicker |
| [dateRangePicker](https://open.dingtalk.com/document/orgapp/jsapi-date-range-picker) | biz.calendar.chooseInterval |
| [timePicker](https://open.dingtalk.com/document/orgapp/jsapi-time-picker) | biz.util.timepicker |
| [chooseDateTime](https://open.dingtalk.com/document/orgapp/jsapi-choose-date-time) | biz.calendar.chooseDateTime |
| [chooseOneDayInCalendar](https://open.dingtalk.com/document/orgapp/jsapi-choose-one-day-in-calendar) | biz.calendar.chooseOneDay |
| [chooseHalfDayInCalendar](https://open.dingtalk.com/document/orgapp/jsapi-choose-half-day-in-calendar) | biz.calendar.chooseHalfDay |
| **下拉刷新** | [enablePullDownRefresh](https://open.dingtalk.com/document/orgapp/jsapi-enable-pull-down-refresh) | ui.pullToRefresh.enable |
| [disablePullDownRefresh](https://open.dingtalk.com/document/orgapp/jsapi-disable-pull-down-refresh) | ui.pullToRefresh.disable |
| **选项选择器** | [singleSelect](https://open.dingtalk.com/document/orgapp/jsapi-single-select) | biz.util.chosen |
| [multiSelect](https://open.dingtalk.com/document/orgapp/jsapi-multi-select) | biz.util.multiSelect |

## **设备**

提供对手机硬件功能的访问能力，如 NFC、振动、剪贴板等。

|  |  |  |
| --- | --- | --- |
| **类目** | **新版客户端API** | **旧版客户端API** |
| **UUID** | [getDeviceUUID](https://open.dingtalk.com/document/orgapp/jsapi-get-device-uuid) | device.base.getUUID |
| **NFC** | [writeNFC](https://open.dingtalk.com/document/orgapp/jsapi-write-nfc) | device.nfc.nfcWrite |
| [readNFC](https://open.dingtalk.com/document/orgapp/jsapi-read-nfc) | device.nfc.nfcRead |
| **振动** | [vibrate](https://open.dingtalk.com/document/orgapp/jsapi-vibrate) | device.notification.vibrate |
| **扫码** | [scanCard](https://open.dingtalk.com/document/orgapp/jsapi-scan-card) | biz.util.scanCard |
| **摇一摇** | [clearShake](https://open.dingtalk.com/document/orgapp/jsapi-clear-shake) | device.accelerometer.clearShake |
| [watchShake](https://open.dingtalk.com/document/orgapp/jsapi-watch-shake) | device.accelerometer.watchShake |
| **剪贴板** | [setClipboard](https://open.dingtalk.com/document/orgapp/jsapi-set-clipboard) | biz.clipboardData.setData |
| **Wi-Fi** | [getWifiStatus](https://open.dingtalk.com/document/orgapp/jsapi-get-wifi-status) | device.base.getWifiStatus |
| **屏幕亮度** | [setKeepScreenOn](https://open.dingtalk.com/document/orgapp/jsapi-set-keep-screen-on) | biz.util.setScreenKeepOn |
| [setScreenBrightness](https://open.dingtalk.com/document/orgapp/jsapi-set-screen-brightness) | device.screen.setScreenBrightness |
| **拨打电话** | [addPhoneContact](https://open.dingtalk.com/document/orgapp/jsapi-add-phone-contact) | biz.phoneContact.add |
| **设备电量** | [getBatteryInfo](https://open.dingtalk.com/document/orgapp/jsapi-get-battery-info) | device.base.getBatteryInfo |
| **网络状态** | [getNetworkType](https://open.dingtalk.com/document/orgapp/jsapi-get-network-type) | device.connection.getNetworkType |
| [getWifiHotspotStatus](https://open.dingtalk.com/document/orgapp/jsapi-get-wifi-hotspot-status) | device.base.getInterface |
| **系统信息** | [getSystemInfo](https://open.dingtalk.com/document/orgapp/jsapi-get-system-info) | device.base.getPhoneInfo |
| [rsa](https://open.dingtalk.com/document/orgapp/jsapi-rsa) | biz.data.rsa |
| [showAuthGuide](https://open.dingtalk.com/document/orgapp/jsapi-show-auth-guide) | biz.util.showAuthGuide |
| [checkAuth](https://open.dingtalk.com/document/orgapp/jsapi-check-auth) | biz.util.checkAuth |
| [isScreenReaderEnabled](https://open.dingtalk.com/document/orgapp/jsapi-is-screen-reader-enabled) | device.screen.isScreenReaderEnabled |
| [getSystemSettings](https://open.dingtalk.com/document/orgapp/jsapi-get-system-settings) | device.base.openSystemSetting |
| **设备方向** | [resetScreenView](https://open.dingtalk.com/document/orgapp/jsapi-reset-screen-view) | device.screen.resetView |
| [rotateScreenView](https://open.dingtalk.com/document/orgapp/jsapi-rotate-screen-view) | device.screen.rotateView |

## **跳转**

用于实现页面跳转、本地缓存等通用功能。

|  |  |
| --- | --- |
| **新版客户端API** | **旧版客户端API** |
| [openLink](https://open.dingtalk.com/document/orgapp/jsapi-open-link) | biz.util.openLink |
| [isInTabWindow](https://open.dingtalk.com/document/orgapp/jsapi-is-in-tab-window) | biz.tabwindow.isTab |
| [getStorage](https://open.dingtalk.com/document/orgapp/jsapi-get-storage) | util.domainStorage.getItem |
| [removeStorage](https://open.dingtalk.com/document/orgapp/jsapi-remove-storage) | util.domainStorage.removeItem |
| [navigateBackPage](https://open.dingtalk.com/document/orgapp/jsapi-navigate-back-page) | biz.navigation.navigateBackPage |
| [navigateToPage](https://open.dingtalk.com/document/orgapp/jsapi-navigate-to-page) | biz.navigation.navigateToPage |
| [openMicroApp](https://open.dingtalk.com/document/orgapp/jsapi-open-micro-app) | biz.microApp.openApp |
| [openPageInMicroApp](https://open.dingtalk.com/document/orgapp/jsapi-open-page-in-micro-app) | biz.util.open |
| [openPageInWorkBenchForPC](https://open.dingtalk.com/document/orgapp/jsapi-open-page-in-work-bench-for-pc) | biz.util.invokeWorkbench |
| [openPageInSlidePanelForPC](https://open.dingtalk.com/document/orgapp/jsapi-open-page-in-slide-panel-for-pc) | biz.util.openSlidePanel |

## **多媒体**

支持图像、音频的采集与播放控制。

|  |  |  |
| --- | --- | --- |
| **类目** | **新版客户端API** | **旧版客户端API** |
| **图片** | [chooseImage](https://open.dingtalk.com/document/orgapp/jsapi-choose-image) | biz.util.chooseImage |
| [previewImage](https://open.dingtalk.com/document/orgapp/jsapi-preview-image) | biz.util.previewImage |
| **录音** | [translateVoice](https://open.dingtalk.com/document/orgapp/jsapi-translate-voice) | device.audio.translateVoice |
| [onPlayAudioEnd](https://open.dingtalk.com/document/orgapp/jsapi-on-play-audio-end) | device.audio.onPlayEnd |
| [onRecordEnd](https://open.dingtalk.com/document/orgapp/jsapi-on-record-end) | device.audio.onRecordEnd |
| [downloadAudio](https://open.dingtalk.com/document/orgapp/jsapi-download-audio) | device.audio.download |
| [resumeAudio](https://open.dingtalk.com/document/orgapp/jsapi-resume-audio) | device.audio.resume |
| [pauseAudio](https://open.dingtalk.com/document/orgapp/jsapi-pause-audio) | device.audio.pause |
| [stopAudio](https://open.dingtalk.com/document/orgapp/jsapi-stop-audio) | device.audio.stop |
| [playAudio](https://open.dingtalk.com/document/orgapp/jsapi-play-audio) | device.audio.play |
| [stopRecord](https://open.dingtalk.com/document/orgapp/jsapi-stop-record) | device.audio.stopRecord |
| [startRecord](https://open.dingtalk.com/document/orgapp/jsapi-start-record) | device.audio.startRecord |

## **缓存**

用于在客户端进行数据持久化存储。

|  |  |
| --- | --- |
| **新版客户端API** | **旧版客户端API** |
| [setStorage](https://open.dingtalk.com/document/orgapp/jsapi-set-storage) | util.domainStorage.setItem |
| [getStorage](https://open.dingtalk.com/document/orgapp/jsapi-get-storage) | util.domainStorage.getItem |
| [removeStorage](https://open.dingtalk.com/document/orgapp/jsapi-remove-storage) | util.domainStorage.removeItem |

## **位置**

提供定位、地图展示、搜索等功能。

|  |  |
| --- | --- |
| **新版客户端API** | **旧版客户端API** |
| [getLocation](https://open.dingtalk.com/document/orgapp/jsapi-get-location) | device.geolocation.get |
| [openLocation](https://open.dingtalk.com/document/orgapp/jsapi-open-location) | biz.map.view |
| [searchMap](https://open.dingtalk.com/document/orgapp/jsapi-search-map) | biz.map.search |
| [locateInMap](https://open.dingtalk.com/document/orgapp/jsapi-locate-in-map) | biz.map.locate |
| [getLocatingStatus](https://open.dingtalk.com/document/orgapp/jsapi-get-locating-status) | device.geolocation.status |
| [stopLocating](https://open.dingtalk.com/document/orgapp/jsapi-stop-locating) | device.geolocation.stop |
| [startLocating](https://open.dingtalk.com/document/orgapp/jsapi-start-locating) | device.geolocation.start |

## **网络**

支持文件下载等网络操作。

|  |  |  |
| --- | --- | --- |
| **类目** | **新版客户端API** | **旧版客户端API** |
| **上传下载** | [downloadFile](https://open.dingtalk.com/document/orgapp/jsapi-download-file) | biz.file.downloadFile |

## **分享**

实现内容分享至会话或其他渠道。

|  |  |
| --- | --- |
| **新版客户端API** | **旧版客户端API** |
| [share](https://open.dingtalk.com/document/orgapp/jsapi-share) | biz.util.share |
| [showSharePanel](https://open.dingtalk.com/document/orgapp/jsapi-show-share-panel) | biz.util.showSharePanel |

## **获取凭证**

用于获取用户身份凭证。

|  |  |
| --- | --- |
| **新版客户端API** | **旧版客户端API** |
| [getAuthCode](https://open.dingtalk.com/document/orgapp/jsapi-get-auth-code) | runtime.permission.requestAuthCode |
| [getOperateAuthCode](https://open.dingtalk.com/document/orgapp/jsapi-get-operate-auth-code) | runtime.permission.requestOperateAuthCode |

## **会话管理**

用于打开或选择聊天窗口。

|  |  |
| --- | --- |
| **新版客户端API** | **旧版客户端API** |
| [chooseChat](https://open.dingtalk.com/document/orgapp/jsapi-choose-chat) | biz.chat.chooseConversationByCorpId |
| [openChatByChatId](https://open.dingtalk.com/document/orgapp/jsapi-open-chat-by-chat-id) | biz.chat.toConversation |
| [openChatByUserId](https://open.dingtalk.com/document/orgapp/jsapi-open-chat-by-user-id) | biz.chat.openSingleChat |
| [openChatByConversationId](https://open.dingtalk.com/document/orgapp/jsapi-open-chat-by-conversation-id) | biz.chat.toConversationByOpenConversationId |

## **通讯录**

用于从组织架构中选择人员或部门。

|  |  |
| --- | --- |
| **新版客户端API** | **旧版客户端API** |
| [choosePhonebook](https://open.dingtalk.com/document/orgapp/jsapi-choose-phonebook) | biz.contact.chooseMobileContacts |
| [complexChoose](https://open.dingtalk.com/document/orgapp/jsapi-complex-choose) | biz.contact.complexPicker |
| [chooseDepartments](https://open.dingtalk.com/document/orgapp/jsapi-choose-departments) | biz.contact.departmentsPicker |
| [chooseExternalUsers](https://open.dingtalk.com/document/orgapp/jsapi-choose-external-users) | biz.contact.externalComplexPicker |
| [editExternalUser](https://open.dingtalk.com/document/orgapp/jsapi-edit-external-user) | biz.contact.externalEditForm |
| [chooseUserFromList](https://open.dingtalk.com/document/orgapp/jsapi-choose-user-from-list) | chooseUserFromList |
| [chooseStaffForPC](https://open.dingtalk.com/document/orgapp/jsapi-choose-staff-for-pc) | biz.contact.choose |

## **DING**

用于创建和发送 DING 消息。

|  |  |
| --- | --- |
| **新版客户端API** | **旧版客户端API** |
| [createDing](https://open.dingtalk.com/document/orgapp/jsapi-create-ding) | biz.ding.create |
| [createDingForPC](https://open.dingtalk.com/document/orgapp/jsapi-create-ding-for-pc) | biz.ding.post |

## **办公电话**

支持云呼叫、快速拨号等功能。

|  |  |
| --- | --- |
| **新版客户端API** | **旧版客户端API** |
| [callUsers](https://open.dingtalk.com/document/orgapp/jsapi-call-users) | biz.telephone.call |
| [checkBizCall](https://open.dingtalk.com/document/orgapp/jsapi-check-biz-call) | biz.telephone.checkBizCall |
| [getCloudCallList](https://open.dingtalk.com/document/orgapp/jsapi-get-cloud-call-list) | biz.conference.getCloudCallList |
| [makeCloudCall](https://open.dingtalk.com/document/orgapp/jsapi-make-cloud-call) | biz.conference.createCloudCall |
| [getCloudCallInfo](https://open.dingtalk.com/document/orgapp/jsapi-get-cloud-call-info) | biz.conference.getCloudCallInfo |
| [quickCallList](https://open.dingtalk.com/document/orgapp/jsapi-quick-call-list) | biz.telephone.quickCallList |

## **钉盘**

用于文件保存、预览和上传。

|  |  |
| --- | --- |
| **新版客户端API** | **旧版客户端API** |
| [saveFileToDingTalk](https://open.dingtalk.com/document/orgapp/jsapi-save-file-to-ding-talk) | biz.cspace.saveFile |
| [previewFileInDingTalk](https://open.dingtalk.com/document/orgapp/jsapi-preview-file-in-ding-talk) | biz.cspace.preview |
| [uploadAttachmentToDingTalk](https://open.dingtalk.com/document/orgapp/jsapi-upload-attachment-to-ding-talk) | biz.util.uploadAttachment |
| [chooseDingTalkDir](https://open.dingtalk.com/document/orgapp/jsapi-choose-ding-talk-dir) | biz.cspace.chooseSpaceDir |
| [previewImagesInDingTalkBatch](https://open.dingtalk.com/document/orgapp/jsapi-preview-images-in-ding-talk-batch) | biz.cspace.previewDentryImages |

## **文件**

操作设备本地文件。

|  |  |
| --- | --- |
| **新版客户端API** | **旧版客户端API** |
| [openLocalFile](https://open.dingtalk.com/document/orgapp/jsapi-open-local-file) | biz.util.openLocalFile |
| [isLocalFileExist](https://open.dingtalk.com/document/orgapp/jsapi-is-local-file-exist) | biz.util.isLocalFileExist |

## **视频**

发起视频会议呼叫。

|  |  |
| --- | --- |
| **新版客户端API** | **旧版客户端API** |
| [makeVideoConfCall](https://open.dingtalk.com/document/orgapp/jsapi-make-video-conf-call) | biz.conference.videoConfCall |

## **专属开放**

面向特定客户开放的能力。

|  |  |
| --- | --- |
| **新版客户端API** | **旧版客户端API** |
| [getUserExclusiveInfo](https://open.dingtalk.com/document/orgapp/jsapi-get-user-exclusive-info) | biz.realm.getUserExclusiveInfo |