---
product: adobe campaign
title: distinctWithNull
description: 了解distinctWithNull函数
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 65a904c1-14ff-42b3-8f03-abb97ef47625
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 15%

---

# distinctWithNull {#distinctWithNull}

返回列表的不同值。 如果列表至少具有一个空值，则返回的列表中将有一个空值。

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
| 列表 | listDateOnly |

## 签名和返回的类型

`distinctWithNull(<listInteger>)`

返回整数列表。

`distinctWithNull(<listDecimal>)`

返回小数列表。

`distinctWithNull(<listString>)`

返回字符串列表。

`distinctWithNull(<listDateTimeOnly>)`

返回不考虑时区的日期时间列表。

`distinctWithNull(<listDateTime>)`

返回datetimes列表。

`distinctWithNull(<listDateOnly>)`

返回日期列表。

`distinctWithNull(<listBoolean>)`

返回布尔值列表。

`distinctWithNull(<listDuration>)`

返回持续时间列表。

## 示例

`distinctWithNull([10,2,10,null])`

返回结果 [10, 2，空]
