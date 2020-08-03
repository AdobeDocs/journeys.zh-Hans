---
title: distinctWithNull
description: 了解函数distinctWithNull
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
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 11%

---


# distinctWithNull {#distinctWithNull}

返回列表的不同值。 如果列表至少有一个null值，则返回的列表中将有null值。

## 类别

列表

## 函数语法

`distinctWithNull(<parameter>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 列表 | listString |
| 列表 | listBoolean |
| 列表 | listInteger |
| 列表 | listDecimal |
| 列表 | listDuration |
| 列表 | listDateTime |
| 列表 | listDateTimeOnly |

## 签名和返回类型

`distinctWithNull(<listInteger>)`

返回整数列表。

`distinctWithNull(<listDecimal>)`

返回一列表小数。

`distinctWithNull(<listString>)`

返回一列表字符串。

`distinctWithNull(<listDateTimeOnly>)`

返回日期时间列表，不考虑时区。

`distinctWithNull(<listDateTime>)`

返回datetimes的列表。

`distinctWithNull(<listBoolean>)`

返回一列表布尔语。

`distinctWithNull(<listDuration>)`

返回持续时间列表。

## 示例

`distinctWithNull([10,2,10,null])`

返 [回10、2、null]
