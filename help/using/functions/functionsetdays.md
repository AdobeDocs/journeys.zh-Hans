---
title: setDays
description: 了解函数setDays
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c
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
