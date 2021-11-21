---
product: adobe campaign
title: inNextDays
description: 了解NextDays中的函数
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 47d31b56-b0ed-426d-bd79-3db3e441454b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 18%

---

# inNextDays {#inNextDays}

如果给定的日期或dateTime介于现在和现在+增量天之间，则返回true。

## 类别

日期

## 函数语法

`inNextDays(<dateTime>,<delta>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 日期时间 | dateTime |
| 三角洲 | 整数 |

## 签名和返回类型

`inNextDays(<dateTime>,<integer>)`

返回布尔值。

## 示例

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

返回true。
