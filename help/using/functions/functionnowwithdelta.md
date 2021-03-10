---
product: adobe campaign
solution: Journey Orchestration
title: nowWithDelta
description: 了解函数nowWithDelta
feature: 历程
role: 数据工程师
level: 富有经验
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 5%

---


# nowWithDelta {#nowWithDelta}

返回包含偏移的当前日期时间。 如果指定了时区ID，则将应用时区偏移。 有关数据类型的详细信息，请参阅[此页](../expression/data-types.md)。

## 类别

日期

## 函数语法

`nowWithDelta(<parameters>)`

## 参数

| 参数 | 说明 |
|--- |--- |
| δ | 正整数 |
| 日期 | 年、月、日、小时、分或秒，作为字符串 |
| 时区id | 时区值的字符串表示形式。 有关详细信息，请参阅[数据类型](../expression/data-types.md)。 时区ID必须是字符串常数。 它不能是字段引用或表达式。 |

## 签名和返回类型

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

返回dateTime。

## 示例

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

返回一个2小时前的dateTime。
