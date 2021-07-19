---
product: adobe campaign
title: sum
description: 了解函数和
feature: 历程
role: Data Engineer
level: Experienced
exl-id: 04289d72-aade-4725-b1f5-47cf55e3a40b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 13%

---

# sum {#sum}

返回一组表达式值的和。 将忽略空值。

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

## 签名和返回的类型

`sum(<listDecimal>)`

返回小数。

`sum(<listInteger>)`

返回整数。

`sum(<integer>,<integer>)`

返回整数。

`sum(<decimal>,<decimal>)`

返回小数。

## 示例

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

返回21。

`sum([10.5,null,8.1])`

返回18.6。
