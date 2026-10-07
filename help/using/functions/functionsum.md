---
product: adobe campaign
title: sum
description: 了解函数总和
feature: Journeys
role: Developer
level: Experienced
exl-id: 04289d72-aade-4725-b1f5-47cf55e3a40b
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 13%
---
# sum {#sum}

返回一组表达式的值的总和。 Null值将被忽略。

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
