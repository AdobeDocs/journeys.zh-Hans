---
product: adobe campaign
title: inLastYears
description: 了解inLastYears函数
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 95ca3d7d-2340-4378-9af4-aa1188bed614
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inLastYears {#inLastYears}

如果给定的日期或日期时间介于现在和现在之间 — 增量年份，则返回true。

## 类别

日期

## 函数语法

`inLastYears(<dateTime>,<delta>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 日期时间 | dateTime |
| delta | 整数 |

## 签名和返回类型

`inLastYears(<dateTime>,<integer>)`

返回布尔值。

## 示例

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4)`

返回真。
