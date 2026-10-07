---
product: adobe campaign
title: toDateTimeOnly
description: 了解函数toDateTime
feature: Journeys
role: Developer
level: Experienced
exl-id: b19adbd0-8449-4bd4-bc4d-f1f305f87cb0
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
source-wordcount: '60'
ht-degree: 15%
---
# toDateTimeOnly{#toDateTimeOnly}

将参数值转换为仅日期时间值。

## 类别

转化

## 函数语法

`toDateTimeOnly(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| ISO-8601或“YYYY-MM-DD”格式的日期时间（XDM日期格式） | 字符串 |
| 日期时间 | dateTime |

## 签名和返回的类型

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--
`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`
-->

返回不考虑时区的日期时间。

## 示例

`toDateTimeOnly ("2016-08-18")`

返回表示2016-08-18T00:00:00.000的日期时间

`toDateTimeOnly(now())`

<!--
`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.
-->
