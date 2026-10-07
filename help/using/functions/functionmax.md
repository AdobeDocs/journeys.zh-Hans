---
product: adobe campaign
title: max
description: 了解函数max
feature: Journeys
role: Developer
level: Experienced
exl-id: 116713e0-7bbd-4150-8495-f87034eafb5f
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
source-wordcount: '94'
ht-degree: 7%
---
# max{#max}

返回一组表达式中的最大值，这些表达式以列表或两个表达式形式给定。 Null值将被忽略。

## 类别

聚合

## 函数语法

`max(<parameter>)`

## 参数

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* listDateOnly
* 持续时间
* 整数
* 小数
* dateTime
* dateTimeOnly

## 签名和返回的类型

`max(<listDuration>)`

返回持续时间。

`max(<listInteger>)`

返回持续时间。

`max(<listDateTimeOnly>)`

返回不考虑时区的日期时间。

`max(<listDateTime>)`

返回日期时间。

`max(<listDateOnly>)`

返回日期。

`max(<listDecimal>)`

返回小数。

`max(<decimal>,<decimal>)`

返回小数。

`max(<duration>,<duration>)`

返回持续时间。

`max(<dateTime>,<dateTime>)`

返回日期时间。

`max(<dateTimeOnly>,<dateTimeOnly>)`

返回不考虑时区的日期时间。

`max(<integer>,<integer>)`

返回整数。

## 示例

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

返回10。

`max([10,null,8])`

返回10。
