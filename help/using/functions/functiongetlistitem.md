---
product: adobe campaign
title: getListItem
description: 了解函数gstListItem
feature: Journeys
role: Developer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 19%
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

返回`["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

返回“20”
