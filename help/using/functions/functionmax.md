---
product: adobe campaign
title: max
description: 了解函数max
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 116713e0-7bbd-4150-8495-f87034eafb5f
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '92'
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
