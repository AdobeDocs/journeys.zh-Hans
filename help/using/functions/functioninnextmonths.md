---
product: adobe campaign
title: inNextMonths
description: 瞭解函式inNextMonths
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b5e8d514-a24d-42a2-b422-ec5d6617048a
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inNextMonths {#inNextMonths}

如果指定的日期或日期時間介於現在和現在+差異月份之間，則傳回true。

## 类别

日期

## 函式語法

`inNextMonths(<dateTime>,<delta>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 日期時間 | dateTime |
| delta | 整数 |

## 簽章和傳回型別

`inNextMonths(<dateTime>,<integer>)`

傳回布林值。

## 示例

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4)`

傳回true。
