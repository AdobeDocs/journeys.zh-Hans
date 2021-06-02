---
product: adobe campaign
title: min
description: 了解函数min
feature: 历程
role: Data Engineer
level: Experienced
exl-id: 7e13a08c-c51a-4d40-a3e2-ef70bd3edca5
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 6%

---

# min {#min}

返回一组表达式中的最小值（以列表或两个表达式的形式提供）。 将忽略空值。

## 类别

聚合

## 函数语法

`min(<parameters>)`

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

`min(<listDuration>)`

返回持续时间。

`min(<listInteger>)`

返回持续时间。

`min(<listDateTimeOnly>)`

返回日期时间，而不考虑时区。

`min(<listDateTime>)`

返回日期时间。

`min(<listDecimal>)`

返回小数。

`min(<decimal>,<decimal>)`

返回小数。

`min(<duration>,<duration>)`

返回持续时间。

`min(<dateTime>,<dateTime>)`

返回日期时间。

`min(<dateTimeOnly>,<dateTimeOnly>)`

返回日期时间，而不考虑时区。

`min(<integer>,<integer>)`

返回整数。

## 示例

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

返回3。

`min([10,null,8])`

返回8。
