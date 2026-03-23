---
title: "LinkBlock 链接块"
source: "https://docs.aliwork.com/docs/developer/components/basic/linkBlock"
category: "開發者手冊 / 组件 / 基础组件"
updated: 
tags:
  - yida
  - 開發者手冊
---
链接块容器，功能同链接组件，不过可以嵌入其他内容，例如图片等。

## 何时使用

-   切换访问当前应用的其他页面；
-   跳转到外部页面。

## 组件示例

## 组件属性

| 属性 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
|
disabled

 | 是否禁用，禁用后点击链接块不会进行页面跳转 | boolean | false |
|

isBlank

 | 是否新开页面 | boolean | false |
|

page

 | 内部页面Uuid，当 **type** 属性为page时生效 | string |

\-

 |
|

params

 | url 查询参数，多用于页面跳转传参 | Record<string, string> |

\-

 |
|

type

 | 链接类型，page：内部页面、url：外部链接 | 'page' | 'url' | 'page' |
|

url

 | 链接地址，点击链接即可跳转对应页面，当 **type** 属性为url时生效 | string |

\-

 |