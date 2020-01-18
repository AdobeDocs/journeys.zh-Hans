---
title: toDuration
description: 了解toDuration函数
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 239efa9592b011c70e2fc331df8f33820301253d

---


# toDuration {#toDuration}

将参数值转换为持续时间。 有关数据类型的详细信息，请参阅 [](../expression/data-types.md)。

## 类别

转化

## 函数语法

`toDuration(<parameter>)`

## 参数

| 参数 | 说明 |
|--- |--- |
| 字符串 | 基于ISO-8601持续时间格式的PnDTnHnMn.nS格式，天数被认为刚好24小时 |
| 整数 | 毫秒数 |

如果字符串表达式：接受的格式基于ISO-8601持续时间格式PnDTnHnMn.nS，其天数被认为恰好为24小时。

字符串以可选符号开头，由ASCII负或正符号表示。 如果为负，则整个周期被否定。 ASCII字母“P”的下一个大小写。 然后有四个部分，每个部分都由数字和后缀组成。 这些部分的后缀为“D”、“H”、“M”和“S”的ASCII，后缀为天、小时、分和秒，在大小写中接受。 后缀必须按顺序出现。 ASCII字母“T”必须在小时、分钟或第二节的第一个出现（如果有）之前出现。 四个部分中至少有一个必须存在，如果“T”存在，则“T”之后必须至少有一个部分。 每个部分的数字部分必须由一个或多个ASCII数字组成。 该数字可以由ASCII负号或正号作为前缀。 天数、小时数和分钟数必须随之分析。 必须解析到的秒数以及可选部分。 小数点可以是点或逗号。 小数部分可具有从零到9位数。

## 签名和返回类型

`toDuration(<string>)`

`toDuration(<integer>)`

返回持续时间。

## 示例

`toDuration("PT10H")`

返回10小时的持续时间。

`toDuration("PT4S")`

返回持续时间4秒。

`toDuration(4000)`

返回持续时间4秒。
