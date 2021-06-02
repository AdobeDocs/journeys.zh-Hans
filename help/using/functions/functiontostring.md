---
product: adobe campaign
title: toString
description: 了解函数toString
feature: 历程
role: Data Engineer
level: Experienced
exl-id: 942e7a44-1cb1-4c99-abd6-e0b045c42c80
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 6%

---

# toString {#toString}

根据参数值的类型，将其转换为字符串值。 有关数据类型的更多信息，请参阅[此页面](../expression/data-types.md)。

## 类别

转换

## 函数语法

`toString(<parameter>)`

## 参数

| 参数 | 说明 |
|--- |--- |
| dateTime | 以UTC日期格式转换日期 |
| dateTimeOnly | 以UTC日期格式转换日期 |
| 持续时间 | 转换为字符串形式的相应毫秒数 |
| 时区 | 转换为时区id字符串表示(JODA id) |
| 整数 | 转换为值的字符串表示形式（1变为“1”） |
| 小数 | 转换为值的字符串表示形式（1.5变为“1.5”） |
| 布尔 | 如果为true，则将布尔值转换为“true”；如果为false，则将布尔值转换为“false” |

## 签名和返回类型

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<timeZone>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

返回字符串。

## 示例

`toString(4)`

返回“4”。
