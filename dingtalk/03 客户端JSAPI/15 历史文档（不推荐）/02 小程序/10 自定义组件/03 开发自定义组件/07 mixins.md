---
title: "mixins"
source: "https://open.dingtalk.com/document/development/mini-app-mixins"
category: "客户端JSAPI / 历史文档（不推荐） / 小程序 / 自定义组件 / 开发自定义组件"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-mini-app-mixins_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-mini-app-mixins_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-09-17开发者有时候可能会实现多个自定义组件，而这些自定义组件可能会有些公共逻辑要处理，为此，小程序提供了mixins。

**重要**

* 每一个 mixin 只能包含 props、data、methods、didMount、didUpdate、didUnmount等属性。
* 多个 mixin 中的属性 key 要确保不同，否则会报错。

```javascript
// /mixins/lifecycle.js
export default {
  didMount(){},
  didUpdate(prevProps,prevData){},
  didUnmount(){},
};
```

```javascript
// /pages/components/xx/index.js
import lifecycle from '../../mixins/lifecycle';

const initialState = {
  data: {
    y: 2
  },
};

const defaultProps = {
  props: {
    a: 3,
  },
};

const methods = {
  methods: {
    onTapHandler() {},
  },
}
```