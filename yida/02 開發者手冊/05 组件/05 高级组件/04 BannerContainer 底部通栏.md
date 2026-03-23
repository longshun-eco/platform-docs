---
title: "BannerContainer 底部通栏"
source: "https://docs.aliwork.com/docs/developer/components/advanced/bannerContainer"
category: "開發者手冊 / 组件 / 高级组件"
updated: 
tags:
  - yida
  - 開發者手冊
---
底部通栏 组件允许你在页面底部添加内容，并且内容固定在页面底部和占据通栏。

## 何时使用

-   需要在页面底部添加内容时，例如添加版权信息等。

## 组件示例

## 组件属性

| 属性 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
|
autoWidth

 | 是否开启自适应宽度 | boolean | false |
|

containerWidth

 | 设置容器宽度，可以用px或%，例如：100px、50% | string |

\-

 |
|

contentWidth

 | 设置内容宽度，可以用px或%，例如：100px、50% | string |

\-

 |
|

extra

 | 自定义内容 | ReactNode |

\-

 |
|

getRefContainer

 | 设置自定义挂载容器 | () => React.HTMLElement |

\-

 |
|

layout

 | 设置布局方式，h代表横向、v代表纵向 | 'h' | 'v' | 'h' |