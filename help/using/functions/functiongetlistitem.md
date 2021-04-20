---
product: adobe campaign
solution: Journey Orchestration
title: getListItem
description: 了解gstListItem函数
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 4%

---


# getListItem {#gestListItem}

返回给定索引处的列表项。

## 类别

列表

## 函数语法

`getListItem(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 列表 | listString |
| 列表 | listBoolean |
| 列表 | listInteger |
| 列表 | listDecimal |
| 列表 | listDuration |
| 列表 | listDateTime |
| 列表 | listDateTimeOnly |
| 索引 | 整数 |

## 签名和返回类型

`getListItem(<listInteger>,<index>)`

返回整数列表。

`getListItem(<listDecimal>,<index>)`

返回一列表小数。

`getListItem(<listString>,<index>)`

返回字符串列表。

`getListItem(<listDateTimeOnly>,<index>)`

返回日期时间列表，不考虑时区。

`getListItem(<listDateTime>,<index>)`

返回datetime的列表。

`getListItem(<listBoolean>,<index>)`

返回一列表布尔语。

`getListItem(<listDuration>,<index>)`

返回持续时间的列表。

## 示例

`getListItem([10, 2, 3], 1)`

返回“2”

`getListItem(["A", "B", "C"], 3)`
返回“C”

事件字段为“事件.appVersion”且值为：&quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

返回`["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

返回“20”