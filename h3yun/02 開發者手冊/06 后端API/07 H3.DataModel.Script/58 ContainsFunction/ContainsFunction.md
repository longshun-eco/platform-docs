---
title: "ContainsFunction"
source: "https://help.h3yun.com/contents/442/629.html"
category: "開發者手冊 / 后端API / H3.DataModel.Script / ContainsFunction"
updated: 2025-12-17
tags:
  - h3yun
  - 開發者手冊
---
类名 : ContainsFunction
说明 : 包含函数。 语法： Contains(A, B)，A是否包含B，返回值是bool类型的值。其中，对于字符串的处理时不区分大小写的 例子： Contains(\[S1, s2, s3\], s1)返回true Contains("hello world", "hello")返回true Contains(\[1, 2, 3\], 4)返回false