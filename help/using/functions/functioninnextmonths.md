---
product: adobe campaign
solution: Journey Orchestration
title: inNextMonths
description: 了解NextMonths中的函数
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%

---


# inNextMonths {#inNextMonths}

如果给定日期或dateTime介于现在和现在+增量月之间，则返回true。

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
