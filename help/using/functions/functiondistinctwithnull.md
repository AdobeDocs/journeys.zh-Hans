---
product: adobe campaign
solution: Journey Orchestration
title: distinctWithNull
description: 了解函数distinctWithNull
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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

返回[10, 2,null]
