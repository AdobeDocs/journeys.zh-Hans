---
product: adobe campaign
title: inNextYears
description: 瞭解函式inNextYears
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8aab6f60-feba-4be2-9a32-ba4ed7f3d7de
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 20%

---

# inNextYears {#inNextYears}

如果指定的日期或dateTime介於現在和現在+差異年度之間，則傳回true。

## 类别

日期

## 函式語法

`inNextYears(<dateTime>,<delta>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 日期時間 | dateTime |
| delta | 整数 |

## 簽章和傳回型別

`inNextYears(<dateTime>,<integer>)`

傳回布林值。

## 示例

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4)`

傳回true。
