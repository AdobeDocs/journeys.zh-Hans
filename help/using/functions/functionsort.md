---
product: adobe campaign
title: sort
description: 了解函数排序
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

以自然顺序对值列表或对象进行排序。

## 类别

列表

## 函数语法

`sort(<parameters>)`

## 参数

| 参数 | 类型 | 描述 |
|-----------|------------------|------------------|
| listToSort | listString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly或listObject | 要排序的列表。 对于listObject，它必须是字段引用。 |
| keyAttributeName | 字符串 | 此参数仅适用于listObject。 给定列表中的对象中的属性名称用作排序的键。 |
| sortingOrder | 布尔 | 升序(true)或降序(false) |

## 签名和返回的类型

`sort(<listInteger>,<boolean>)`

返回整数列表。

`sort(<listDecimal>,<boolean>)`

返回小数位数列表。

`sort(<listString>,<boolean>)`

返回字符串列表。

`sort(<listDateTimeOnly>,<boolean>)`

返回不考虑时区的日期时间列表。

`sort(<listDateTime>,<boolean>)`

返回日期时间列表。

`sort(<listDateOnly>,<boolean>)`

返回日期列表。

`sort(<listBoolean>,<boolean>)`

返回布尔值列表。

`sort(<listObject>,<string>,<boolean>)`

返回对象列表。

## 示例

`sort(["A", "C", "B"], true)`

返回结果 `["A","B","C"]`.

`sort([1, 3, 2], false)`

返回结果 `[3, 2, 1]`.

