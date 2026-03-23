---
title: "data"
source: "https://open.dingtalk.com/document/development/mini-app-data"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 自定义组件 / 开发自定义组件"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mini-app-data_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mini-app-data_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17data 为组件的局部状态，和页面一样，可以通过this.setData更改，会触发组件的重新渲染；也可以通过this.$spliceData做数据的更改。

详情请参考[注册小程序页面](/document/dingstart/register-a-mini-program-page-1)。

**示例代码**

```
// /components/counter/index.js
Component({
  data: { counter: 0 }
});
```

```json
{{counter}}
```

```
// /components/counter/index.json
{
  "component": true,
}
```

以上代码分别实现了自定义组件的三个要素：js、axml、json。然后我们在页面上就可以使用了。 首先需要在页面的 json 文件中声明依赖的组件，和组件的声明依赖方式相同。

```
// /pages/index/index.json
{
  "usingComponents": {
    "my-component": "/components/counter/index"
  }
}
```

然后在页面的 axml 中就可以使用了。

```

```

页面输出：

```

```