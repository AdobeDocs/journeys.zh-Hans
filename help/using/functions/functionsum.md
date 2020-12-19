---
product: adobe campaign
solution: Journey Orchestration
title: sum
description: 了解函数和
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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
