---
product: adobe campaign
title: distinct
description: 了解distinct函数
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 034e4d77-2f0e-4117-9fd4-b9e35ef71a39
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 6%

---

# distinct {#distinct}

返回给定列表的不同值或对象。 Null条目将被忽略。

## 类别

列表

## 函数语法

`distinct(<parameters>)`

## 参数

| 参数 | 类型 | 描述 |
|-----------|------------------|------------------|
| listToProcess | listString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly或listObject | 要处理的列表。 对于listObject，它必须是字段引用。 |
| keyAttributeName | 字符串 | 此参数是可选的，并且仅适用于listObject。 如果未提供参数，则当所有属性都具有相同的值时，会将对象视为重复。 否则，如果给定的属性具有相同的值，则将对象视为重复。 |

## 签名和返回的类型

`distinct(<listInteger>)`

返回整数列表。

`distinct(<listDecimal>)`

返回小数位数列表。

`distinct(<listString>)`

返回字符串列表。

`distinct(<listDateTimeOnly>)`

返回不考虑时区的日期时间列表。

`distinct(<listDateTime>)`

返回日期时间列表。

`distinct(<listDateOnly>)`

返回日期列表。

`distinct(<listBoolean>)`

返回布尔值列表。

`distinct(<listDuration>)`

返回持续时间列表。

`distinct(<listObject>)`

`distinct(<listObject>,<string>)`

返回对象列表。


## 示例

`distinct([10,2,10,null])`

返回`[10, 2]`。
