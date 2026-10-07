---
product: adobe campaign
title: setDays
description: 了解函数setDays
feature: Journeys
role: Developer
level: Experienced
exl-id: eee7bf61-9101-4959-aa93-27d0f221c517
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
source-wordcount: '75'
ht-degree: 13%
---
# setDays {#setDays}

仅设置日期时间或日期时间的日期。 例如，如果您要等到月份的某一天，则可以强制该天。

## 类别

日期

## 函数语法

`setDays(<parameter>)`

## 参数

| 参数 | 类型 |
|--- |--- |
| 日期时间 | dateTime |
| 不考虑时区的日期时间 | dateTimeOnly |
| 天数 | 整数 |

## 签名和返回的类型

`setDays(<dateTime>,<days>)`

返回日期时间。

`setDays(<dateTimeOnly>,<days>)`

返回不考虑时区的日期时间。

## 示例

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

返回2010-12-25T01:11:00Z。

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
