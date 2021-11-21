---
product: adobe campaign
title: nowWithDelta
description: 了解函数nowWithDelta
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: f23f729b-7edb-4efc-a7ea-904314a7b2e1
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 7%

---

# nowWithDelta {#nowWithDelta}

返回包含偏移的当前日期时间。 如果指定了时区ID，则将应用时区偏移。 有关数据类型的更多信息，请参阅 [本页](../expression/data-types.md).

## 类别

日期

## 函数语法

`nowWithDelta(<parameters>)`

## 参数

| 参数 | 描述 |
|--- |--- |
| 三角洲 | 正整数或负整数值 |
| 日期部分 | 年、月、日、小时、分钟或秒（字符串） |
| 时区id | 时区值的字符串表示形式。 有关更多信息，请参阅 [数据类型](../expression/data-types.md). 时区ID必须是字符串常量。 它不能是字段引用或表达式。 |

## 签名和返回类型

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

返回dateTime。

## 示例

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

返回恰好2小时前的dateTime。
