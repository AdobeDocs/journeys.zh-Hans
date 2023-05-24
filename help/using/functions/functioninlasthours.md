---
product: adobe campaign
title: inLastHours
description: 瞭解函式inLastHours
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 9baeb836-e029-4e19-b08e-7b7b5f27ff8f
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%

---

# inLastHours {#inLastHours}

如果指定的日期時間介於現在和現在之間 — 差異小時，則傳回true。

## 类别

日期

## 函式語法

`inLastHours(<dateTime>,<delta>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 日期時間 | dateTime |
| delta | 整数 |

## 簽章和傳回型別

`inLastHours(<dateTime>,<integer>)`

傳回布林值。

## 示例

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4)`

傳回true。

`inLastHours(@{MyEvent.timestamp}, 4)`

傳回true。
