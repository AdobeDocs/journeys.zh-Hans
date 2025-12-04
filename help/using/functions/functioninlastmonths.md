---
product: adobe campaign
title: inLastMonths
description: 了解inLastMonths函数
feature: Journeys
role: Developer
level: Experienced
exl-id: ff8effa9-404a-482b-8842-a276f029e2ed
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inLastMonths {#inLastMonths}

如果给定的日期或日期时间介于现在和现在之间 — 增量月份，则返回true。

## 类别

日期

## 函数语法

`inLastMonths(<dateTime>,<delta>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 日期时间 | dateTime |
| 增量 | 整数 |

## 签名和返回的类型

`inLastMonths(<dateTime>,<integer>)`

返回布尔值。

## 示例

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4)`

返回真。
