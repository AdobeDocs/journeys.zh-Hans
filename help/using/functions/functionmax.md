---
product: adobe campaign
title: max
description: 瞭解函式max
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

傳回一組運算式中的最大值，以清單或兩個運算式形式給出。 Null值會被忽略。

## 类别

聚合

## 函式語法

`max(<parameter>)`

## 参数

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* listDateOnly
* 持續時間
* 整数
* 小數
* dateTime
* dateTimeOnly

## 簽章和傳回的型別

`max(<listDuration>)`

傳回持續時間。

`max(<listInteger>)`

傳回持續時間。

`max(<listDateTimeOnly>)`

傳回不考慮時區的日期時間。

`max(<listDateTime>)`

傳回日期時間。

`max(<listDateOnly>)`

傳回日期。

`max(<listDecimal>)`

傳回小數。

`max(<decimal>,<decimal>)`

傳回小數。

`max(<duration>,<duration>)`

傳回持續時間。

`max(<dateTime>,<dateTime>)`

傳回日期時間。

`max(<dateTimeOnly>,<dateTimeOnly>)`

傳回不考慮時區的日期時間。

`max(<integer>,<integer>)`

傳回整數。

## 示例

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

傳回10。

`max([10,null,8])`

傳回10。
