---
title: "Filter"
source: "https://open.dingtalk.com/document/development/filter"
category: "客户端JSAPI / 酷应用 / 文档酷应用 / API参考文档"
updated: 
tags:
  - dingtalk
  - 客户端JSAPI
---
![[development-filter_O1CN01Zx4PED22rkUkmRe1L_!!6000000007174-2-tps-226-40.png]]![[development-filter_O1CN01UwOv1C27lrTuGFj2D_!!6000000007838-2-tps-17-30.png]]

更新于 2025-08-27

## getId()

获取 ID。

### 返回结果

string - ID。

### 示例代码

```javascript
const filterId = filter.getId();
```

## getRange()

获取当前筛选区域。

### 返回结果

Range | null - 筛选所在的 Range。

### 示例代码

```javascript
const range = filter.getRange();
```

## delete()

移除当前 filter。

### 返回结果

void -

### 示例代码

```sql
filter.delete();
```

## getColumnFilterCriteria(column)

获取指定列的筛选规则实例。

### 返回结果

FilterCriteria | null - 筛选规则。

### 参数说明

| 参数 | 类型 | 是否必传 | 说明 |
| --- | --- | --- | --- |
| column | number | 是 | 相对于 filterRange 首列的偏移量。 |

### 示例代码

```javascript
const filterCriteria = filter.getColumnFilterCriteria(0);
```

## setColumnFilterCriteria(column, filterCriteria)

设置指定列的筛选规则。

### 返回结果

Filter - 当前Filter实例。

### 参数说明

| 参数 | 类型 | 是否必传 | 说明 |
| --- | --- | --- | --- |
| column | number | 是 | 相对于筛选区域首列的偏移量。 |
| filterCriteria | FilterCriteria | 是 | 筛选规则。 |

### 示例代码

```java
const criteria = Workbook.newFilterCriteriaBuilder().
 setVisibleValues(['A', 'B', 'C']).
  build();
filter.setColumnFilterCriteria(0, criteria);
```

## clearColumnFilterCriteria(column)

移除指定列的筛选规则。

### 返回结果

Filter - 当前Filter实例。

### 参数说明

| 参数 | 类型 | 是否必传 | 说明 |
| --- | --- | --- | --- |
| column | number | 是 | 相对于筛选区域首列的偏移量。 |

### 示例代码

```
filter.clearColumnFilterCriteria(0);
```

## sort(field)

筛选排序。

### 返回结果

Filter - 当前Filter实例。

### 参数说明

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| 参数 | 类型 | 说明 |
| field | SortField | number  类型是number时，指定排序按照筛选区域的首列的偏移量，降序排序 | 排序规则。 |

### 示例代码

```
filter.sort({ column: 0, ascending: false });
filter.sort(0);
```

## getColumnSortState(column)

获取排序状态。

### 返回结果

'none' | 'ascending' | 'descending' - 排序状态，依次代表无排序、升序和降序。

### 参数说明

| 参数 | 类型 | 说明 |
| --- | --- | --- |
| column | number | 相对于筛选区域首列的偏移量。 |

### 示例代码

```javascript
const state = filter.getColumnSortState(0);
```