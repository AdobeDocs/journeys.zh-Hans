---
product: adobe campaign
title: inLastHours
description: 了解inLastHours函数
feature: Journeys
role: Developer
level: Experienced
exl-id: 9baeb836-e029-4e19-b08e-7b7b5f27ff8f
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%
---
# inLastHours {#inLastHours}

如果给定的日期时间介于现在和现在之间 — 增量小时，则返回true。

## 类别

日期

## 函数语法

`inLastHours(<dateTime>,<delta>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 日期时间 | dateTime |
| 增量 | 整数 |

## 签名和返回的类型

`inLastHours(<dateTime>,<integer>)`

返回布尔值。

## 示例

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4)`

返回真。

`inLastHours(@{MyEvent.timestamp}, 4)`

返回真。
