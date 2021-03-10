---
product: adobe campaign
solution: Journey Orchestration
title: inLastHours
description: 了解LastHours中的函数
feature: 历程
role: 数据工程师
level: 富有经验
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 10%

---


# inLastHours {#inLastHours}

如果给定日期时间介于现在和现在之间 — 增量小时，则返回true。

## 类别

日期

## 函数语法

`inLastHours(<dateTime>,<delta>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 日期时间 | dateTime |
| δ | 整数 |

## 签名和返回类型

`inLastHours(<dateTime>,<integer>)`

返回布尔值。

## 示例

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4))`

返回true。

`inLastHours(@{MyEvent.timestamp}, 4)`

返回true。
