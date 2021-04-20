---
product: adobe campaign
solution: Journey Orchestration
title: toDuration
description: 了解toDuration函数
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 2%

---


# toDuration {#toDuration}

将参数值转换为持续时间。 有关数据类型的详细信息，请参阅[此页](../expression/data-types.md)。

## 类别

转换

## 函数语法

`toDuration(<parameter>)`

## 参数

| 参数 | 说明 |
|--- |--- |
| 字符串 | 基于ISO-8601持续时间格式的格式PnDTnHnMn.nS，天数被认为正好24小时 |
| 整数 | 毫秒数 |

如果字符串表达式:接受的格式基于ISO-8601持续时间格式PnDTnHnMn.nS，其天数被认为正好24小时。

带有可选符号的字符串开始，由ASCII负或正符号表示。 如果为负，则整个周期被否定。 ASCII字母“P”是大小写或小写的下一个。 然后有四个部分，每个部分都由一个数字和后缀组成。 这些部分的ASCII后缀为“D”、“H”、“M”和“S”，以天、小时、分和秒表示，在大小写或小写中接受。 后缀必须按顺序发生。 ASCII字母“T”必须出现在小时、分钟或第二节的第一个出现（如果有）之前。 四个部分中必须至少有一个部分必须存在，如果存在“T”，则“T”之后必须至少有一个部分。 每个部分的数字部分必须由一个或多个ASCII数字组成。 数字可以由ASCII负或正符号作为前缀。 必须分析的天数、小时数和分钟数。 必须对的秒数以及可选分数进行解析。 小数点可以是点或逗号。 小数部分可以具有从零到9位。

## 签名和返回类型

`toDuration(<string>)`

`toDuration(<integer>)`

返回持续时间。

## 示例

`toDuration("PT10H")`

返回10小时的持续时间。

`toDuration("PT4S")`

返回4s的持续时间。

`toDuration(4000)`

返回4s的持续时间。
