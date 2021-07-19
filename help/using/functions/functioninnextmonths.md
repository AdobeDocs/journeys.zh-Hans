---
product: adobe campaign
title: inNextMonths
description: 了解NextMonths中的函数
feature: 历程
role: Data Engineer
level: Experienced
exl-id: b5e8d514-a24d-42a2-b422-ec5d6617048a
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%

---

# inNextMonths {#inNextMonths}

如果给定的日期或dateTime介于现在和现在+增量月之间，则返回true。

## 类别

日期

## 函数语法

`inNextMonths(<dateTime>,<delta>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 日期时间 | dateTime |
| 三角洲 | 整数 |

## 签名和返回类型

`inNextMonths(<dateTime>,<integer>)`

返回布尔值。

## 示例

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4))`

返回true。
