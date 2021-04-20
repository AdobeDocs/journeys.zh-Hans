---
product: adobe campaign
solution: Journey Orchestration
title: inLastYears
description: 了解LastYears中的函数
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

---


# inLastYears {#inLastYears}

如果给定日期或dateTime介于现在和现在之间 — 增量年，则返回true。

## 类别

日期

## 函数语法

`inLastYears(<dateTime>,<delta>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 日期时间 | dateTime |
| δ | 整数 |

## 签名和返回类型

`inLastYears(<dateTime>,<integer>)`

返回布尔值。

## 示例

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4))`

返回true。
