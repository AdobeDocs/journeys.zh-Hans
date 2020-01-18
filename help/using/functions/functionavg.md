---
title: 平均
description: 了解函数平均值
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

---


# 平均 {#avg}

返回一组表达式中的平均值，以列表或两个表达式的形式给出。 忽略空值。


## 类别

聚合

## 函数语法

`avg(<parameter>)`

## 参数

支持的类型：

* listInteger
* listDecimal
* 小数点
* 整数

## 签名和返回类型

`avg(<listInteger>)`

`avg(<listInteger>)`

`avg(<listDecimal>)`

`avg(<decimal>,<decimal>)`

`avg(<decimal>,<integer>)`

`avg(<integer>,<decimal>)`

`avg(<integer>,<integer>)`

返回小数点。

## 示例

`avg(@{BarBeacon.inventory},5)`

`avg([10,3,8])`

返回7.0。

`avg(10.2, 3)`

返回6.6。
