---
title: "H5微应用JSAPI总览"
source: "https://open.dingtalk.com/document/development/jsapi-overview-1"
category: "客户端JSAPI / 历史文档（不推荐） / H5微应用"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-overview-1_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-overview-1_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17钉钉提供的前端JSAPI总览。

**扫码体验**

![[development-jsapi-overview-1_p236462.png]]

同时，钉钉提供了前端API调试工具[JSAPI Explorer](https://open-dev.dingtalk.com/apiExplorer#/jsapi?api=biz.util.multiSelect)，供开发者体验提供的前端JSAPI功能。

|  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- |
| 分类 | 接口说明 | **JSAPI名称** | **是否需鉴权** | **Android** | **iOS** | **PC** |
| **免登** | [获取微应用免登授权码](/document/orgapp/obtain-the-micro-application-exemption-authorization-code) | runtime.permission.requestAuthCode | 不需要 | 支持 | 支持 | 支持 |
| [获取微应用反馈式操作的临时授权码](/document/orgapp/obtain-the-temporary-authorization-code-for-micro-application-feedback-operation) | runtime.permission.requestOperateAuthCode | 需要 | 支持 | 支持 | 支持 |
| **设备** | [获取手机基础信息](/document/orgapp/obtain-basic-mobile-phone-information) | device.base.getPhoneInfo | 不需要 | 支持 | 支持 | 不支持 |
| [获取uuid](/document/orgapp/get-uuid) | device.base.getUUID | 需要 | 支持 | 支持 | 不支持 |
| [获取热点接入信息](/document/orgapp/queries-the-hotspot-access-information) | device.base.getInterface | 需要 | 支持 | 支持 | 不支持 |
| [获取wifi状态](/document/orgapp/get-wifi-status) | device.base.getWifiStatus | 不需要 | 支持 | 支持 | 不支持 |
| [获取网络类型](/document/orgapp/queries-the-network-type) | device.connection.getNetworkType | 不需要 | 支持 | 支持 | 不支持 |
| [读取NFC芯片内容](/document/orgapp/read-nfc-chip-content) | device.nfc.nfcRead | 不需要 | 支持 | 不支持 | 不支持 |
| [NFC数据写入](/document/orgapp/nfc-data-write) | device.nfc.nfcWrite | 需要 | 支持 | 不支持 | 不支持 |
| [设置屏幕常亮](/document/orgapp/the-setting-screen-is-always-on) | biz.util.setScreenKeepOn | 不需要 | 支持 | 支持 | 不支持 |
| [获取H5容器启动时间](/document/orgapp/obtains-the-h5-container-startup-time) | runtime.monitor.getLoadTime | 不需要 | 支持 | 支持 | 不支持 |
| [打开iOS系统设置](/document/orgapp/open-ios-system-settings) | device.base.openSystemSetting | 不需要 | 不支持 | 支持 | 不支持 |
| [打开Android系统设置](/document/orgapp/open-android-system-settings) | device.base.openSystemSetting | 不需要 | 支持 | 不支持 | 不支持 |
| **日期和月历** | [日期选择器](/document/orgapp/date-selector) | biz.util.datepicker | 不需要 | 支持 | 支持 | 不支持 |
| [时间选择器](/document/orgapp/time-picker) | biz.util.timepicker | 不需要 | 支持 | 支持 | 不支持 |
| [日期及时间选择器](/document/orgapp/date-and-time-selector) | biz.util.datetimepicker | 不需要 | 支持 | 支持 | 不支持 |
| [月历组件：选择某时间](/document/orgapp/monthly-calendar-component-select-a-specific-time) | biz.calendar.chooseDateTime | 不需要 | 支持 | 支持 | 不支持 |
| [月历组件：选择某天](/document/orgapp/monthly-calendar-component-select-a-certain-day) | biz.calendar.chooseOneDay | 不需要 | 支持 | 支持 | 不支持 |
| [月历组件：选择半天](/document/orgapp/monthly-calendar-component-select-a-date-range) | biz.calendar.chooseHalfDay | 不需要 | 支持 | 支持 | 不支持 |
| [月历组件：选择日期区间](/document/orgapp/month-calendar-component-select-date-range) | biz.calendar.chooseInterval | 不需要 | 支持 | 支持 | 不支持 |
| **通讯录选人** | [选择部门和人](/document/orgapp/select-department-and-person) | biz.contact.complexPicker | 需要 | 支持 | 支持 | 支持 |
| [选择部门信息](/document/orgapp/select-department-information-h5) | biz.contact.departmentsPicker | 需要 | 支持 | 支持 | 支持 |
| [创建企业聊天](/document/orgapp/create-enterprise-chat) | biz.contact.createGroup | 需要 | 支持 | 支持 | 不支持 |
| [选取手机通讯录](/document/orgapp/select-phone-address-book) | biz.contact.chooseMobileContacts | 需要 | 支持 | 支持 | 不支持 |
| [PC端选择企业内部的人](/document/orgapp/on-the-pc-select-the-person-in-the-enterprise) | biz.contact.choose | 需要 | 不支持 | 不支持 | 支持 |
| **角色** | [选择角色组或角色](/document/orgapp/select-a-role-group-or-role) | biz.contact.rolesPicker | 需要 | 支持 | 支持 | 不支持 |
| **业务** | [分享](/document/orgapp/share) | biz.util.share | 不需要 | 支持 | 支持 | 不支持 |
| [下拉控件](/document/orgapp/drop-down-control) | biz.util.chosen | 不需要 | 支持 | 支持 | 不支持 |
| [复制到粘贴板](/document/orgapp/copy-to-clipboard) | biz.clipboardData.setData | 需要 | 支持 | 支持 | 不支持 |
| [打开应用](/document/orgapp/open-an-application) | biz.microApp.openApp | 不需要 | 支持 | 支持 | 不支持 |
| **导航栏** | [设置导航栏颜色](/document/orgapp/set-the-navigation-bar-color) | 拼接dd\_nav\_bgcolor参数 | 不需要 | 支持 | 支持 | 不支持 |
| [微应用页面支持横屏](/document/orgapp/microapplication-page-supports-horizontal-dashboard-h5) | 拼接dd\_orientation参数 | 不需要 | 支持 | 支持 | 不支持 |
| [设置导航栏标题](/document/orgapp/set-the-navigation-bar-title) | biz.navigation.setTitle | 不需要 | 支持 | 支持 | 支持 |
| [标题栏添加问号图标](/document/orgapp/title-bar-add-question-mark-icon) | biz.navigation.setIcon | 不需要 | 支持 | 支持 | 不支持 |
| [设置左侧导航按钮文本](/document/orgapp/set-left-navigation-button-text) | biz.navigation.setLeft | 不需要 | 不支持 | 支持 | 支持 |
| [关闭当前页面](/document/orgapp/close-the-current-page) | biz.navigation.close | 不需要 | 支持 | 支持 | 不支持 |
| [关闭页面](/document/orgapp/close-page) | biz.navigation.quit | 不需要 | 不支持 | 不支持 | 支持 |
| [返回上一级页面](/document/orgapp/return-to-previous-page) | biz.navigation.goBack | 不需要 | 支持 | 支持 | 不支持 |
| [替换页面](/document/orgapp/replace-page) | biz.navigation.replace | 不需要 | 支持 | 支持 | 不支持 |
| **弹窗** | [alert](/document/orgapp/alert) | device.notification.alert | 不需要 | 支持 | 支持 | 支持 |
| [confirm](/document/orgapp/confirm) | device.notification.confirm | 不需要 | 支持 | 支持 | 支持 |
| [prompt](/document/orgapp/prompt) | device.notification.prompt | 不需要 | 支持 | 支持 | 支持 |
| [手机震动](/document/orgapp/mobile-phone-vibration) | device.notification.vibrate | 不需要 | 支持 | 支持 | 不支持 |
| [显示加载](/document/orgapp/show-load) | device.notification.showPreloader | 不需要 | 支持 | 支持 | 不支持 |
| [隐藏加载](/document/orgapp/hide-loading) | device.notification.hidePreloader | 不需要 | 支持 | 支持 | 不支持 |
| [toast](/document/orgapp/toast) | device.notification.toast | 不需要 | 支持 | 支持 | 支持 |
| [actionsheet](/document/orgapp/actionsheet) | device.notification.actionSheet | 不需要 | 支持 | 支持 | 支持 |
| [modal弹浮层](/document/orgapp/modal-pop-up-layer) | device.notification.modal | 不需要 | 支持 | 支持 | 不支持 |
| [extendModal](/document/orgapp/extendmodal) | device.notification.extendModal | 不需要 | 支持 | 支持 | 不支持 |
| [多选组件](/document/orgapp/multiple-select-components) | biz.util.multiSelect | 不需要 | 支持 | 支持 | 不支持 |
| **会话** | [根据corpid选择会话](/document/orgapp/select-session-based-on-corpid) | biz.chat.chooseConversationByCorpId | 需要 | 支持 | 支持 | 支持 |
| [根据chatId跳转到对应会话](/document/orgapp/redirects-to-a-specific-session-based-on-the-chatid-h5) | biz.chat.toConversation | 需要 | 支持 | 支持 | 不支持 |
| [根据openConversationId跳转到对应会话](/document/orgapp/redirects-to-the-specified-session-based-on-the-openconversationid) | biz.chat.toConversationByOpenConversationId | 需要 | 支持 | 支持 | 支持 |
| [打开与某个用户的单聊会话](/document/orgapp/open-a-one-on-one-chat-session-with-a-user) | biz.chat.openSingleChat | 需要 | 支持 | 支持 | 不支持 |
| **电话** | [拨打钉钉电话](/document/orgapp/call-dingtalk-h5) | biz.telephone.call | 需要 | 支持 | 支持 | 不支持 |
| [通用电话拨打](/document/orgapp/universal-phone-call-h5) | biz.telephone.showCallMenu | 需要 | 支持 | 支持 | 不支持 |
| [检查某企业的办公电话开通状态](/document/orgapp/check-the-status-of-office-telephones-of-an-enterprise-h5) | biz.telephone.checkBizCall | 需要 | 支持 | 支持 | 不支持 |
| [拨打单人电话选项（可定制）](/document/orgapp/make-a-single-call-option-customizable-h5) | biz.telephone.quickCallList | 需要 | 支持 | 支持 | 支持 |
| **DING** | [DING 2.0 发钉](/document/orgapp/ding-2-0-hair-pin) | biz.ding.create | 需要 | 支持 | 支持 | 支持 |
| [DING 1.0 发钉](/document/orgapp/ding-1-0-hair-pin) | biz.ding.post | 需要 | 不支持 | 不支持 | 支持 |
| **文件** | [批量检测本地文件是否存在](/document/orgapp/checks-for-local-files-in-batches) | biz.util.isLocalFileExist | 不需要 | 不支持 | 不支持 | 支持 |
| [打开本地文件](/document/orgapp/open-a-local-file) | biz.util.openLocalFile | 不需要 | 不支持 | 不支持 | 支持 |
| [上传文件](/document/orgapp/upload-objects-jsapi) | biz.util.uploadFile | 不需要 | 支持 | 不支持 | 不支持 |
| [下载文件](/document/orgapp/download-objects) | biz.util.downLoadFile | 不需要 | 不支持 | 不支持 | 支持 |
| **存储** | [设置存储信息](/document/orgapp/set-storage-information) | util.domainStorage.setItem | 不需要 | 支持 | 支持 | 不支持 |
| [获取存储信息](/document/orgapp/obtain-storage-information) | util.domainStorage.getItem | 不需要 | 支持 | 支持 | 不支持 |
| [删除存储信息](/document/orgapp/delete-storage-information) | util.domainStorage.removeItem | 不需要 | 支持 | 支持 | 不支持 |
| **钉盘** | [保存文件到钉盘](/document/orgapp/save-file-to-nail-plate) | biz.cspace.saveFile | 需要 | 支持 | 支持 | 不支持 |
| [上传附件到钉盘/从钉盘选择文件](/document/orgapp/upload-attachment-to-nail-plate-select-file-from-nail-plate-h5) | biz.util.uploadAttachment | 需要 | 支持 | 支持 | 支持 |
| [预览钉盘文件](/document/orgapp/preview-nail-plate-file) | biz.cspace.preview | 需要 | 支持 | 支持 | 支持 |
| [批量预览钉盘图片](/document/orgapp/batch-preview-of-nail-plate-pictures) | biz.cspace.previewDentryImages | 不需要 | 支持 | 支持 | 不支持 |
| [选取钉盘目录](/document/orgapp/select-a-pin-plate-directory-h5) | biz.cspace.chooseSpaceDir | 需要 | 支持 | 支持 | 不支持 |
| **图片** | [选择图片](/document/orgapp/select-picture) | biz.util.chooseImage | 需要 | 支持 | 支持 | 不支持 |
| [压缩图片](/document/orgapp/compress-images) | biz.util.compressImage | 不需要 | 支持 | 支持 | 不支持 |
| [图片预览](/document/orgapp/image-preview) | biz.util.previewImage | 不需要 | 支持 | 支持 | 支持 |
| **地图** | [获取当前地理位置信息（单次定位）](/document/orgapp/obtain-current-geographic-location-information-single-positioning) | device.geolocation.get | 需要 | 支持 | 支持 | 不支持 |
| [连续获取当前地理位置信息（持续定位）](/document/orgapp/continuous-retrieval-of-current-geographic-information-continuous-location) | device.geolocation.start | 需要 | 支持 | 支持 | 不支持 |
| [停止连续定位](/document/orgapp/stop-continuous-positioning) | device.geolocation.stop | 需要 | 支持 | 支持 | 不支持 |
| [批量获取连续定位的状态](/document/orgapp/batch-continuous-positioning-status) | device.geolocation.status | 不需要 | 支持 | 支持 | 不支持 |
| [地图定位](/document/orgapp/map-positioning) | biz.map.locate | 需要 | 支持 | 支持 | 不支持 |
| [地图页面支持搜索](/document/orgapp/map-page-supports-search) | biz.map.search | 需要 | 支持 | 支持 | 不支持 |
| [展示位置](/document/orgapp/display-position) | biz.map.view | 需要 | 支持 | 支持 | 不支持 |
| **音频** | [开始录音](/document/orgapp/start-recording) | device.audio.startRecord | 需要 | 支持 | 支持 | 不支持 |
| [停止录音](/document/orgapp/stop-recording) | device.audio.stopRecord | 需要 | 支持 | 支持 | 不支持 |
| [监听录音自动停止](/document/orgapp/automatic-stop-of-monitoring-and-recording) | device.audio.onRecordEnd | 需要 | 支持 | 支持 | 不支持 |
| [下载音频](/document/orgapp/download-audio) | device.audio.download | 需要 | 支持 | 支持 | 不支持 |
| [播放语音](/document/orgapp/playback-voice) | device.audio.play | 需要 | 支持 | 支持 | 不支持 |
| [暂停播放语音](/document/orgapp/pause-playback-of-speech) | device.audio.pause | 需要 | 支持 | 支持 | 不支持 |
| [恢复暂停播放的语音](/document/orgapp/resume-paused-voice) | device.audio.resume | 需要 | 支持 | 支持 | 不支持 |
| [停止播放音频](/document/orgapp/stop-audio-playback) | device.audio.stop | 需要 | 支持 | 支持 | 不支持 |
| [监听播放自动停止](/document/orgapp/automatically-stops-playback) | device.audio.onPlayEnd | 需要 | 支持 | 支持 | 不支持 |
| [语音转文字](/document/orgapp/voice-to-text) | device.audio.translateVoice | 需要 | 支持 | 支持 | 不支持 |
| **摇一摇** | [启动摇一摇](/document/orgapp/start-a-shake) | device.accelerometer.watchShake | 不需要 | 支持 | 支持 | 不支持 |
| [停止摇一摇](/document/orgapp/stop-a-shake) | device.accelerometer.clearShake | 不需要 | 支持 | 支持 | 不支持 |
| **UI控件** | [输入框](/document/orgapp/input-box) | ui.input.plain | 不需要 | 支持 | 支持 | 不支持 |
| [设置顶部进度条颜色](/document/orgapp/set-the-color-of-the-top-progress-bar) | ui.progressBar.setColors | 不需要 | 支持 | 支持 | 不支持 |
| [启用下拉刷新](/document/orgapp/enable-pull-down-refresh) | ui.pullTorefresh.enable | 不需要 | 支持 | 支持 | 不支持 |
| [收起下拉刷新](/document/orgapp/refresh) | ui.pullToRefresh.stop | 不需要 | 支持 | 支持 | 不支持 |
| [禁用下拉刷新](/document/orgapp/disable-pull-down-refresh) | ui.pullToRefresh.disable | 不需要 | 支持 | 支持 | 不支持 |
| [启用iOS Webview弹性效果](/document/orgapp/enable-webview-for-ios) | ui.webViewBounce.enable | 不需要 | 不支持 | 支持 | 不支持 |
| [禁用iOS Webview弹性效果](/document/orgapp/disable-webview-autoscaling-for-ios) | ui.webViewBounce.disable | 不需要 | 不支持 | 支持 | 不支持 |
| **扫码** | [扫条形码、二维码](/document/orgapp/scan-barcodes-and-qr-codes) | biz.util.scan | 不需要 | 支持 | 支持 | 不支持 |
| [扫名片](/document/orgapp/scan-business-cards) | biz.util.scanCard | 需要 | 支持 | 支持 | 不支持 |
| **支付** | [支付接口](/document/orgapp/payment-interface) | biz.alipay.pay | 需要 | 支持 | 支持 | 不支持 |
| **转屏横屏** | [微应用页面支持转屏](/document/orgapp/microapplication-page-supports-screen-rotation) | 拼接dd\_orientation=auto参数 | 不需要 | 支持 | 支持 | 不支持 |
| [微应用页面支持横屏](/document/orgapp/microapplication-page-supports-horizontal-dashboard) | 拼接dd\_orientation参数 | 不需要 | 支持 | 支持 | 不支持 |
| [微应用页面全屏展示](/document/orgapp/full-screen-display-of-microapplication-page) | 拼接dd\_full\_screen=true参数 | 不需要 | 支持 | 支持 | 不支持 |
| [微应用页面导航栏透明](/document/orgapp/the-microapplication-navigation-bar-is-transparent) | 拼接dd\_nav\_translucent=true参数 | 不需要 | 支持 | 支持 | 不支持 |
| [旋转屏幕](/document/orgapp/rotate-screen) | device.screen.rotateView | 不需要 | 支持 | 支持 | 不支持 |
| [重置旋转屏幕](/document/orgapp/reset-rotation-screen) | device.screen.resetView | 不需要 | 支持 | 支持 | 不支持 |
| **外部联系人** | [选择外部联系人](/document/orgapp/select-external-contacts) | biz.contact.externalComplexPicker | 需要 | 支持 | 支持 | 不支持 |
| [编辑外部联系人](/document/orgapp/edit-external-contacts) | biz.contact.externalEditForm | 需要 | 支持 | 支持 | 不支持 |
| **自定义联系人** | [单选自定义联系人](/document/orgapp/custom-radio-contact) | biz.customContact.choose | 需要 | 支持 | 支持 | 支持 |
| [多选自定义联系人](/document/orgapp/multiple-custom-contacts) | biz.customContact.multipleChoose | 需要 | 支持 | 支持 | 支持 |
| **打开新页面** | [打开应用内页面](/document/orgapp/open-the-in-application-page) | biz.util.open | 需要 | 支持 | 支持 | 支持 |
| [打开目标页面](/document/orgapp/open-link-on-new-window) | biz.util.openLink | 不需要 | 支持 | 支持 | 支持 |
| [打开模态框](/document/orgapp/open-modal-box) | biz.util.openModal | 不需要 | 不支持 | 不支持 | 支持 |
| [打开侧边面板](/document/orgapp/open-side-panel) | biz.util.openSlidePanel | 不需要 | 不支持 | 不支持 | 支持 |
| [PC端打开新弹窗页面](/document/orgapp/open-new-tab) | biz.util.invokeWorkbench | 需要 | 不支持 | 不支持 | 支持 |
| [判断是否为弹窗窗口](/document/orgapp/determines-whether-it-is-a-pop-up-window) | biz.tabwindow.isTab | 不需要 | 不支持 | 不支持 | 支持 |
| **打开应用** | [跳转H5微应用](/document/orgapp/jump-to-h5-micro-application) | biz.navigation.navigateToPage | 不需要 | 支持 | 支持 | 不支持 |
| [返回上一个应用](/document/orgapp/return-to-previous-application) | biz.navigation.navigateBackPage | 不需要 | 支持 | 支持 | 不支持 |
| **数据加解密** | [数据加密](/document/orgapp/data-encryption) | biz.util.encrypt | 需要 | 支持 | 支持 | 不支持 |
| [数据解密](/document/orgapp/data-decryption) | biz.util.decrypt | 需要 | 支持 | 支持 | 不支持 |
| **视频会议** | [发起视频会议](/document/orgapp/initiate-video-conference) | biz.conference.videoConfCall | 需要 | 支持 | 支持 | 支持 |
| **办公电话** | [查询企业是否已开办公电话](/document/orgapp/check-whether-the-enterprise-has-an-office-phone-number) | biz.conference.getCloudCallInfo | 需要 | 支持 | 支持 | 支持 |
| [发起办公电话呼叫](/document/orgapp/direct-dialing) | biz.conference.createCloudCall | 需要 | 支持 | 支持 | 支持 |
| [查询话单列表](/document/orgapp/query-the-number-list) | biz.conference.getCloudCallList | 需要 | 支持 | 支持 | 支持 |
| **在线课堂** | [发起在线课堂](/document/orgapp/online-classroom-initiation) | biz.live.startClassRoom | 需要 | 不支持 | 不支持 | 支持 |
| **专属钉钉** | [获取钉钉客户端是否为专属钉钉](/document/orgapp/retrieve-user-information-info) | biz.realm.getUserExclusiveInfo | 不需要 | 支持 | 支持 | 支持 |
| [专属实人认证](/document/orgapp/id-verification) | biz.ATMBle.exclusiveLiveCheck | 需要 | 支持 | 支持 | 不支持 |