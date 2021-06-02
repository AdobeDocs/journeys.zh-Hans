---
product: adobe campaign
title: toDuration
description: 了解函数toDuration
feature: 历程
role: Data Engineer
level: Experienced
exl-id: 77f068fa-678e-49a4-b45f-843c3287390a
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 2%

---

# toDuration {#toDuration}

将参数值转换为持续时间。 有关数据类型的更多信息，请参阅[此页面](../expression/data-types.md)。

## 类别

转换

## 函数语法

`toDuration(<parameter>)`

## 参数

| 参数 | 说明 |
|--- |--- |
| 字符串 | 基于ISO-8601持续时间格式的格式PnDTnHnMn.nS，天数被认为恰好为24小时 |
| 整数 | 毫秒数 |

如果字符串表达式：接受的格式基于ISO-8601持续时间格式PnDTnHnMn.nS，天数被认为恰好为24小时。

字符串以可选符号开头，由ASCII负号或正号表示。 如果为负，则整个周期都会被否定。 ASCII字母“P”在大写或小写中位于下一位。 然后有四个部分，每个部分都包含一个数字和后缀。 这些部分的ASCII后缀为“D”、“H”、“M”和“S”（天、小时、分钟和秒），在大小写中接受。 后缀必须按顺序发生。 ASCII字母“T”必须在小时、分钟或秒部分的第一个实例（如果有）之前出现。 这四个部分中至少有一个必须存在，并且如果存在“T”，则“T”后面必须至少有一个部分。 每个部分的数字部分必须由一个或多个ASCII数字组成。 数字可以用ASCII负号或正号作为前缀。 必须解析到的天数、小时数和分钟数。 必须解析到的秒数以及可选部分。 小数点可以是点或逗号。 小数部分可以具有0到9位。

## 签名和返回类型

`toDuration(<string>)`

`toDuration(<integer>)`

返回持续时间。

## 示例

`toDuration("PT10H")`

返回10小时的持续时间。

`toDuration("PT4S")`

返回持续时间4s。

`toDuration(4000)`

返回持续时间4s。
