---
product: adobe campaign
title: toDateTimeOnly
description: 了解函数toDateTime
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b19adbd0-8449-4bd4-bc4d-f1f305f87cb0
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 16%

---

# toDateTimeOnly{#toDateTimeOnly}

将参数值转换为仅限日期时间的值。

## 类别

转化

## 函数语法

`toDateTimeOnly(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 日期时间(ISO-8601或“YYYY-MM-DD”格式（XDM日期格式） | 字符串 |
| 日期时间 | dateTime |

## 签名和返回的类型

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

不考虑时区而返回日期时间。

## 示例

`toDateTimeOnly ("2016-08-18")`

返回表示2016-08-18T00的dateTime:00:00.000

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
