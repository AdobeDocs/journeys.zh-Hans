---
title: sum
description: 了解函数和
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
source-git-commit: 654888ee62a7b9b6e3d34fc3963fb83cac719003
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 7%

---


# sum {#sum}

返回一组表达式的值之和。 忽略null值。

## 类别

聚合

## 函数语法

`sum(<parameters>)`

## 参数

* listInteger
* listDecimal
* 持续时间
* 整数
* 小数

## 签名和返回类型

`sum(<listDecimal>)`

返回十进制。

`sum(<listInteger>)`

返回整数。

`sum(<integer>,<integer>)`

返回整数。

`sum(<decimal>,<decimal>)`

返回十进制。

## 示例

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

返回21。

`sum([10.5,null,8.1])`

返回18.6。
