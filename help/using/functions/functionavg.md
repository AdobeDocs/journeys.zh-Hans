---
product: adobe campaign
title: avg
description: 了解函数avg
feature: 历程
role: Data Engineer
level: Experienced
exl-id: 6c9f3a5d-20b4-4c0a-b17f-5221f5db51be
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 12%

---

# avg {#avg}

返回一组表达式中的平均值（以列表或两个表达式的形式提供）。 将忽略空值。


## 类别

聚合

## 函数语法

`avg(<parameter>)`

## 参数

支持的类型：

* listInteger
* listDecimal
* 小数
* 整数

## 签名和返回类型

`avg(<listInteger>)`

`avg(<listInteger>)`

`avg(<listDecimal>)`

`avg(<decimal>,<decimal>)`

`avg(<decimal>,<integer>)`

`avg(<integer>,<decimal>)`

`avg(<integer>,<integer>)`

返回小数。

## 示例

`avg(@{BarBeacon.inventory},5)`

`avg([10,3,8])`

返回7.0。

`avg(10.2, 3)`

返回6.6。
