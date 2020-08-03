---
title: distinct
description: 了解函数的独特性
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
source-wordcount: '83'
ht-degree: 13%

---


# distinct {#distinct}

返回列表的不同值（不含null值）。

## 类别

列表

## 函数语法

`distinct(<parameter>)`

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

`distinct(<listInteger>)`

返回整数列表。

`distinct(<listDecimal>)`

返回一列表小数。

`distinct(<listString>)`

返回一列表字符串。

`distinct(<listDateTimeOnly>)`

返回日期时间列表，不考虑时区。

`distinct(<listDateTime>)`

返回datetimes的列表。

`distinct(<listBoolean>)`

返回一列表布尔语。

`distinct(<listDuration>)`

返回持续时间列表。

## 示例

`distinct([10,2,10,null])`

退货 `[10, 2]`。
