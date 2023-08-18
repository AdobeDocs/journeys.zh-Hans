---
product: adobe campaign
title: getListItem
description: 了解函数gstListItem
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 21%

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
| list | listString |
| list | listBoolean |
| list | listInteger |
| list | listDecimal |
| list | listDuration |
| list | listDateTime |
| list | listDateTimeOnly |
| list | listDateOnly |
| index | 整数 |

## 签名和返回的类型

`getListItem(<listInteger>,<index>)`

返回整数。

`getListItem(<listDecimal>,<index>)`

返回小数。

`getListItem(<listString>,<index>)`

返回字符串。

`getListItem(<listDateTimeOnly>,<index>)`

返回不考虑时区的日期时间。

`getListItem(<listDateTime>,<index>)`

返回日期时间。

`getListItem(<listDateOnly>,<index>)`

返回日期列表。

`getListItem(<listBoolean>,<index>)`

返回布尔值。

`getListItem(<listDuration>,<index>)`

返回持续时间。

## 示例

`getListItem([10, 2, 3], 1)`

返回“2”

`getListItem(["A", "B", "C"], 2)`
返回“C”

具有事件字段&quot;event.appVersion&quot;且值为&quot;20.45.2.3434&quot;的示例

`split(@{event.appVersion}, "\\.")`

返回结果 `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

返回“20”
