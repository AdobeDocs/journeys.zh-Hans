---
product: adobe campaign
title: inNextHours
description: 瞭解inNextHours函式
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 4bcbfdbc-fc95-4089-8abc-f9314dde2c06
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inNextHours {#inNextHours}

如果指定的日期或日期時間介於現在和現在+差異小時之間，則傳回true。

## 类别

日期

## 函式語法

`inNextHours(<dateTime>,<delta>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 日期時間 | dateTime |
| delta | 整数 |

## 簽章和傳回型別

`inNextHours(<dateTime>,<integer>)`

傳回布林值。

## 示例

`inNextHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

傳回true。
