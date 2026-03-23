---
title: "JsonPath"
source: "https://help.h3yun.com/contents/1105/2179.html"
category: "用戶手冊 / 插件 / 第三方连接 / JsonPath"
updated: 2025-12-25
tags:
  - h3yun
  - 用戶手冊
---
JSON是一种轻量级的数据交换格式，因为JSON结构清晰、易读易写易解析等优势，大部分第三方返回数据都支持JSON格式，而JsonPath用于从JSON中分析和提取指定信息。

## 示例

通过一个简单示例，了解在不同场景，如何配置JsonPath获取数据作为返回参数值，[前往Json Path在线解析平台](https://jsonpath.com/ "前往Json Path在线解析平台")，将下方示例数据复制粘贴至左侧Inputs，根据下方表格编辑调整Json Path语法，右侧Evaluation Results是输出结果。

```json
{
    "trade_id": 100202008162234,
    "total_price": 358.85,
    "product": {
	"clothes": {
            "name": "衬衫",
            "price": 198.00
        },
	"drink": {
            "name": "光明牛奶",
	    "volume": "250ml",
            "price": 10.95
        },
        "book": [
            {
                "category": "经济",
                "author": "曼昆 N.Gregory Mankiw",
                "name": "经济学原理",
                "price": 89.60
            },
            {
                "category": "教育",
                "author": "曲一线",
                "name": "五年高考三年模拟",
                "price": 60.30
            }
        ]
    }
}
```

| **jsonpath** | **输出结果** | **数据字段值** | **说明** |
| --- | --- | --- | --- |
| $.total\_price | \[
      358.85
\] | 358.85 | 总价格 |
| $.product.drink.name | \[
      "光明牛奶"
\] | 光明牛奶 | 饮料商品的名称 |
| $..name | \[
      "衬衫",
      "光明牛奶",
      "经济学原理",
      "五年高考三年模拟"
\] | 值1：衬衫
值2：光明牛奶
值3：经济学原理
值4：五年高考三年模拟 | 所有商品的名称 |
| $..price | \[
      198,
      10.95,
      89.6,
      60.3
\] | 值1：198
值2：10.95
值3：89.6
值4：60.3 | 所有商品的价格 |
| $.product.book\[\*\].name | \[
      "经济学原理",
      "五年高考三年模拟"
\] | 值1：经济学原理
值2：五年高考三年模拟 | 所有书籍商品的名称 |
| $.product.book\[0\].author | \[
      "曼昆 N.Gregory   Mankiw"
\] | 曼昆 N.Gregory Mankiw | 第一本书籍商品的作者 |
| $.product.\[-1:\].name | \[   "五年高考三年模拟" \] | 五年高考三年模拟 | 最后一件商品的名称 |
| $.product\[?(@.volume)\].price | \[
      10.95
\] | 10.95 | 有容量的商品的价格 |
| $.product\[?(@.price   < 50)\].name | \[
      "光明牛奶"
\] | 光明牛奶 | 价格小于50的商品的名称 |
| $.product.\[?(@.name   == '经济学原理')\].price | \[
      89.6
\] | 89.6 | 名称为经济学原理的商品价格 |
| $.product.drink | \[
      {
        "name":   "光明牛奶",
        "volume":   "250ml",
        "price": 10.95
      }
\] | {
        "name":   "光明牛奶",
        "volume":   "250ml",
        "price": 10.95
}
   
    注：不建议这么配置 | 饮料商品的完整信息 |
| $.product.book\[\*\] | \[
      {
        "category":   "经济",
        "author": "曼昆   N.Gregory Mankiw",
        "name":   "经济学原理",
        "price": 89.6
      },
      {
        "category":   "教育",
        "author":   "曲一线",
        "name": "五年高考三年模拟",
        "price": 60.3
      }
\] | 值1：
    {
        "category":   "经济",
        "author": "曼昆   N.Gregory Mankiw",
        "name":   "经济学原理",
        "price": 89.6
    }
   
值2：
    {
        "category":   "教育",
        "author":   "曲一线",
        "name":   "五年高考三年模拟",
        "price": 60.3
    }
   
**注：不建议这么配置** | 书籍商品的完整信息 |

![[2179_ad1b1f8a7379bce2.png]]![[2179_ea96a6bc684de412.png]]![[2179_500565ad12fa8463.png]]![[2179_b3e99647cd5bef36.png]]![[2179_7a448e4b2f6e5e84.png]]

## 调试方式1

通过第三方服务的API接口文档，获取返回数据示例（第三方通常提供返回示例数据），复制到[JsonPath在线解析平台](https://jsonpath.com/ "JsonPath在线解析平台")，配置JsonPath调试。

例如阿里云API市场的快递查询服务，除了正常返回示例中的返回参数，建议同时配置返回参数获取失败时的错误提示。

![[2179_222f57bfb80a72c9.png]]![[2179_6461096aa885831d.png]]

## 调试方式2

在插件中心配置连接时，如果账户和请求配置正确，给请求参数配置默认值，添加希望能获取的返回参数（只需填写返回参数名称），点击调试（调试也就是调用）。在调试弹窗中，右侧是完整返回数据，左侧是返回参数、Json Path和Json Path获取的参数值，调整Json Path直到获取到正确数据作为返回参数值，点击确定。

例如阿里云API市场的运营商三要素验证，填写请求参数默认值（身份证号、手机号、姓名），添加希望获取的返回数据，点击调试，在调试弹窗中调整Json Path。

![[2179_8ed9e83d2ecdcd2b.png]]![[2179_d1a5ba8d155d2d.png]]
