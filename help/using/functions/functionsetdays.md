---
product: adobe campaign
title: setDays
description: 了解函数setDays
feature: 历程
role: Data Engineer
level: Experienced
exl-id: eee7bf61-9101-4959-aa93-27d0f221c517
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 8%

---

# setDays {#setDays}

仅设置日期时间或日期时间的日期。 例如，如果要等到当月的某一天，则可以强制该天。

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

## 签名和返回类型

`setDays(<dateTime>,<days>)`

返回日期时间。

`setDays(<dateTimeOnly>,<days>)`

返回日期时间，而不考虑时区。

## 示例

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

返回2010-12-25T01:11:00Z。

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
