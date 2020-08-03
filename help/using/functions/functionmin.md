---
title: min
description: 了解函数min
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 4%

---


# min {#min}

返回一组表达式中的最小值，以列表或两个表达式的形式给定。 忽略null值。

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

## 签名和返回类型

`min(<listDuration>)`

返回持续时间。

`min(<listInteger>)`

返回持续时间。

`min(<listDateTimeOnly>)`

返回日期时间，不考虑时区。

`min(<listDateTime>)`

返回日期时间。

`min(<listDecimal>)`

返回十进制。

`min(<decimal>,<decimal>)`

返回十进制。

`min(<duration>,<duration>)`

返回持续时间。

`min(<dateTime>,<dateTime>)`

返回日期时间。

`min(<dateTimeOnly>,<dateTimeOnly>)`

返回日期时间，不考虑时区。

`min(<integer>,<integer>)`

返回整数。

## 示例

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

返回3。

`min([10,null,8])`

返回8。
