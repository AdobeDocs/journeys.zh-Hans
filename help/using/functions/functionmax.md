---
title: max
description: 了解函数max
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 4%

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
