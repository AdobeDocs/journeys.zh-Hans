---
product: adobe campaign
title: sort
description: 瞭解函式排序
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 9%

---

# sort {#sort}

以自然順序排序值清單或物件。

## 类别

列表

## 函式語法

`sort(<parameters>)`

## 参数

| 参数 | 类型 | 描述 |
|-----------|------------------|------------------|
| listToSort | listString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly或listObject | 要排序的清單。 對於listObject，它必須是欄位參考。 |
| keyAttributeName | 字符串 | 此引數僅適用於listObject。 給定清單的物件中的屬性名稱會用作排序的索引鍵。 |
| sortingOrder | 布尔 | 遞增(true)或遞減(false) |

## 簽章和傳回的型別

`sort(<listInteger>,<boolean>)`

傳回整數清單。

`sort(<listDecimal>,<boolean>)`

傳回小數點清單。

`sort(<listString>,<boolean>)`

傳回字串清單。

`sort(<listDateTimeOnly>,<boolean>)`

傳回日期時間清單，不考慮時區。

`sort(<listDateTime>,<boolean>)`

傳回日期時間清單。

`sort(<listDateOnly>,<boolean>)`

傳回日期清單。

`sort(<listBoolean>,<boolean>)`

傳回布林值清單。

`sort(<listObject>,<string>,<boolean>)`

傳回物件清單。

## 示例

`sort(["A", "C", "B"], true)`

返回结果 `["A","B","C"]`.

`sort([1, 3, 2], false)`

返回结果 `[3, 2, 1]`.

