---
product: adobe campaign
title: setHours
description: 了解函数setHours
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
source-git-commit: 51536b20e81cde1a7fdd7f4654d70bfe6176b0d4
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 8%

---

# setHours {#setHours}

仅设置日期时间或日期时间的小时数。 例如，如果您想要等到明天某个小时，则可以强制该小时。

## 类别

日期

## 函数语法

`setHours(<parameter>)`

## 参数

| 参数 | 类型 |
|--- |--- |
| 日期时间 | dateTime |
| 不考虑时区的日期时间 | dateTimeOnly |
| 小时 | 整数 |

## 签名和返回类型

`setHours(<dateTime>,<hours>)`

返回日期时间。

`setHours(<dateTimeOnly>,<hours>)`

返回日期时间，而不考虑时区。

## 示例

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4))`

返回2010-12-12T04:11:00Z。

`setHours(nowWithDelta(1, "days"), 20)`

明天8:XY PM返回，XY是当前时间评估时的分钟。 如果评估在凌晨2:45进行，则返回的时间将为晚上8:45。
