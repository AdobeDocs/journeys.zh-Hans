---
product: adobe campaign
solution: Journey Orchestration
title: setHours
description: 了解函数setHours
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 6%

---


# setHours {#setHours}

仅设置日期时间或日期时间的小时数。 例如，如果您希望等到明天某个小时，您可以强制该小时。

## 类别

日期

## 函数语法

`setHours(<parameter>)`

## 参数

| 参数 | 类型 |
|--- |--- |
| 日期时间 | dateTime |
| 不考虑时区 | dateTimeOnly |
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

明天晚上8点回来。
