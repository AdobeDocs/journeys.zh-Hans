---
product: adobe campaign
title: toString
description: 了解函数toString
feature: Journeys
role: Developer
level: Experienced
exl-id: 942e7a44-1cb1-4c99-abd6-e0b045c42c80
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
source-wordcount: '107'
ht-degree: 9%
---
# toString {#toString}

根据类型将参数值转换为字符串值。 有关数据类型的详细信息，请参阅[此页面](../expression/data-types.md)。

## 类别

转化

## 函数语法

`toString(<parameter>)`

## 参数

| 参数 | 说明 |
|--- |--- |
| dateTime | 将日期转换为UTC日期格式 |
| dateTimeOnly | 将日期转换为UTC日期格式 |
| 持续时间 | 转换为字符串形式的相应毫秒数 |
| 整数 | 转换为值的字符串表示形式（1变为“1”） |
| 小数 | 转换为值的字符串表示形式（1.5变为“1.5”） |
| 布尔 | 将布尔值转换为“true”（如果为true），“false”（如果为false） |

## 签名和返回的类型

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

返回字符串。

## 示例

`toString(4)`

返回“4”。
