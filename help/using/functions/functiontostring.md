---
product: adobe campaign
title: toString
description: 瞭解函式toString
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 942e7a44-1cb1-4c99-abd6-e0b045c42c80
source-git-commit: c7730ecac062719e5e5adfd465d1cedb59b3eaf1
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 9%

---

# toString {#toString}

根據其型別，將引數值轉換為字串值。 如需資料型別的詳細資訊，請參閱 [此頁面](../expression/data-types.md).

## 类别

转化

## 函式語法

`toString(<parameter>)`

## 参数

| 参数 | 描述 |
|--- |--- |
| dateTime | 將日期轉換為UTC日期格式 |
| dateTimeOnly | 將日期轉換為UTC日期格式 |
| 持續時間 | 轉換為字串形式的對應毫秒數 |
| 整数 | 轉換為值的字串表示法（1會變成「1」） |
| 小數 | 轉換為值的字串表示法（1.5變成&quot;1.5&quot;） |
| 布尔 | 將布林值轉換為&#39;true&#39; （如果為true）、&#39;false&#39; （如果為false） |

## 簽章和傳回型別

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

傳回字串。

## 示例

`toString(4)`

傳回「4」。
