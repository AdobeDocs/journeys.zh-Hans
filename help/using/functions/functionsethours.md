---
product: adobe campaign
title: setHours
description: 瞭解函式setHours
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 9%

---

# setHours {#setHours}

僅設定日期時間或日期時間的小時。 例如，如果您要等到明天的某個小時，您可以強制該小時。

## 类别

日期

## 函式語法

`setHours(<parameter>)`

## 参数

| 参数 | 类型 |
|--- |--- |
| 日期時間 | dateTime |
| 不考慮時區的日期時間 | dateTimeOnly |
| 小时 | 整数 |

## 簽章和傳回型別

`setHours(<dateTime>,<hours>)`

傳回日期時間。

`setHours(<dateTimeOnly>,<hours>)`

傳回不考慮時區的日期時間。

## 示例

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

傳回2010-12-12T04:11:00Z。

`setHours(nowWithDelta(1, "days"), 20)`

明天晚上8：XY，XY會傳回目前時間評估的分鐘數。 如果評估在凌晨2:45進行，則傳回的時間將會是晚上8:45。
