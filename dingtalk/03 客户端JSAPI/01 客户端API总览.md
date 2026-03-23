---
title: "客户端API总览"
source: "https://open.dingtalk.com/document/development/jsapi-overview"
category: "客户端JSAPI"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-jsapi-overview_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-jsapi-overview_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-01

## **客户端 SDK**

### **方式一：使用npm引入（推荐）**

1. 使用npm安装。

   ```bash
   npm install dingtalk-jsapi --save
   ```

   > dingtalk-jsapi 3.0.27 版本后支持一段式，例如：chooseChat，同时也支持三段式，例如：biz.contact.choose。
2. 加载 dingtalk-jsapi：

   ```
   import * as dd from 'dingtalk-jsapi'; // 此方式为整体加载，也可按需进行加载
   ```

### **方式二：使用cdn引入（不推荐）**

浏览器引入，在浏览器中使用 script 和 link 标签直接引入文件，并使用全局变量 dd。

**说明**

不推荐使用浏览器引入方法，这样无法按需加载，而且难以获得底层依赖模块的 bug 快速修复支持。

## **基础**

|  |  |
| --- | --- |
| **API名称** | **API说明** |
| [canIUse](https://open.dingtalk.com/document/orgapp/jsapi-can-i-use) | 判断 API 是否可用 |
| [corpId](https://open.dingtalk.com/document/orgapp/jsapi-corp-id) | 获取当前访问用户的企业corpId |
| [exit](https://open.dingtalk.com/document/orgapp/jsapi-exit) | 关闭钉钉小程序 |
| [ExtSDKVersion](https://open.dingtalk.com/document/orgapp/jsapi-ext-sdk-version) | 使用本接口获取基础库版本号 |
| [getRunScene](https://open.dingtalk.com/document/orgapp/jsapi-get-run-scene) | 获取当前小程序的运行版本 |
| [getAppIdSync](https://open.dingtalk.com/document/orgapp/jsapi-get-app-id-sync) | 同步获取小程序的AppId，即MiniAppId |
| [getLaunchOptionsSync](https://open.dingtalk.com/document/orgapp/jsapi-get-launch-options-sync) | 获取小程序启动时的参数 |
| [SDKVersion](https://open.dingtalk.com/document/orgapp/jsapi-sdk-version) | 使用本接口获取基础库版本号 |

## **界面**

|  |  |  |
| --- | --- | --- |
| **类目** | **API名称** | **API说明** |
| **导航栏** | [closePage](https://open.dingtalk.com/document/orgapp/jsapi-close-page) | 关闭当前页面 |
| [goBackPage](https://open.dingtalk.com/document/orgapp/jsapi-go-back-page) | 返回上一级页面 |
| [quitPage](https://open.dingtalk.com/document/orgapp/jsapi-quit-page) | PC端关闭页面 |
| [replacePage](https://open.dingtalk.com/document/orgapp/jsapi-replace-page) | 替换页面 |
| [setNavigationBar](https://open.dingtalk.com/document/orgapp/jsapi-set-navigation-bar) | 设置小程序导航栏样式及标题等 |
| [setNavigationTitle](https://open.dingtalk.com/document/orgapp/jsapi-set-navigation-title) | 设置导航栏标题 |
| [setNavigationIcon](https://open.dingtalk.com/document/orgapp/jsapi-set-navigation-icon) | 标题栏添加问号图标 |
| [setNavigationLeft](https://open.dingtalk.com/document/orgapp/jsapi-set-navigation-left) | 设置左侧导航按钮文本 |
| **TabBar** | [addTabBarItem](https://open.dingtalk.com/document/orgapp/jsapi-add-tab-bar-item) | 添加tabBar页面 |
| [hideTabBarRedDot](https://open.dingtalk.com/document/orgapp/jsapi-hide-tab-bar-red-dot) | 隐藏tabBar红点 |
| [removeTabBarItem](https://open.dingtalk.com/document/orgapp/jsapi-remove-tab-bar-item) | 移除tabBar页面 |
| [removeTabBarBadge](https://open.dingtalk.com/document/orgapp/jsapi-remove-tab-bar-badge) | 移除tabBar文本 |
| [setTabBarBadge](https://open.dingtalk.com/document/orgapp/jsapi-set-tab-bar-badge) | 为 tabBar 某一项的右上角添加文本 |
| [showTabBarRedDot](https://open.dingtalk.com/document/orgapp/jsapi-show-tab-bar-red-dot) | 显示tabBar红点 |
| [enableLeaveConfirm](https://open.dingtalk.com/document/orgapp/jsapi-enable-leave-confirm) | 对当前页面进行离开二次确认 |
| **路由** | [navigateTo](https://open.dingtalk.com/document/orgapp/jsapi-navigate-to) | 跳转到应用内的某个指定页面 |
| [navigateBack](https://open.dingtalk.com/document/orgapp/jsapi-navigate-back) | 返回上一级或返回多级页面 并且关闭当前页面 |
| [reLaunch](https://open.dingtalk.com/document/orgapp/jsapi-re-launch) | 跳转到小程序应用内指定页面并且关闭当前所有页面 |
| [redirectTo](https://open.dingtalk.com/document/orgapp/jsapi-redirect-to) | 跳转到应用内的某个指定页面 |
| [switchTab](https://open.dingtalk.com/document/orgapp/jsapi-switch-tab) | 跳转到指定 tabBar 页面 |
| **动画** | [createAnimation](https://open.dingtalk.com/document/orgapp/jsapi-create-animation) | 创建动画实例 |
| [Animation.bottom](https://open.dingtalk.com/document/orgapp/jsapi-animation-bottom) | 设置动画实例bottom值 |
| [Animation.backgroundColor](https://open.dingtalk.com/document/orgapp/jsapi-animation-background-color) | 设置动画背景色 |
| [Animation.height](https://open.dingtalk.com/document/orgapp/jsapi-animation-height) | 设置动画实例高度值 |
| [Animation.left](https://open.dingtalk.com/document/orgapp/jsapi-animation-left) | 设置动画实例Left值 |
| [Animation.matrix](https://open.dingtalk.com/document/orgapp/jsapi-animation-matrix) | 设置动画实例Matrix值 |
| [Animation.matrix3d](https://open.dingtalk.com/document/orgapp/jsapi-animation-matrix3d) | 设置动画实例Matrix3d |
| [Animation.opacity](https://open.dingtalk.com/document/orgapp/jsapi-animation-opacity) | 设置动画透明度 |
| [Animation.right](https://open.dingtalk.com/document/orgapp/jsapi-animation-right) | 设置动画实例Right值 |
| [Animation.rotate](https://open.dingtalk.com/document/orgapp/jsapi-animation-rotate) | 设置动画实例旋转Rotate值 |
| [Animation.rotateX](https://open.dingtalk.com/document/orgapp/jsapi-animation-rotate-x) | 设置动画实例RotateX值 |
| [Animation.rotateY](https://open.dingtalk.com/document/orgapp/jsapi-animation-rotate-y) | 设置动画实例RotateY值 |
| [Animation.rotateZ](https://open.dingtalk.com/document/orgapp/jsapi-animation-rotate-z) | 设置动画实例RotateZ值 |
| [Animation.rotate3d](https://open.dingtalk.com/document/orgapp/jsapi-animation-rotate3d) | 设置动画实例Rotate3D值 |
| [Animation.scale](https://open.dingtalk.com/document/orgapp/jsapi-animation-scale) | 设置动画实例Scale值 |
| [Animation.scaleX](https://open.dingtalk.com/document/orgapp/jsapi-animation-scale-x) | 设置动画实例ScaleX值 |
| [Animation.scaleY](https://open.dingtalk.com/document/orgapp/jsapi-animation-scale-y) | 设置动画实例ScaleY值 |
| [Animation.scaleZ](https://open.dingtalk.com/document/orgapp/jsapi-animation-scale-z) | 设置动画实例ScaleZ值 |
| [Animation.scale3d](https://open.dingtalk.com/document/orgapp/jsapi-animation-scale3d) | 设置动画实例Scale3d值 |
| [Animation.skew](https://open.dingtalk.com/document/orgapp/jsapi-animation-skew) | 设置动画实例Skew |
| [Animation.skewX](https://open.dingtalk.com/document/orgapp/jsapi-animation-skew-x) | 设置动画实例SkewX |
| [Animation.skewY](https://open.dingtalk.com/document/orgapp/jsapi-animation-skew-y) | 设置动画实例SkewY |
| [Animation.top](https://open.dingtalk.com/document/orgapp/jsapi-animation-top) | 设置动画实例Top值 |
| [Animation.translate](https://open.dingtalk.com/document/orgapp/jsapi-animation-translate) | 设置动画实例Translate |
| [Animation.translateX](https://open.dingtalk.com/document/orgapp/jsapi-animation-translate-x) | 设置动画实例TranslateX值 |
| [Animation.translateY](https://open.dingtalk.com/document/orgapp/jsapi-animation-translate-y) | 设置动画实例TranslateY值 |
| [Animation.translateZ](https://open.dingtalk.com/document/orgapp/jsapi-animation-translate-z) | 设置动画实例TranslateZ值 |
| [Animation.translate3d](https://open.dingtalk.com/document/orgapp/jsapi-animation-translate3d) | 设置动画实例Translate3d值 |
| [Animation.width](https://open.dingtalk.com/document/orgapp/jsapi-animation-width) | 设置动画实例长度值 |
| **画布** | [createCanvasContext](https://open.dingtalk.com/document/orgapp/jsapi-create-canvas-context) | 创建canvas绘图上下文 |
| [CanvasContext.arc](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-arc) | 画一条弧线 |
| [CanvasContext.addColorStop](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-add-color-stop) | 创建渐变点 |
| [CanvasContext.beginPath](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-begin-path) | 创建一个路径 |
| [CanvasContext.bezierCurveTo](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-bezier-curve-to) | 创建三次方贝塞尔曲线路径 |
| [CanvasContext.clip](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-clip) | 创建的路径设置为当前剪切路径 |
| [CanvasContext.clearRect](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-clear-rect) | 清除画布上在该矩形区域内的内容 |
| [CanvasContext.closePath](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-close-path) | 关闭一个路径 |
| [CanvasContext.createLinearGradient](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-create-linear-gradient) | 创建一个线性的渐变色 |
| [CanvasContext.createCircularGradient](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-create-circular-gradient) | 创建一个圆形的渐变色 |
| [CanvasContext.draw](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-draw) | 在绘图上下文中的描述（路径、变形、样式）画到 canvas 中 |
| [CanvasContext.drawImage](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-draw-image) | 绘制图像 |
| [CanvasContext.fill](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-fill) | 对当前路径中的内容进行填充 |
| [CanvasContext.fillRect](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-fill-rect) | 填充矩形 |
| [CanvasContext.fillText](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-fill-text) | 在画布上绘制被填充的文本 |
| [CanvasContext.getImageData](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-get-image-data) | 获取canvas区域隐含的像素数据 |
| [CanvasContext.lineTo](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-line-to) | 创建一条从上次指定点到目标点的线 |
| [CanvasContext.moveTo](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-move-to) | 将路径移动到画布中的指定点 |
| [CanvasContext.putImageData](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-put-image-data) | 将像素数据绘制到画布 |
| [CanvasContext.quadraticCurveTo](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-quadratic-curve-to) | 创建二次贝塞尔曲线路径 |
| [CanvasContext.rect](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-rect) | 创建一个矩形 |
| [CanvasContext.rotate](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-rotate) | 以原点为中心（原点可以用translate方法修改），顺时针旋转当前坐标轴。多次调用rotate，旋转的角度会叠加 |
| [CanvasContext.restore](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-restore) | 恢复之前保存的绘图上下文 |
| [CanvasContext.save](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-save) | 保存当前的绘图上下文 |
| [CanvasContext.scale](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-scale) | 调用scale方法后，之后创建的路径其横纵坐标会被缩放。多次调用scale，倍数会相乘 |
| [CanvasContext.stroke](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-stroke) | 画出当前路径的边框 |
| [CanvasContext.strokeRect](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-stroke-rect) | 画一个非填充矩形 |
| [CanvasContext.setFillStyle](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-set-fill-style) | 设置填充色 |
| [CanvasContext.setFontSize](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-set-font-size) | 设置字体大小 |
| [CanvasContext.setShadow](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-set-shadow) | 设置阴影样式 |
| [CanvasContext.setLineCap](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-set-line-cap) | 设置线条的端点样式 |
| [CanvasContext.setLineJoin](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-set-line-join) | 设置线条的交点样式 |
| [CanvasContext.setTextAlign](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-set-text-align) | 设置文本的对齐方式 |
| [CanvasContext.setMiterLimit](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-set-miter-limit) | 设置最大斜接长度 |
| [CanvasContext.setLineWidth](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-set-line-width) | 设置线条的宽度 |
| [CanvasContext.setStrokeStyle](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-set-stroke-style) | 设置边框颜色 |
| [CanvasContext.setGlobalAlpha](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-set-global-alpha) | 设置全局画笔透明度 |
| [CanvasContext.setTextBaseline](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-set-text-baseline) | 设置当前文本基线的属性 |
| [CanvasContext.translate](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-translate) | 对当前坐标系的原点(0, 0)进行变换，默认的坐标系原点为页面左上角 |
| [CanvasContext.toTempFilePath](https://open.dingtalk.com/document/orgapp/jsapi-canvas-context-to-temp-file-path) | 画布内容导出成图片 |
| **字体** | [loadFontFace](https://open.dingtalk.com/document/orgapp/jsapi-load-font-face) | 动态的加载网络字体 |
| **地图** | [chooseDistrict](https://open.dingtalk.com/document/orgapp/jsapi-choose-district) | 选择地区 |
| [createMapContext](https://open.dingtalk.com/document/orgapp/jsapi-create-map-context) | 创建并返回一个地图上下文对象 |
| [MapContext.clearRoute](https://open.dingtalk.com/document/orgapp/jsapi-map-context-clear-route) | 清除地图上的步行导航路线 |
| [MapContext.changeMarkers](https://open.dingtalk.com/document/orgapp/jsapi-map-context-change-markers) | 用于添加、删除、更新指定的标记 |
| [MapContext.calculateDistance](https://open.dingtalk.com/document/orgapp/jsapi-map-context-calculate-distance) | 提供地图路径计算能力，用于计算途径地图上多个点的总路线距离 |
| [MapContext.getRegion](https://open.dingtalk.com/document/orgapp/jsapi-map-context-get-region) | 获取地图东北角、西南角的经纬度，从而获取地图整体的视野范围 |
| [MapContext.gestureEnable](https://open.dingtalk.com/document/orgapp/jsapi-map-context-gesture-enable) | 设置所有手势是否可用 |
| [MapContext.getMapProperties](https://open.dingtalk.com/document/orgapp/jsapi-map-context-get-map-properties) | 获取地图的属性信息 |
| [MapContext.getCenterLocation](https://open.dingtalk.com/document/orgapp/jsapi-map-context-get-center-location) | 获取当前地图中心位置 |
| [MapContext.moveToLocation](https://open.dingtalk.com/document/orgapp/jsapi-map-context-move-to-location) | 将视野移动到定位点并恢复到默认缩放级别 |
| [MapContext.showRoute](https://open.dingtalk.com/document/orgapp/jsapi-map-context-show-route) | 规划默认步行路线，只能显示一条 |
| [MapContext.showsScale](https://open.dingtalk.com/document/orgapp/jsapi-map-context-shows-scale) | 设置比例尺控件是否可见 |
| [MapContext.showsCompass](https://open.dingtalk.com/document/orgapp/jsapi-map-context-shows-compass) | 设置指南针是否可见 |
| [MapContext.smoothMoveMarker](https://open.dingtalk.com/document/orgapp/jsapi-map-context-smooth-move-marker) | 指定标记（marker）进行动画 |
| [MapContext.smoothMovePolyline](https://open.dingtalk.com/document/orgapp/jsapi-map-context-smooth-move-polyline) | 用于轨迹动画 |
| [MapContext.translateMarker](https://open.dingtalk.com/document/orgapp/jsapi-map-context-translate-marker) | 用于平移点标记 |
| [MapContext.updateComponents](https://open.dingtalk.com/document/orgapp/jsapi-map-context-update-components) | 用于增量更新地图 |
| **滚动** | [pageScrollTo](https://open.dingtalk.com/document/orgapp/jsapi-page-scroll-to) | 滚动到页面的目标位置 |
| **交互反馈** | [alert](https://open.dingtalk.com/document/orgapp/jsapi-alert) | 显示警告框 |
| [confirm](https://open.dingtalk.com/document/orgapp/jsapi-confirm) | 显示确认框 |
| [hideToast](https://open.dingtalk.com/document/orgapp/jsapi-hide-toast) | 隐藏弱提示 |
| [hideLoading](https://open.dingtalk.com/document/orgapp/jsapi-hide-loading) | 隐藏加载提示 |
| [prompt](https://open.dingtalk.com/document/orgapp/jsapi-prompt) | 弹出输出入对话框 |
| [showModal](https://open.dingtalk.com/document/orgapp/jsapi-show-modal) | 增强版modal弹浮层 |
| [showToast](https://open.dingtalk.com/document/orgapp/jsapi-show-toast) | 显示一个弱提示 |
| [showLoading](https://open.dingtalk.com/document/orgapp/jsapi-show-loading) | 显示加载提示 |
| [showActionSheet](https://open.dingtalk.com/document/orgapp/jsapi-show-action-sheet) | 显示操作菜单 |
| **下拉刷新** | [disablePullDownRefresh](https://open.dingtalk.com/document/orgapp/jsapi-disable-pull-down-refresh) | 禁用下拉刷新 |
| [enablePullDownRefresh](https://open.dingtalk.com/document/orgapp/jsapi-enable-pull-down-refresh) | 启用下拉刷新 |
| [onPullDownRefresh](https://open.dingtalk.com/document/orgapp/jsapi-on-pull-down-refresh) | 监听下拉刷新 |
| [stopPullDownRefresh](https://open.dingtalk.com/document/orgapp/jsapi-stop-pull-down-refresh) | 停止当前页面的下拉刷新 |
| **键盘输入** | [hideKeyboard](https://open.dingtalk.com/document/orgapp/jsapi-hide-keyboard) | 隐藏键盘 |
| [onKeyboardHide](https://open.dingtalk.com/document/orgapp/jsapi-on-keyboard-hide) | 监听键盘收起 |
| [onKeyboardShow](https://open.dingtalk.com/document/orgapp/jsapi-on-keyboard-show) | 监听键盘弹起事件 |
| **节点查询** | [createIntersectionObserver](https://open.dingtalk.com/document/orgapp/jsapi-create-intersection-observer) | 创建并返回一个IntersectionObserver对象实例 |
| [IntersectionObserver.disconnect](https://open.dingtalk.com/document/orgapp/jsapi-intersection-observer-disconnect) | 停止监听 |
| [IntersectionObserver.observe](https://open.dingtalk.com/document/orgapp/jsapi-intersection-observer-observe) | 指定目标节点并开始监听相交状态变化情况 |
| [IntersectionObserver.relativeTo](https://open.dingtalk.com/document/orgapp/jsapi-intersection-observer-relative-to) | 使用选择器指定一个节点，作为参照区域之一 |
| [IntersectionObserver.relativeToViewport](https://open.dingtalk.com/document/orgapp/jsapi-intersection-observer-relative-to-viewport) | 指定页面显示区域作为参照区域之一 |
| [createSelectorQuery](https://open.dingtalk.com/document/orgapp/jsapi-create-selector-query) | 创建一个节点查询对象SelectorQuery |
| [SelectorQuery.boundingClientRect](https://open.dingtalk.com/document/orgapp/jsapi-selector-query-bounding-client-rect) | 将当前选择节点的位置信息放入查询结果， 返回对象包含 width/height/left/top/bottom/right |
| [SelectorQuery.exe](https://open.dingtalk.com/document/orgapp/jsapi-selector-query-exec) | 查询结果放入 callback 回调中 |
| [SelectorQuery.select](https://open.dingtalk.com/document/orgapp/jsapi-selector-query-select) | 选择当前第一个匹配选择器的节点，选择器支持 id 选择器以及 class 选择器 |
| [SelectorQuery.selectAll](https://open.dingtalk.com/document/orgapp/jsapi-selector-query-select-all) | 选择所有匹配选择器的节点，选择器支持 id 选择器以及 class 选择器 |
| [SelectorQuery.scrollOffset](https://open.dingtalk.com/document/orgapp/jsapi-selector-query-scroll-offset) | 将当前选择节点的滚动信息放入查询结果，返回对象包含 scrollTop/scrollLeft |
| [SelectorQuery.selectViewport](https://open.dingtalk.com/document/orgapp/jsapi-selector-query-select-viewport) | 选择窗口对象 |
| **暗黑模式** | [getColorSchemeSync](https://open.dingtalk.com/document/orgapp/jsapi-get-color-scheme-sync) | 获取钉钉当前显示模式。返回当前系统的显示模式"light" 或 "dark" |
| **选择日期** | [chooseDateTime](https://open.dingtalk.com/document/orgapp/jsapi-choose-date-time) | 选择日期和时间 |
| [chooseOneDayInCalendar](https://open.dingtalk.com/document/orgapp/jsapi-choose-one-day-in-calendar) | 月历组件，选择某天 |
| [chooseHalfDayInCalendar](https://open.dingtalk.com/document/orgapp/jsapi-choose-half-day-in-calendar) | 月历组件，选择半天 |
| [datePicker](https://open.dingtalk.com/document/orgapp/jsapi-date-picker) | 打开日期选择列表 |
| [dateRangePicker](https://open.dingtalk.com/document/orgapp/jsapi-date-range-picker) | 月历组件，选择日期区间 |
| [timePicker](https://open.dingtalk.com/document/orgapp/jsapi-time-picker) | 时间选择器 |
| 选项选择器 | [multiSelect](https://open.dingtalk.com/document/orgapp/jsapi-multi-select) | 多选组件 |
| [singleSelect](https://open.dingtalk.com/document/orgapp/jsapi-single-select) | 单选组件 |

## **跳转**

|  |  |
| --- | --- |
| **API名称** | **API说明** |
| [isInTabWindow](https://open.dingtalk.com/document/orgapp/jsapi-is-in-tab-window) | 判断当前页面是否为弹窗页面 |
| [navigateToPage](https://open.dingtalk.com/document/orgapp/jsapi-navigate-to-page) | 跳转到另一个钉钉H5微应用 |
| [navigateBackPage](https://open.dingtalk.com/document/orgapp/jsapi-navigate-back-page) | 返回上一个应用 |
| [navigateToMiniProgram](https://open.dingtalk.com/document/orgapp/jsapi-navigate-to-mini-program) | 跳转到其他钉钉小程序 |
| [navigateBackMiniProgram](https://open.dingtalk.com/document/orgapp/jsapi-navigate-back-mini-program) | 返回到上一个钉钉小程序 |
| [openLink](https://open.dingtalk.com/document/orgapp/jsapi-open-link) | 打开目标页面 |
| [openMicroApp](https://open.dingtalk.com/document/orgapp/jsapi-open-micro-app) | 打开应用 |
| [openPageInMicroApp](https://open.dingtalk.com/document/orgapp/jsapi-open-page-in-micro-app) | 打开应用内页面 |
| [openPageInModalForPC](https://open.dingtalk.com/document/orgapp/jsapi-open-page-in-modal-for-pc) | 打开模态框 |
| [openPageInSlidePanelForPC](https://open.dingtalk.com/document/orgapp/jsapi-open-page-in-slide-panel-for-pc) | 打开侧边面板 |
| [openPageInWorkBenchForPC](https://open.dingtalk.com/document/orgapp/jsapi-open-page-in-work-bench-for-pc) | PC端打开新弹窗页面 |

## **多媒体**

|  |  |  |
| --- | --- | --- |
| **类目** | **API名称** | **API说明** |
| **图片** | [chooseImage](https://open.dingtalk.com/document/orgapp/jsapi-choose-image) | 拍照或从本地相册选择图片 |
| [compressImage](https://open.dingtalk.com/document/orgapp/jsapi-compress-image) | 压缩图片 |
| [editPicture](https://open.dingtalk.com/document/orgapp/jsapi-edit-picture) | 编辑图片 |
| [getImageInfo](https://open.dingtalk.com/document/orgapp/jsapi-get-image-info) | 获取图片信息 |
| [previewImage](https://open.dingtalk.com/document/orgapp/jsapi-preview-image) | 预览图片 |
| [saveImage](https://open.dingtalk.com/document/orgapp/jsapi-save-image) | 保存在线、本地临时或者永久地址图片到手机相册 |
| **录音** | [downloadAudio](https://open.dingtalk.com/document/orgapp/jsapi-download-audio) | 下载音频 |
| [onRecordEnd](https://open.dingtalk.com/document/orgapp/jsapi-on-record-end) | 监听录音自动停止 |
| [onPlayAudioEnd](https://open.dingtalk.com/document/orgapp/jsapi-on-play-audio-end) | 监听播放自动停止 |
| [playAduio](https://open.dingtalk.com/document/orgapp/jsapi-play-aduio) | 播放语音 |
| [pauseAduio](https://open.dingtalk.com/document/orgapp/jsapi-pause-aduio) | 暂停播放语音 |
| [resumeAudio](https://open.dingtalk.com/document/orgapp/jsapi-resume-audio) | 恢复暂停播放的语音 |
| [stopRecord](https://open.dingtalk.com/document/orgapp/jsapi-stop-record) | 停止录音 |
| [startRecord](https://open.dingtalk.com/document/orgapp/jsapi-start-record) | 开始录音 |
| [stopAudio](https://open.dingtalk.com/document/orgapp/jsapi-stop-audio) | 停止播放音频 |
| [translateVoice](https://open.dingtalk.com/document/orgapp/jsapi-translate-voice) | 语音转文字 |
| [getRecorderManager](https://open.dingtalk.com/document/orgapp/jsapi-get-recorder-manager) | 获取当前小程序全局唯一的录音管理器 |
| [RecorderManager.onstart](https://open.dingtalk.com/document/orgapp/jsapi-recorder-manager-on-start) | 录音开始时的回调 |
| [RecorderManager.onstop](https://open.dingtalk.com/document/orgapp/jsapi-recorder-manager-on-stop) | 录音停止时的回调 |
| [RecorderManager.onerror](https://open.dingtalk.com/document/orgapp/jsapi-recorder-manager-on-error) | 录音管理监听错误 |
| [RecorderManager.onpause](https://open.dingtalk.com/document/orgapp/jsapi-recorder-manager-on-pause) | 录音管理监听暂停 |
| [RecorderManager.onresume](https://open.dingtalk.com/document/orgapp/jsapi-recorder-manager-on-resume) | 录音管理监听继续 |
| [RecorderManager.onframerecorded](https://open.dingtalk.com/document/orgapp/jsapi-recorder-manager-on-frame-recorded) | 录音管理监听已录制完制定帧大小的文件 |
| [RecorderManager.pause](https://open.dingtalk.com/document/orgapp/jsapi-recorder-manager-pause) | 录音管理暂停录音 |
| [RecorderManager.resume](https://open.dingtalk.com/document/orgapp/jsapi-recorder-manager-resume) | 录音管理继续录音 |
| [RecorderManager.stop](https://open.dingtalk.com/document/orgapp/jsapi-recorder-manager-stop) | 停止录音 |
| [RecorderManager.start](https://open.dingtalk.com/document/orgapp/jsapi-recorder-manager-start) | 开始录音 |
| **音频** | [getBackgroundAudioManager](https://open.dingtalk.com/document/orgapp/jsapi-get-background-audio-manager) | 获取当前小程序全局唯一的背景音频管理 |
| [BackgroundAudioManager.onPlay](https://open.dingtalk.com/document/orgapp/jsapi-background-audio-manager-on-play) | 监听背景音频播放事件 |
| [BackgroundAudioManager.onStop](https://open.dingtalk.com/document/orgapp/jsapi-background-audio-manager-on-stop) | 监听背景音频停止事件 |
| [BackgroundAudioManager.onPause](https://open.dingtalk.com/document/orgapp/jsapi-background-audio-manager-on-pause) | 监听背景音频暂停事件 |
| [BackgroundAudioManager.onEnded](https://open.dingtalk.com/document/orgapp/jsapi-background-audio-manager-on-ended) | 监听背景音频结束事件 |
| [BackgroundAudioManager.onPrev](https://open.dingtalk.com/document/orgapp/jsapi-background-audio-manager-on-prev) | 监听用户在系统音乐播放面板点击上一曲事件 |
| [BackgroundAudioManager.onNext](https://open.dingtalk.com/document/orgapp/jsapi-background-audio-manager-on-next) | 监听用户在系统音乐播放面板点击下一曲事件 |
| [BackgroundAudioManager.onCanplay](https://open.dingtalk.com/document/orgapp/jsapi-background-audio-manager-on-canplay) | 监听背景音频进入可以播放事件 |
| [BackgroundAudioManager.onSeeked](https://open.dingtalk.com/document/orgapp/jsapi-background-audio-manager-on-seeked) | 监听背景音频完成播放进度跳转操作事件 |
| [BackgroundAudioManager.onSeeking](https://open.dingtalk.com/document/orgapp/jsapi-background-audio-manager-on-seeking) | 监听背景音频开始播放进度跳转事件 |
| [BackgroundAudioManager.onWaiting](https://open.dingtalk.com/document/orgapp/jsapi-background-audio-manager-on-waiting) | 监听音频加载中事件。 |
| [BackgroundAudioManager.onTimeUpdate](https://open.dingtalk.com/document/orgapp/jsapi-background-audio-manager-on-time-update) | 监听背景音频播放进度更新事件 |
| [BackgroundAudioManager.play](https://open.dingtalk.com/document/orgapp/jsapi-background-audio-manager-play) | 播放背景音乐 |
| [BackgroundAudioManager.pause](https://open.dingtalk.com/document/orgapp/jsapi-background-audio-manager-pause) | 暂停背景音频 |
| [BackgroundAudioManager.stop](https://open.dingtalk.com/document/orgapp/jsapi-background-audio-manager-stop) | 停止播放背景音乐 |
| [BackgroundAudioManager.seek](https://open.dingtalk.com/document/orgapp/jsapi-background-audio-manager-seek) | 跳转到指定位置position |
| [onAudioInterruptionEnd](https://open.dingtalk.com/document/orgapp/jsapi-on-audio-interruption-end) | 监听音频被中断的结束事件。 |
| [onAudioInterruptionBegin](https://open.dingtalk.com/document/orgapp/jsapi-on-audio-interruption-begin) | 监听音频因为系统占用而被中断的开始事件 |
| [saveVideoToPhotosAlbum](https://open.dingtalk.com/document/orgapp/jsapi-save-video-to-photos-album) | 保存视频到系统相册 |
| **视频** | [chooseVideo](https://open.dingtalk.com/document/orgapp/jsapi-choose-video) | 拍摄视频或从手机相册中选视频 |
| [createVideoContext](https://open.dingtalk.com/document/orgapp/jsapi-create-video-context) | 创建并返回一个 video上下文对象videoContext |
| [VideoContext.exitFullScreen](https://open.dingtalk.com/document/orgapp/jsapi-video-context-exit-full-screen) | 控制相应video组件的全屏退出 |
| [VideoContext.mute](https://open.dingtalk.com/document/orgapp/jsapi-video-context-mute) | 切换静音状态 |
| [VideoContext.play](https://open.dingtalk.com/document/orgapp/jsapi-video-context-play) | 控制相应video组件的播放 |
| [VideoContext.pause](https://open.dingtalk.com/document/orgapp/jsapi-video-context-pause) | 控制相应video组件的暂停 |
| [VideoContext.playbackRate](https://open.dingtalk.com/document/orgapp/jsapi-video-context-playback-rate) | 设置倍速播放 |
| [VideoContext.requestFullScreen](https://open.dingtalk.com/document/orgapp/jsapi-video-context-request-full-screen) | 控制相应video组件的全屏进入 |
| [VideoContext.stop](https://open.dingtalk.com/document/orgapp/jsapi-video-context-stop) | 控制相应video组件的终止 |
| [VideoContext.seek](https://open.dingtalk.com/document/orgapp/jsapi-video-context-seek) | 控制相应video组件的定位 |
| [VideoContext.snapshot](https://open.dingtalk.com/document/orgapp/jsapi-video-context-snapshot) | 控制相应video组件的截图 |

## **缓存**

|  |  |
| --- | --- |
| **API名称** | **API说明** |
| [clearStorage](https://open.dingtalk.com/document/orgapp/jsapi-clear-storage) | 异步清除本地缓存数据 |
| [clearStorageSync](https://open.dingtalk.com/document/orgapp/jsapi-clear-storage-sync) | 同步清除本地storage缓存的数据 |
| [getStorage](https://open.dingtalk.com/document/orgapp/jsapi-get-storage) | 可以获取指定key的单条缓存数据 |
| [getStorageInfo](https://open.dingtalk.com/document/orgapp/jsapi-get-storage-info) | 异步获取当前storage下所有缓存信息的key |
| [getStorageSync](https://open.dingtalk.com/document/orgapp/jsapi-get-storage-sync) | 同步获取缓存数据 |
| [getStorageInfoSync](https://open.dingtalk.com/document/orgapp/jsapi-get-storage-info-sync) | 同步获取当前storage下所有缓存信息的key、已占用空间大小和限制最大的缓存空间大小信息 |
| [removeStorage](https://open.dingtalk.com/document/orgapp/jsapi-remove-storage) | 删除缓存数据 |
| [removeStorageSync](https://open.dingtalk.com/document/orgapp/jsapi-remove-storage-sync) | 同步删除缓存数据 |
| [setStorage](https://open.dingtalk.com/document/orgapp/jsapi-set-storage) | 将数据存储在本地缓存中指定的 key 中，会覆盖掉原来该 key 对应的数据 |
| [setStorageSync](https://open.dingtalk.com/document/orgapp/jsapi-set-storage-sync) | 同步将数据存储在本地缓存中指定的 key 中 |

## **文件**

|  |  |
| --- | --- |
| **API名称** | **API说明** |
| [isLocalFileExist](https://open.dingtalk.com/document/orgapp/jsapi-is-local-file-exist) | 批量检测本地文件是否存在 |
| [openLocalFile](https://open.dingtalk.com/document/orgapp/jsapi-open-local-file) | 打开本地文件 |

## **位置**

|  |  |
| --- | --- |
| **API名称** | **API说明** |
| [getLocation](https://open.dingtalk.com/document/orgapp/jsapi-get-location) | 获取用户当前的地理位置信息 |
| [getLocatingStatus](https://open.dingtalk.com/document/orgapp/jsapi-get-locating-status) | 批量获取连续定位状态 |
| [locateInMap](https://open.dingtalk.com/document/orgapp/jsapi-locate-in-map) | 地图定位 |
| [openLocation](https://open.dingtalk.com/document/orgapp/jsapi-open-location) | 使用内置地图查看位置 |
| [searchMap](https://open.dingtalk.com/document/orgapp/jsapi-search-map) | 唤起地图页面 |
| [stopLocating](https://open.dingtalk.com/document/orgapp/jsapi-stop-locating) | 停止连续定位 |
| [startLocating](https://open.dingtalk.com/document/orgapp/jsapi-start-locating) | 连续获取当前地理位置信息（持续定位） |

## **网络**

|  |  |  |
| --- | --- | --- |
| **类目** | **API名称** | **API说明** |
| **网络请求** | [httpRequest](https://open.dingtalk.com/document/orgapp/jsapi-http-request) | 向指定服务器发起一个跨域 http(s) 请求 |
| **上传下载** | [downloadFile](https://open.dingtalk.com/document/orgapp/jsapi-download-file) | 下载文件资源到本地 |
| [uploadFile](https://open.dingtalk.com/document/orgapp/jsapi-upload-file) | 上传本地资源到开发者服务器 |
| **WebSocket** | [closeSocket](https://open.dingtalk.com/document/orgapp/jsapi-close-socket) | 关闭WebSocket连接 |
| [connectSocket](https://open.dingtalk.com/document/orgapp/jsapi-connect-socket) | 创建一个 WebSocket 的连接 |
| [onSocketOpen](https://open.dingtalk.com/document/orgapp/jsapi-on-socket-open) | 监听WebSocket连接打开事件 |
| [offSocketOpen](https://open.dingtalk.com/document/orgapp/jsapi-off-socket-open) | 取消监听WebSocket连接打开事件 |
| [onSocketError](https://open.dingtalk.com/document/orgapp/jsapi-on-socket-error) | 监听WebSocket错误 |
| [offSocketError](https://open.dingtalk.com/document/orgapp/jsapi-off-socket-error) | 取消监听WebSocket错误 |
| [onSocketClose](https://open.dingtalk.com/document/orgapp/jsapi-on-socket-close) | 监听WebSocket关闭 |
| [offSocketClose](https://open.dingtalk.com/document/orgapp/jsapi-off-socket-close) | 取消监听WebSocket关闭事件 |
| [offSocketMessage](https://open.dingtalk.com/document/orgapp/jsapi-off-socket-message) | 取消监听WebSocket接收到服务器的消息事件 |
| [onSocketMessage](https://open.dingtalk.com/document/orgapp/jsapi-on-socket-message) | 监听WebSocket接收到服务器的消息事件 |
| [sendSocketMessage](https://open.dingtalk.com/document/orgapp/jsapi-send-socket-message) | 通过WebSocket连接发送数据 |

## **设备**

|  |  |  |
| --- | --- | --- |
| **类目** | **API名称** | **API说明** |
| **UUID** | [getDeviceUUID](https://open.dingtalk.com/document/orgapp/jsapi-get-device-uuid) | 获取uuid |
| **系统信息** | [checkAuth](https://open.dingtalk.com/document/orgapp/jsapi-check-auth) | 检查手机权限授权状态 |
| [getSystemInfo](https://open.dingtalk.com/document/orgapp/jsapi-get-system-info) | 获取手机系统信息 |
| [getSystemSettings](https://open.dingtalk.com/document/orgapp/jsapi-get-system-settings) | 打开系统设置 |
| [getSystemInfoSync](https://open.dingtalk.com/document/orgapp/jsapi-get-system-info-sync) | 获取手机系统信息的同步接口 |
| [isScreenReaderEnabled](https://open.dingtalk.com/document/orgapp/jsapi-is-screen-reader-enabled) | 判断是否开启无障碍模式 |
| [rsa](https://open.dingtalk.com/document/orgapp/jsapi-rsa) | 实现rsa加解密 |
| [showAuthGuide](https://open.dingtalk.com/document/orgapp/jsapi-show-auth-guide) | 授权引导 |
| **网络状态** | [getNetworkType](https://open.dingtalk.com/document/orgapp/jsapi-get-network-type) | 获取当前网络状态 |
| [getWifiHotspotStatus](https://open.dingtalk.com/document/orgapp/jsapi-get-wifi-hotspot-status) | 获取热点接入信息 |
| **Wi-Fi** | [connectWifi](https://open.dingtalk.com/document/orgapp/jsapi-connect-wifi) | 连接 Wi-Fi |
| [getWifiList](https://open.dingtalk.com/document/orgapp/jsapi-get-wifi-list) | 获取 Wi-Fi 列表 |
| [getWifiStatus](https://open.dingtalk.com/document/orgapp/jsapi-get-wifi-status) | 获取wifi状态 |
| [getConnectedWifi](https://open.dingtalk.com/document/orgapp/jsapi-get-connected-wifi) | 获取已连接 Wi-Fi 信息 |
| [onGetWifiList](https://open.dingtalk.com/document/orgapp/jsapi-on-get-wifi-list) | 监听获取到 Wi-Fi 列表事件 |
| [offGetWifiList](https://open.dingtalk.com/document/orgapp/jsapi-off-get-wifi-list) | 停止监听已获取 Wi-Fi 列表数据事件 |
| [onWifiConnected](https://open.dingtalk.com/document/orgapp/jsapi-on-wifi-connected) | 监听连接上 Wi-Fi 事件 |
| [offWifiConnected](https://open.dingtalk.com/document/orgapp/jsapi-off-wifi-connected) | 停止监听连接 Wi-Fi 事件 |
| [registerSSID](https://open.dingtalk.com/document/orgapp/jsapi-register-ssid) | 信任该 SSID(iOS) |
| [stopWifi](https://open.dingtalk.com/document/orgapp/jsapi-stop-wifi) | 关闭 Wi-Fi 模块 |
| [startWifi](https://open.dingtalk.com/document/orgapp/jsapi-start-wifi) | 初始化 Wi-Fi 模块 |
| [unregisterSSID](https://open.dingtalk.com/document/orgapp/jsapi-unregister-ssid) | 不再信任该 SSID(iOS) |
| [setWifiList](https://open.dingtalk.com/document/orgapp/jsapi-set-wifi-list) | 设置入参中 wifiList 的 AP 相关信息 |
| **剪贴板** | [getClipboard](https://open.dingtalk.com/document/orgapp/jsapi-get-clipboard) | 获取系统剪贴板的内容 |
| [setClipboard](https://open.dingtalk.com/document/orgapp/jsapi-set-clipboard) | 设置剪切板数据 |
| **振动** | [vibrate](https://open.dingtalk.com/document/orgapp/jsapi-vibrate) | 使用振动功能 |
| [vibrateLong](https://open.dingtalk.com/document/orgapp/jsapi-vibrate-long) | 使用长振动功能 |
| [vibrateShort](https://open.dingtalk.com/document/orgapp/jsapi-vibrate-short) | 使用短振动功能 |
| **低功耗蓝牙** | [connectBLEDevice](https://open.dingtalk.com/document/orgapp/jsapi-connect-bledevice) | 连接低功耗蓝牙设备 |
| [disconnectBLEDevice](https://open.dingtalk.com/document/orgapp/jsapi-disconnect-bledevice) | 断开与低功耗蓝牙设备的连接 |
| [getBLEDeviceServices](https://open.dingtalk.com/document/orgapp/jsapi-get-ble-device-services) | 获取蓝牙设备所有服务 |
| [getBLEDeviceCharacteristics](https://open.dingtalk.com/document/orgapp/jsapi-get-ble-device-characteristics) | 获取蓝牙设备所有特征值 |
| [notifyBLECharacteristicValueChange](https://open.dingtalk.com/document/orgapp/jsapi-notify-ble-characteristic-value-change) | 启用低功耗蓝牙设备特征值变化时的notify功能 |
| [onBLEConnectionStateChanged](https://open.dingtalk.com/document/orgapp/jsapi-on-ble-connection-state-changed) | 监听低功耗蓝牙连接的错误事件，包括设备丢失，连接异常断开等 |
| [offBLEConnectionStateChanged](https://open.dingtalk.com/document/orgapp/jsapi-off-ble-connection-state-changed) | 移除低功耗蓝牙连接状态变化事件的监听 |
| [onBLECharacteristicValueChange](https://open.dingtalk.com/document/orgapp/jsapi-on-ble-characteristic-value-change) | 监听低功耗蓝牙设备的特征值变化的事件 |
| [offBLECharacteristicValueChange](https://open.dingtalk.com/document/orgapp/jsapi-off-ble-characteristic-value-change) | 移除低功耗蓝牙设备的特征值变化事件的监听 |
| [readBLECharacteristicValue](https://open.dingtalk.com/document/orgapp/jsapi-read-ble-characteristic-value) | 读取低功耗蓝牙设备特征值中的数据 |
| [writeBLECharacteristicValue](https://open.dingtalk.com/document/orgapp/jsapi-write-ble-characteristic-value) | 向低功耗蓝牙设备特征值中写入数据 |
| **传统蓝牙** | [closeBluetoothAdapter](https://open.dingtalk.com/document/orgapp/jsapi-close-bluetooth-adapter) | 关闭本机蓝牙模块 |
| [getBluetoothDevices](https://open.dingtalk.com/document/orgapp/jsapi-get-bluetooth-devices) | 获取所有已发现的蓝牙设备 |
| [getBluetoothAdapterState](https://open.dingtalk.com/document/orgapp/jsapi-get-bluetooth-adapter-state) | 获取本机蓝牙模块状态 |
| [getConnectedBluetoothDevices](https://open.dingtalk.com/document/orgapp/jsapi-get-connected-bluetooth-devices) | 获取处于已连接状态的设备 |
| [onBluetoothDeviceFound](https://open.dingtalk.com/document/orgapp/jsapi-on-bluetooth-device-found) | 搜索到新的蓝牙设备时触发此事件 |
| [offBluetoothDeviceFound](https://open.dingtalk.com/document/orgapp/jsapi-off-bluetooth-device-found) | 移除寻找到新的蓝牙设备事件的监听 |
| [onBluetoothAdapterStateChange](https://open.dingtalk.com/document/orgapp/jsapi-on-bluetooth-adapter-state-change) | 监听本机蓝牙状态变化的事件 |
| [offBluetoothAdapterStateChange](https://open.dingtalk.com/document/orgapp/jsapi-off-bluetooth-adapter-state-change) | 停止监听本机蓝牙状态变化的事件 |
| [openBluetoothAdapter](https://open.dingtalk.com/document/orgapp/jsapi-open-bluetooth-adapter) | 初始化小程序蓝牙模块 |
| [stopBluetoothDevicesDiscovery](https://open.dingtalk.com/document/orgapp/jsapi-stop-bluetooth-devices-discovery) | 停止搜寻附近的蓝牙外围设备 |
| [startBluetoothDevicesDiscovery](https://open.dingtalk.com/document/orgapp/jsapi-start-bluetooth-devices-discovery) | 开始搜寻附近的蓝牙外围设备 |
| **扫码** | [scanCard](https://open.dingtalk.com/document/orgapp/jsapi-scan-card) | 扫名片 |
| [scan](https://open.dingtalk.com/document/orgapp/jsapi-scan) | 扫一扫功能 |
| **NFC** | [readNFC](https://open.dingtalk.com/document/orgapp/jsapi-read-nfc) | 读取NFC芯片内容 |
| [writeNFC](https://open.dingtalk.com/document/orgapp/jsapi-write-nfc) | 实现NFC数据写入 |
| **摇一摇** | [clearShake](https://open.dingtalk.com/document/orgapp/jsapi-clear-shake) | 停止摇一摇 |
| [watchShake](https://open.dingtalk.com/document/orgapp/jsapi-watch-shake) | 启动摇一摇 |
| **屏幕亮度** | [getScreenBrightness](https://open.dingtalk.com/document/orgapp/jsapi-get-screen-brightness) | 获取屏幕亮度 |
| [setScreenBrightness](https://open.dingtalk.com/document/orgapp/jsapi-set-screen-brightness) | 设置屏幕亮度 |
| [setKeepScreenOn](https://open.dingtalk.com/document/orgapp/jsapi-set-keep-screen-on) | 设置屏幕常亮 |
| **拨打电话** | [addPhoneContact](https://open.dingtalk.com/document/orgapp/jsapi-add-phone-contact) | 添加手机联系人 |
| **设备电量** | [getBatteryInfo](https://open.dingtalk.com/document/orgapp/jsapi-get-battery-info) | 获取设备电量 |
| **设备方向** | [rotateScreenView](https://open.dingtalk.com/document/orgapp/jsapi-reset-screen-view) | 旋转屏幕 |
| [resetScreenView](https://open.dingtalk.com/document/orgapp/jsapi-rotate-screen-view) | 重置旋转屏幕 |

## **分享**

|  |  |
| --- | --- |
| **API名称** | **API说明** |
| [onShareAppMessage](https://open.dingtalk.com/document/orgapp/jsapi-on-share-app-message) | 自定义该页面的分享内容 |
| [share](https://open.dingtalk.com/document/orgapp/jsapi-share) | 实现分享功能 |
| [showSharePanel](https://open.dingtalk.com/document/orgapp/jsapi-show-share-panel) | 唤起H5或小程序分享面板的API |

## **更新管理**

|  |  |
| --- | --- |
| **API名称** | **API说明** |
| [getUpdateManager](https://open.dingtalk.com/document/orgapp/jsapi-get-update-manager) | 用来管理小程序更新 |
| [UpdateManager.applyUpdate](https://open.dingtalk.com/document/orgapp/jsapi-update-manager-apply-update) | 强制小程序重启并使用新版本 |
| [UpdateManager.onUpdateFailed](https://open.dingtalk.com/document/orgapp/jsapi-update-manager-on-update-failed) | 监听小程序更新失败事件 |
| [UpdateManager.onUpdateReady](https://open.dingtalk.com/document/orgapp/jsapi-update-manager-on-update-ready) | 监听小程序有版本更新事件 |
| [UpdateManager.onCheckForUpdate](https://open.dingtalk.com/document/orgapp/jsapi-update-manager-on-check-for-update) | 监听向钉钉后台请求检查更新结果事件 |

## **钉盘**

|  |  |
| --- | --- |
| **API名称** | **API说明** |
| [chooseDingTalkDir](https://open.dingtalk.com/document/orgapp/jsapi-choose-ding-talk-dir) | 唤起钉盘选择器 |
| [previewFileInDingTalk](https://open.dingtalk.com/document/orgapp/jsapi-preview-file-in-ding-talk) | 预览钉盘文件 |
| [previewImagesInDingTalkBatch](https://open.dingtalk.com/document/orgapp/jsapi-preview-images-in-ding-talk-batch) | 批量预览钉盘图片 |
| [saveFileToDingTalk](https://open.dingtalk.com/document/orgapp/jsapi-save-file-to-ding-talk) | 转存文件到钉盘 |
| [uploadAttachmentToDingTalk](https://open.dingtalk.com/document/orgapp/jsapi-upload-attachment-to-ding-talk) | 上传附件到钉盘，或从钉盘选择文件 |

## **支付**

|  |  |
| --- | --- |
| **API名称** | **API说明** |
| [pay](https://open.dingtalk.com/document/orgapp/jsapi-pay) | 完成支付 |

## **文件**

|  |  |
| --- | --- |
| **API名称** | **API说明** |
| [getFileSystemManager](https://open.dingtalk.com/document/orgapp/jsapi-get-file-system-manager) | 获取FileSystemManager文件管理器 |
| [FileSystemManager.access](https://open.dingtalk.com/document/orgapp/jsapi-file-system-manager-access) | 判断文件或者目录是否存在 |
| [FileSystemManager.appendFile](https://open.dingtalk.com/document/orgapp/jsapi-file-system-manager-append-file) | 向本地用户文件末尾添加内容 |
| [FileSystemManager.copyFile](https://open.dingtalk.com/document/orgapp/jsapi-file-system-manager-copy-file) | 复制文件保存到本地用户目录 |
| [FileSystemManager.getFileInfo](https://open.dingtalk.com/document/orgapp/jsapi-file-system-manager-get-file-info) | 获取本地临时文件、本地缓存文件和本地用户文件的信息 |
| [FileSystemManager.getSavedFileList](https://open.dingtalk.com/document/orgapp/jsapi-file-system-manager-get-saved-file-list) | 获取本地缓存文件列表 |
| [FileSystemManager.mkdir](https://open.dingtalk.com/document/orgapp/jsapi-file-system-manager-mkdir) | 创建本地用户目录 |
| [FileSystemManager.rmdir](https://open.dingtalk.com/document/orgapp/jsapi-file-system-manager-rmdir) | 删除本地用户文件目录 |
| [FileSystemManager.rename](https://open.dingtalk.com/document/orgapp/jsapi-file-system-manager-rename) | 重命名本地用户文件或目录的名称并且可以移动到新目录下 |
| [FileSystemManager.readdir](https://open.dingtalk.com/document/orgapp/jsapi-file-system-manager-readdir) | 获取本地用户文件列表 |
| [FileSystemManager.readFile](https://open.dingtalk.com/document/orgapp/jsapi-file-system-manager-read-file) | 读取本地用户文件的内容 |
| [FileSystemManager.removeSavedFile](https://open.dingtalk.com/document/orgapp/jsapi-file-system-manager-remove-saved-file) | 删除本地缓存文件 |
| [FileSystemManager.stat](https://open.dingtalk.com/document/orgapp/jsapi-file-system-manager-stat) | 获取文件或目录的status对象 |
| [FileSystemManager.saveFile](https://open.dingtalk.com/document/orgapp/jsapi-file-system-manager-save-file) | 本地临时文件保存为本地缓存文件或本地用户文件 |
| [FileSystemManager.unzip](https://open.dingtalk.com/document/orgapp/jsapi-file-system-manager-unzip) | 解压本地用户文件 |
| [FileSystemManager.unlink](https://open.dingtalk.com/document/orgapp/jsapi-file-system-manager-unlink) | 删除本地用户文件 |
| [FileSystemManager.writeFile](https://open.dingtalk.com/document/orgapp/jsapi-file-system-manager-write-file) | 向本地用户目录内写入文件 |

## **办公电话**

|  |  |
| --- | --- |
| **API名称** | **API说明** |
| [callUsers](https://open.dingtalk.com/document/orgapp/jsapi-call-users) | 拨打钉钉电话 |
| [checkBizCall](https://open.dingtalk.com/document/orgapp/jsapi-check-biz-call) | 检查某企业办公电话开通状态 |
| [getCloudCallInfo](https://open.dingtalk.com/document/orgapp/jsapi-get-cloud-call-info) | 查询企业是否已开办公电话 |
| [getCloudCallList](https://open.dingtalk.com/document/orgapp/jsapi-get-cloud-call-list) | 查询话单列表 |
| [makeCloudCall](https://open.dingtalk.com/document/orgapp/jsapi-make-cloud-call) | 发起办公电话呼叫 |
| [quickCallList](https://open.dingtalk.com/document/orgapp/jsapi-quick-call-list) | 拨打单人电话选项 |
| [showCallMenu](https://open.dingtalk.com/document/orgapp/jsapi-show-call-menu) | 唤起拨打电话菜单 |

## **视频**

|  |  |
| --- | --- |
| **API名称** | **API说明** |
| [makeVideoConfCall](https://open.dingtalk.com/document/orgapp/jsapi-make-video-conf-call) | 发起视频会议 |

# **组织关系**

## **通讯录**

|  |  |
| --- | --- |
| **API名称** | **API说明** |
| [complexChoose](https://open.dingtalk.com/document/orgapp/jsapi-complex-choose) | 选择人和部门 |
| [chooseStaffForPC](https://open.dingtalk.com/document/orgapp/jsapi-choose-staff-for-pc) | PC端选择企业内部的人 |
| [choosePhonebook](https://open.dingtalk.com/document/orgapp/jsapi-choose-phonebook) | 选取用户手机联系人 |
| [chooseDepartments](https://open.dingtalk.com/document/orgapp/jsapi-choose-departments) | 选择部门 |
| [chooseUserFromList](https://open.dingtalk.com/document/orgapp/jsapi-choose-user-from-list) | 选取单个自定义联系人 |
| [chooseExternalUsers](https://open.dingtalk.com/document/orgapp/jsapi-choose-external-users) | 选择外部联系人 |
| [editExternalUser](https://open.dingtalk.com/document/orgapp/jsapi-edit-external-user) | 编辑外部联系人 |

## **专属开放**

|  |  |
| --- | --- |
| **API名称** | **API说明** |
| [exclusiveLiveCheck](https://open.dingtalk.com/document/orgapp/jsapi-exclusive-live-check) | 专属实人认证 |
| [getUserExclusiveInfo](https://open.dingtalk.com/document/orgapp/jsapi-get-user-exclusive-info) | 获取钉钉客户端是否为专属钉钉 |

# **身份与免登**

## **获取凭证**

|  |  |
| --- | --- |
| **API名称** | **API说明** |
| [getAuthCode](https://open.dingtalk.com/document/orgapp/jsapi-get-auth-code) | 获取小程序免登授权码 |
| [getOperateAuthCode](https://open.dingtalk.com/document/orgapp/jsapi-get-operate-auth-code) | 获取微应用反馈式操作的临时授权码 |
| [requestAuthInfo](https://open.dingtalk.com/document/orgapp/jsapi-request-auth-info) | 唤起授权弹窗，获取用户授权 |

# **即时通讯**

## **会话管理**

|  |  |
| --- | --- |
| **API名称** | **API说明** |
| [chooseChat](https://open.dingtalk.com/document/orgapp/jsapi-choose-chat) | 选择会话 |
| [openChatByChatId](https://open.dingtalk.com/document/orgapp/jsapi-open-chat-by-chat-id) | 打开对应会话 |
| [openChatByUserId](https://open.dingtalk.com/document/orgapp/jsapi-open-chat-by-user-id) | 打开与某个用户的聊天页面 |
| [openChatByConversationId](https://open.dingtalk.com/document/orgapp/jsapi-open-chat-by-conversation-id) | 跳转到对应会话 |

## **DING**

|  |  |
| --- | --- |
| **API名称** | **API说明** |
| [createDing](https://open.dingtalk.com/document/orgapp/jsapi-create-ding) | 发起DING |
| [createDingForPC](https://open.dingtalk.com/document/orgapp/jsapi-create-ding-for-pc) | 发起PC端发钉 |