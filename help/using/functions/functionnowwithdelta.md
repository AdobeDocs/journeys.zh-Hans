---
product: adobe campaign
title: nowWithDelta
description: Learn about the function nowWithDelta
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

Returns the current datetime including an offset. If a time zone id is specified, the time zone offset will be applied. For more information on data types, refer to [this page](../expression/data-types.md).

## 类别

日期

## 函数语法

`nowWithDelta(<parameters>)`

## 参数

| 参数 | 描述 |
|--- |--- |
| 三角洲 | 正整数或负整数值 |
| 日期部分 | 年、月、日、小时、分钟或秒（字符串） |
| 时区id | 时区值的字符串表示形式。 For more, see [Data types](../expression/data-types.md). 时区ID必须是字符串常量。 It cannot be a field reference nor an expression. |

## Signatures and returned type

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

Returns a dateTime.

## 示例

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

Returns a dateTime exactly 2 hours ago.
