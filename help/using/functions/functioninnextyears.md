---
product: adobe campaign
title: inNextYears
description: 了解NextYears中的功能
feature: 历程
role: Data Engineer
level: Experienced
exl-id: 8aab6f60-feba-4be2-9a32-ba4ed7f3d7de
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%

---

# inNextYears {#inNextYears}

如果给定的日期或dateTime介于现在和现在+增量年之间，则返回true。

## 类别

日期

## 函数语法

`inNextYears(<dateTime>,<delta>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 日期时间 | dateTime |
| 三角洲 | 整数 |

## 签名和返回类型

`inNextYears(<dateTime>,<integer>)`

返回布尔值。

## 示例

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4))`

返回true。
