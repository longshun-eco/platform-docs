---
title: "OperatorParser"
source: "https://help.h3yun.com/contents/439/620.html"
category: "開發者手冊 / 后端API / H3.DataModel.Script / OperatorParser"
updated: 2025-12-23
tags:
  - h3yun
  - 開發者手冊
---
类名 : OperatorParser
说明 : 操作符解析器 
方法名称 : IsOperator(System.String,System.Boolean,System.Int32@)

| 参数 | 说明 |
| --- | --- |
| "S" | 要解析操作符的整个表达式 |
| "IsFirstOperator" | 当前的操作符是否是第一个操作符，比如操作符+，如果是第一个操作符的话，就表示正号，否则则表示是加号 |
| "Pos" | 要解析的开始位置，解析完毕后，会在这里记录解析后的字符的位置 |
| 返回值 |  |
| 操作符 |  |