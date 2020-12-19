---
product: adobe campaign
solution: Journey Orchestration
title: max
description: 了解函数max
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# max{#max}

返回一组表达式中的最大值，该列表以或两个表达式的形式给定。 忽略null值。

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

## 签名和返回类型

`max(<listDuration>)`

返回持续时间。

`max(<listInteger>)`

返回持续时间。

`max(<listDateTimeOnly>)`

返回日期时间，不考虑时区。

`max(<listDateTime>)`

返回日期时间。

`max(<listDecimal>)`

返回十进制。

`max(<decimal>,<decimal>)`

返回十进制。

`max(<duration>,<duration>)`

返回持续时间。

`max(<dateTime>,<dateTime>)`

返回日期时间。

`max(<dateTimeOnly>,<dateTimeOnly>)`

返回日期时间，不考虑时区。

`max(<integer>,<integer>)`

返回整数。

## 示例

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

返回10。

`max([10,null,8])`

返回10。
