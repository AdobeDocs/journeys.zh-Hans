---
product: adobe campaign
solution: Journey Orchestration
title: setDays
description: 了解函数setDays
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '74'
ht-degree: 5%

---


# setDays {#setDays}

仅设置日期时间或日期时间的日期。 例如，如果要等到某月的某一天，可以强制该天。

## 类别

日期

## 函数语法

`setDays(<parameter>)`

## 参数

| 参数 | 类型 |
|--- |--- |
| 日期时间 | dateTime |
| 不考虑时区的日期时间 | dateTimeOnly |
| 天 | 整数 |

## 签名和返回类型

`setDays(<dateTime>,<days>)`

返回日期时间。

`setDays(<dateTimeOnly>,<days>)`

返回日期时间，不考虑时区。

## 示例

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

返回2010-12-25T01:11:00Z。

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
