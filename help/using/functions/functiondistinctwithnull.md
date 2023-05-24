---
product: adobe campaign
title: distinctWithNull
description: 瞭解函式distinctWithNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 65a904c1-14ff-42b3-8f03-abb97ef47625
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 5%

---

# distinctWithNull {#distinctWithNull}

傳回給定清單的不同值或物件。 如果清單中至少有一個null專案，則傳回的清單中將會出現null專案。

## 类别

列表

## 函式語法

`distinctWithNull(<parameters>)`

## 参数

| 参数 | 类型 | 描述 |
|-----------|------------------|------------------|
| listToProcess | listString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly或listObject | 要處理的清單。 對於listObject，它必須是欄位參考。 |
| keyAttributeName | 字符串 | 此引數是選用引數，僅適用於listObject。 如果未提供引數，如果所有屬性的值都相同，則會將物件視為重複。 否則，如果給定的屬性具有相同的值，則會將物件視為重複。 |

## 簽章和傳回的型別

`distinctWithNull(<listInteger>)`

傳回整數清單。

`distinctWithNull(<listDecimal>)`

傳回小數點清單。

`distinctWithNull(<listString>)`

傳回字串清單。

`distinctWithNull(<listDateTimeOnly>)`

傳回日期時間清單，不考慮時區。

`distinctWithNull(<listDateTime>)`

傳回日期時間清單。

`distinctWithNull(<listDateOnly>)`

傳回日期清單。

`distinctWithNull(<listBoolean>)`

傳回布林值清單。

`distinctWithNull(<listDuration>)`

傳回持續時間清單。

`distinctWithNull(<listObject>)`

`distinctWithNull(<listObject>,<string>)`

傳回物件清單。

## 示例

`distinctWithNull([10,2,10,null])`

傳回 [10， 2， null]
