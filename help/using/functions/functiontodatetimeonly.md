---
product: adobe campaign
solution: Journey Orchestration
title: toDateTimeOnly
description: 了解函数toDateTime
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 8%

---


# toDateTimeOnly{#toDateTimeOnly}

将参数值转换为仅限日期时间的值。

## 类别

转换

## 函数语法

`toDateTimeOnly(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| ISO-8601格式的日期时间 | 字符串 |
| 日期时间 | dateTime |

## 签名和返回类型

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

返回日期时间，不考虑时区。

## 示例

`toDateTimeOnly ("2016-08-18T23:17:59.123Z")`

返回2016-08-18T23:17:59.123。

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
