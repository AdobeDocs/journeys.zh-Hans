---
product: adobe campaign
title: toInteger
description: 瞭解函式toInteger
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3fcbf4dd-3ca5-4f4b-b774-af6ac3170768
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 14%

---

# toInteger {#toInteger}

將引數值轉換為整數。

## 类别

转化

## 函式語法

`toInteger(<parameter>)`

## 参数

| 参数 | 描述 |
|--- |--- |
| 字符串 | 將字串值轉換為整數 |
| dateTime | 將日期轉換為毫秒數（紀元毫秒） |
| 小數 | 透過移除小數部分轉換為整數（範例： 1.5變為1） |
| 布尔 | 將布林值轉換為1 （如果為true）、0 （如果為false） |

## 簽章和傳回型別

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

傳回整數。

## 示例

`toInteger("4")`

傳回4。
