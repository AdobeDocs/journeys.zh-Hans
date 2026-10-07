---
product: adobe campaign
title: sort
description: 了解函数排序
feature: Journeys
role: Developer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 8%
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

返回`["A","B","C"]`。

`sort([1, 3, 2], false)`

返回`[3, 2, 1]`。

