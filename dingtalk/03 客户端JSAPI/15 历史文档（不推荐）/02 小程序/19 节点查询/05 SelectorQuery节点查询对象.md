---
title: "SelectorQuery节点查询对象"
source: "https://open.dingtalk.com/document/development/selectorquery"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 节点查询"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-selectorquery_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-selectorquery_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17SelectorQuery 是节点查询对象类，包含以下方法。

## selectorQuery.select(selector)

选择当前第一个匹配选择器的节点，选择器支持 id 选择器以及 class 选择器。

## selectorQuery.selectAll(selector)

选择所有匹配选择器的节点，选择器支持 id 选择器以及 class 选择器。

## selectorQuery.selectViewport()

选择窗口对象。

## selectorQuery.boundingClientRect()

将当前选择节点的位置信息放入查询结果，类似 dom 的 getBoundingClientRect， 返回对象包含 width/height/left/top/bottom/right。如果当前节点为窗口对象则只返回 width/height。

## selectorQuery.scrollOffset()

将当前选择节点的滚动信息放入查询结果，返回对象包含 scrollTop/scrollLeft。

## selectorQuery.exec(callback)

将查询结果放入 callback 回调中。查询结果为数组，每项为一次查询的结果，如果当前是节点列表，则单次查询结果也为数组。注意 exec 必须放到 Page onReady 后调用。

示例代码：

```
节点 all1

节点 all2

节点 one

  独立滚动区域
```

```sql
Page({
  onReady() {
    dd.createSelectorQuery()
      .select('#non-exists').boundingClientRect()
      .select('#one').boundingClientRect()
      .selectAll('.all').boundingClientRect()
      .select('#scroll').scrollOffset()
      .selectViewport().boundingClientRect()
      .selectViewport().scrollOffset().exec((ret) => {
      console.log(JSON.stringify(ret, null, 2));
    });
  },
});
```

结果ret：

```
[
  null,
  {
    "x": 1,
    "y": 2,
    "width": 1367,
    "height": 18,
    "top": 2,
    "right": 1368,
    "bottom": 20,
    "left": 1
  },
  [
    {
      "x": 1,
      "y": -34,
      "width": 1367,
      "height": 18,
      "top": -34,
      "right": 1368,
      "bottom": -16,
```