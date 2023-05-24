---
product: adobe campaign
title: distinct
description: 瞭解不同的函式
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 034e4d77-2f0e-4117-9fd4-b9e35ef71a39
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 7%

---

# distinct {#distinct}

傳回給定清單的不同值或物件。 會忽略Null專案。

## 类别

列表

## 函式語法

`distinct(<parameters>)`

## 参数

| 参数 | 类型 | 描述 |
|-----------|------------------|------------------|
| listToProcess | listString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly或listObject | 要處理的清單。 對於listObject，它必須是欄位參考。 |
| keyAttributeName | 字符串 | 此引數是選用引數，僅適用於listObject。 如果未提供引數，如果所有屬性的值都相同，則會將物件視為重複。 否則，如果給定的屬性具有相同的值，則會將物件視為重複。 |

## 簽章和傳回的型別

`distinct(<listInteger>)`

傳回整數清單。

`distinct(<listDecimal>)`

傳回小數點清單。

`distinct(<listString>)`

傳回字串清單。

`distinct(<listDateTimeOnly>)`

傳回日期時間清單，不考慮時區。

`distinct(<listDateTime>)`

傳回日期時間清單。

`distinct(<listDateOnly>)`

傳回日期清單。

`distinct(<listBoolean>)`

傳回布林值清單。

`distinct(<listDuration>)`

傳回持續時間清單。

`distinct(<listObject>)`

`distinct(<listObject>,<string>)`

傳回物件清單。


## 示例

`distinct([10,2,10,null])`

返回结果 `[10, 2]`.
