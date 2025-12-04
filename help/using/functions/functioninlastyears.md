---
product: adobe campaign
title: inLastYears
description: 了解函数inLastYears
feature: Journeys
role: Developer
level: Experienced
exl-id: 95ca3d7d-2340-4378-9af4-aa1188bed614
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inLastYears {#inLastYears}

如果给定的日期或日期时间介于现在和现在之间 — 增量年，则返回true。

## 类别

日期

## 函数语法

`inLastYears(<dateTime>,<delta>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 日期时间 | dateTime |
| 增量 | 整数 |

## 签名和返回的类型

`inLastYears(<dateTime>,<integer>)`

返回布尔值。

## 示例

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4)`

返回真。
