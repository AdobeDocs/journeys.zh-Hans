---
product: adobe campaign
title: inLastDays
description: 了解函数inLastDays
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 1fc29153-3554-4af1-bb2e-7bba53ffce69
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inLastDays {#inLastDays}

如果给定的日期或日期时间介于现在和现在之间 — 增量天，则返回true。

## 类别

日期

## 函数语法

`inLastDays(<dateTime>,<delta>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 日期时间 | dateTime |
| 增量 | 整数 |

## 签名和返回的类型

`inLastDays(<dateTime>,<integer>)`

返回布尔值。

## 示例

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4)`

返回真。
