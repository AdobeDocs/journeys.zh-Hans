---
product: adobe campaign
title: inLastYears
description: 了解LastYears中的函数
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 95ca3d7d-2340-4378-9af4-aa1188bed614
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 18%

---

# inLastYears {#inLastYears}

Returns true if a given date or dateTime is between now and now - delta years.

## 类别

日期

## Function syntax

`inLastYears(<dateTime>,<delta>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| date time | dateTime |
| delta | integer |

## 签名和返回类型

`inLastYears(<dateTime>,<integer>)`

Returns a boolean.

## 示例

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4)`

返回true。
