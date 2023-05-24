---
product: adobe campaign
title: inNextDays
description: 瞭解函式inNextDays
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 47d31b56-b0ed-426d-bd79-3db3e441454b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inNextDays {#inNextDays}

如果指定的日期或日期時間介於現在和現在+差異天數之間，則傳回true。

## 类别

日期

## 函式語法

`inNextDays(<dateTime>,<delta>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 日期時間 | dateTime |
| delta | 整数 |

## 簽章和傳回型別

`inNextDays(<dateTime>,<integer>)`

傳回布林值。

## 示例

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

傳回true。
