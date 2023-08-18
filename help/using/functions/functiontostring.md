---
product: adobe campaign
title: toString
description: 了解函数toString
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 942e7a44-1cb1-4c99-abd6-e0b045c42c80
source-git-commit: c7730ecac062719e5e5adfd465d1cedb59b3eaf1
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 9%

---

# toString {#toString}

根据类型将参数值转换为字符串值。 有关数据类型的详细信息，请参阅 [此页面](../expression/data-types.md).

## 类别

转化

## 函数语法

`toString(<parameter>)`

## 参数

| 参数 | 描述 |
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
