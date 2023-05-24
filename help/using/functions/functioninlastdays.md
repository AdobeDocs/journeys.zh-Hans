---
product: adobe campaign
title: inLastDays
description: 瞭解函式inLastDays
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

如果指定的日期或日期時間介於現在和現在 — 差異天數之間，則傳回true。

## 类别

日期

## 函式語法

`inLastDays(<dateTime>,<delta>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 日期時間 | dateTime |
| delta | 整数 |

## 簽章和傳回型別

`inLastDays(<dateTime>,<integer>)`

傳回布林值。

## 示例

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4)`

傳回true。
