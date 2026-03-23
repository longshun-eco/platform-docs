---
title: "BizDataType"
source: "https://help.h3yun.com/contents/453/671.html"
category: "開發者手冊 / 后端API / H3.Data / BizDataType"
updated: 2025-12-20
tags:
  - h3yun
  - 開發者手冊
---
类名 : BizDataType
说明 : 数据项的逻辑类型 
成员 : 

| 名称 | 说明 |
| --- | --- |
| Unspecified | 空值 |
| Bool | 逻辑型 |
| DateTime | 日期型 |
| Double | 双精度数值型 |
| Int | 整数 |
| Long | 长整数 |
| String | 长文本 |
| ShortString | 短文本 |
| ByteArray | 二进制流 |
| Image | 图片类型 |
| File | 未指定类型的附件 |
| TimeSpan | 时间段型 |
| Unit | 参与者（单人） |
| UnitArray | 参与者（多人） |
| Html | Html |
| Xml | Xml |
| BizObject | 业务对象 |
| BizObjectArray | 业务对象数组 |
| BizStructure | 业务结构 |
| BizStructureArray | 业务结构数组 |
| Association | 关联到其他的对象，这种字段在表单上通常是以开窗查询的形式出现 |
| AssociationArray | 关联对象数组 |
| Map | 地图类型,存json格式：{Address:"",Point:{lat:32323.43,lng:323.232}} |
| Address | 地址类型,存json格式:{"Province":"福建省","City":"泉州市","Town":"惠安县","Detail":"32323"} |
| Formula | 公式型控件 |