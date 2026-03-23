---
title: "关于 didMount"
source: "https://docs.aliwork.com/docs/yida_support/lbtl0t/ocmxyv/fa52gl"
category: "用戶手冊 / 开发者功能（需有代码基础） / JS 动作面板 - 前端代码开发"
updated: 
tags:
  - yida
  - 用戶手冊
---
1.  当页面渲染完毕后马上调用下面的函数，这个函数是在当前页面 - 设置 - 生命周期 - 页面加载完成时中被关联的。

**注意：自定页面需要手动绑定一次，否则不会触发。**

![[yida_support-lbtl0t-ocmxyv-fa52gl_1657081797045-bcd7727c-1aee-4c3b-b591-aca821abe231.png]]

2.  在 didMount 里的代码在表单的提交页面和详情页面都会执行，在某些场景下就需要进行判断，判断方式如下：

```jsx
this.utils.isSubmissionPage()// 判断表单是否是提交页this.utils.isViewPage()// 判断表单是否是详情页
```