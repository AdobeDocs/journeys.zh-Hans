---
product: adobe campaign
title: sum
description: 瞭解函式總和
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 04289d72-aade-4725-b1f5-47cf55e3a40b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 13%

---

# sum {#sum}

傳回一組運算式的值總和。 Null值會被忽略。

## 类别

聚合

## 函式語法

`sum(<parameters>)`

## 参数

* listInteger
* listDecimal
* 持續時間
* 整数
* 小數

## 簽章和傳回的型別

`sum(<listDecimal>)`

傳回小數。

`sum(<listInteger>)`

傳回整數。

`sum(<integer>,<integer>)`

傳回整數。

`sum(<decimal>,<decimal>)`

傳回小數。

## 示例

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

傳回21。

`sum([10.5,null,8.1])`

傳回18.6。
