---
product: adobe campaign
solution: Journey Orchestration
title: toString
description: 了解函数toString
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# toString {#toString}

根据参数值的类型，将参数值转换为字符串值。 有关数据类型的详细信息，请参阅[此页](../expression/data-types.md)。

## 类别

转换

## 函数语法

`toString(<parameter>)`

## 参数

| 参数 | 说明 |
|--- |--- |
| dateTime | 以UTC日期格式转换日期 |
| dateTimeOnly | 以UTC日期格式转换日期 |
| 持续时间 | 以字符串形式转换为相应的毫秒数 |
| 时区 | 转换为时区id字符串表示法(JODA id) |
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
