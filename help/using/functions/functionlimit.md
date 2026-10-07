---
product: adobe campaign
title: limit
description: 了解函数限制
feature: Journeys
role: Developer
level: Experienced
exl-id: 7e006660-1206-4b8a-9e5b-c6fbeee9cc8f
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
source-wordcount: '135'
ht-degree: 8%
---
# limit {#limit}

返回列表的第一个或最后的N个元素。

## 类别

列表

## 函数语法

`limit(<parameters>)`

## 参数

| 参数 | 类型 | 描述 |
|-----------|------------------|------------------|
| listToProcess | listString、listBoolean、listInteger、listDecimal、listDuration、listDateTime、listDateTimeOnly、listDateOnly或listObject | 要排序的列表。 对于listObject，它必须是字段引用。 |
| 项目数 | 整数 | 要从给定列表中返回的项目数。 |
| firstOrLastItems | 布尔 | 此参数是可选的（默认为true）。 true返回第一项。 false返回最后一个项目。 |

## 签名和返回的类型

`limit(<listString>,<integer>)`
`limit(<listString>,<integer>,<boolean>)`

返回字符串列表。

`limit(<listInteger>,<integer>)`
`limit(<listInteger>,<integer>,<boolean>)`

返回整数列表。

`limit(<listDecimal>,<integer>)`
`limit(<listDecimal>,<integer>,<boolean>)`

返回小数位数列表。

`limit(<listBoolean>,<integer>)`
`limit(<listBoolean>,<integer>,<boolean>)`

返回布尔值列表。

`limit(<listDateOnly>,<integer>)`
`limit(<listDateOnly>,<integer>,<boolean>)`

返回日期列表。

`limit(<listDateTimeOnly>,<integer>)`
`limit(<listDateTimeOnly>,<integer>,<boolean>)`

返回不考虑时区的日期时间列表。

`limit(<listDateTime>,integer>)`
`limit(<listDateTime>,<integer>,<boolean>)`

返回日期时间列表。

`limit(<listDuration>,<integer>)`
`limit(<listDuration>,<integer>,<boolean>)`

返回持续时间列表。

`limit(<listObject>,<integer>)`
`limit(<listObject>,<integer>,<boolean>)`

返回对象列表。

## 示例

`limit(["A", "B", "C", "D", "E"], 3)`

返回`["A","B","C"]`。

`limit(["A", "B", "C", "D", "E"], 3, false)`

返回`["C","D","E"]`。
