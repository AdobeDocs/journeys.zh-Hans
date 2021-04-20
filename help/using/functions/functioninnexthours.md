---
product: adobe campaign
solution: Journey Orchestration
title: inNextHours
description: 了解NextHours中的函数
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

---


# inNextHours {#inNextHours}

如果给定日期或dateTime介于现在和现在+增量小时之间，则返回true。

## 类别

日期

## 函数语法

`inNextHours(<dateTime>,<delta>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 日期时间 | dateTime |
| δ | 整数 |

## 签名和返回类型

`inNextHours(<dateTime>,<integer>)`

返回布尔值。

## 示例

`inNextHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

返回true。
