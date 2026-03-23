---
title: "FilterCriteria"
source: "https://open.dingtalk.com/document/development/filtercriteria"
category: "客户端JSAPI / 酷应用 / 文档酷应用 / API参考文档"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-filtercriteria_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-filtercriteria_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

## copy()

根据当前 FilterCriteria 生成新的 FilterCriteriaBuilder。

### 返回结果

FilterCriteriaBuilder - 新的FilterCriteriaBuilder。

### 示例代码

```javascript
const builder = criteria.copy();
```

## getVisibleValues()

获取设置的可见值。

### 返回结果

string[] | null - 可见值。

### 示例代码

```
builder.getVisibleValues();
```

## getVisibleFontColor()

获取设置的可见字体颜色。

### 返回结果

Color ｜ null - 可见字体颜色。

### 示例代码

```
builder.getVisibleFontColor();
```

## getVisibleBackgroundColor()

获取设置的可见单元格颜色。

### 返回结果

Color ｜ null - 可见单元格颜色。

### 示例代码

```
builder.getVisibleBackgroundColor();
```

## getVisibleConditions()

获取设置的筛选条件。

### 返回结果

FilterCondition[] | null - 筛选条件列表。

### 示例代码

```
builder.getVisibleConditions();
```

## getVisibleConditionsOperator()

获取设置的两个筛选条件关系。

### 返回结果

'and' | 'or' | null - 筛选条件关系。

### 示例代码

```
builder.getVisibleConditionsOperator();
```