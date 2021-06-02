---
product: adobe campaign
title: max
description: 了解函数max
feature: 历程
role: Data Engineer
level: Experienced
exl-id: 116713e0-7bbd-4150-8495-f87034eafb5f
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 6%

---

# max{#max}

返回一组表达式中的最大值（以列表或两个表达式的形式给定）。 将忽略空值。

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

返回日期时间，而不考虑时区。

`max(<listDateTime>)`

返回日期时间。

`max(<listDecimal>)`

返回小数。

`max(<decimal>,<decimal>)`

返回小数。

`max(<duration>,<duration>)`

返回持续时间。

`max(<dateTime>,<dateTime>)`

返回日期时间。

`max(<dateTimeOnly>,<dateTimeOnly>)`

返回日期时间，而不考虑时区。

`max(<integer>,<integer>)`

返回整数。

## 示例

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

返回10。

`max([10,null,8])`

返回10。
