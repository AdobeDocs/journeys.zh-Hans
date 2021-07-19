---
product: adobe campaign
title: getListItem
description: 了解gstListItem函数
feature: 历程
role: Data Engineer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 18%

---

# getListItem {#gestListItem}

返回给定索引处列表的项目。

## 类别

列表

## 函数语法

`getListItem(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| list | listString |
| 列表 | listBoolean |
| 列表 | listInteger |
| 列表 | listDecimal |
| 列表 | listDuration |
| 列表 | listDateTime |
| 列表 | listDateTimeOnly |
| index | 整数 |

## 签名和返回类型

`getListItem(<listInteger>,<index>)`

返回整数列表。

`getListItem(<listDecimal>,<index>)`

返回小数列表。

`getListItem(<listString>,<index>)`

返回字符串列表。

`getListItem(<listDateTimeOnly>,<index>)`

返回不考虑时区的日期时间列表。

`getListItem(<listDateTime>,<index>)`

返回datetimes列表。

`getListItem(<listBoolean>,<index>)`

返回布尔值列表。

`getListItem(<listDuration>,<index>)`

返回持续时间列表。

## 示例

`getListItem([10, 2, 3], 1)`

返回“2”

`getListItem(["A", "B", "C"], 3)`
返回“C”

事件字段为“event.appVersion”且值为的示例：&quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

返回结果 `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

返回“20”
