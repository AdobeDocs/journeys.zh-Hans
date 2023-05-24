---
product: adobe campaign
title: toDateOnly
description: 瞭解函式toDateOnly
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2d7b132e-5ee0-4fa0-bacc-ce4c6ec7e794
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 21%

---

# toDateOnly{#toDateOnly}

將引數值轉換為僅日期值。

## 类别

转化

## 函式語法

`toDateOnly(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| ISO-8601或&quot;YYYY-MM-DD&quot;格式的日期（XDM日期格式） | 字符串 |
| 日期 | 日期 |

## 簽章和傳回的型別

`toDateOnly(<date>)`

`toDateOnly(<string>)`

傳回日期時間而不考慮時區。

## 示例

`toDateOnly("2016-08-18")`

傳回代表2016-08-18的dateOnly物件。
