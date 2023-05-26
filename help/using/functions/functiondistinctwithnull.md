---
product: adobe campaign
title: distinctWithNull
description: 了解distinctWithNull函数
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

返回给定列表的不同值或对象。 如果列表至少有一个null条目，则返回的列表中将显示一个null条目。

## 类别

列表

## 函数语法

`distinctWithNull(<parameters>)`

## 参数

| 参数 | 类型 | 描述 |
|-----------|------------------|------------------|
| listToProcess | listString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly或listObject | 要处理的列表。 对于listObject，它必须是字段引用。 |
| keyAttributeName | 字符串 | 此参数是可选的，仅适用于listObject。 如果未提供参数，则在所有属性具有相同的值时，会将对象视为重复。 否则，如果给定的属性具有相同的值，则对象被视为重复。 |

## 签名和返回的类型

`distinctWithNull(<listInteger>)`

返回整数的列表。

`distinctWithNull(<listDecimal>)`

返回小数位数列表。

`distinctWithNull(<listString>)`

返回字符串列表。

`distinctWithNull(<listDateTimeOnly>)`

返回不考虑时区的日期时间列表。

`distinctWithNull(<listDateTime>)`

返回日期时间列表。

`distinctWithNull(<listDateOnly>)`

返回日期列表。

`distinctWithNull(<listBoolean>)`

返回布尔值列表。

`distinctWithNull(<listDuration>)`

返回持续时间列表。

`distinctWithNull(<listObject>)`

`distinctWithNull(<listObject>,<string>)`

返回对象列表。

## 示例

`distinctWithNull([10,2,10,null])`

返回 [10， 2，空]
