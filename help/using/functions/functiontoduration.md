---
product: adobe campaign
solution: Journey Orchestration
title: toDuration
description: 了解toDuration函数
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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
| 字符串 | 基于ISO-8601持续时间格式的格式PnDTnHnMn.nS，天数被认为恰好为24小时 |
| 整数 | 毫秒数 |

如果字符串表达式:接受的格式基于ISO-8601持续时间格式PnDTnHnMn.nS，其天数被认为正好24小时。

带有可选符号的字符串开始，由ASCII负或正符号表示。 如果为负，则整个周期被否定。 ASCII字母“P”在大写或小写中是下一个。 然后有四个部分，每个部分都由数字和后缀组成。 这些部分的后缀以“D”、“H”、“M”和“S”的ASCII表示，以大写或小写形式接受，时间、小时、分钟和秒。 后缀必须按顺序发生。 ASCII字母“T”必须在小时、分钟或第二节的第一个出现（如果有）之前出现。 四个部分中至少有一个必须存在，如果存在“T”，则“T”之后必须至少有一个部分。 每个部分的数字部分必须由一个或多个ASCII数字组成。 数字可以由ASCII负或正符号前缀。 天数、小时数和分钟数必须随之分析。 秒数必须与可选分数一起解析到。 小数点可以是点或逗号。 分数部分可具有从零到9位数。

## 签名和返回类型

`toDuration(<string>)`

`toDuration(<integer>)`

返回持续时间。

## 示例

`toDuration("PT10H")`

返回10小时的持续时间。

`toDuration("PT4S")`

返回4秒的持续时间。

`toDuration(4000)`

返回4秒的持续时间。
