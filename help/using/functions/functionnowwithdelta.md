---
product: adobe campaign
solution: Journey Orchestration
title: nowWithDelta
description: 立即了解函数WithDelta
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 4%

---


# nowWithDelta {#nowWithDelta}

返回包含偏移的当前日期时间。 如果指定了时区ID，则将应用时区偏移。 For more information on data types, refer to [this page](../expression/data-types.md).

## 类别

日期

## 函数语法

`nowWithDelta(<parameters>)`

## 参数

| 参数 | 说明 |
|--- |--- |
| 三角洲 | 正整数值 |
| 日期部分 | 年、月、日、小时、分钟或秒（字符串） |
| 时区id | 时区值的字符串表示形式。 有关详细信息，请参 [阅数据类型](../expression/data-types.md)。 时区ID必须是字符串常数。 它不能是字段引用或表达式。 |

## 签名和返回类型

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

返回dateTime。

## 示例

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

返回一个dateTime，恰好在2小时前。
