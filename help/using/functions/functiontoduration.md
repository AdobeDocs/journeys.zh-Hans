---
product: adobe campaign
title: toDuration
description: 了解函数toDuration
feature: Journeys
role: Developer
level: Experienced
exl-id: 77f068fa-678e-49a4-b45f-843c3287390a
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 3%
---
# toDuration {#toDuration}

将参数值转换为持续时间。 有关数据类型的详细信息，请参阅[此页面](../expression/data-types.md)。

## 类别

转化

## 函数语法

`toDuration(<parameter>)`

## 参数

| 参数 | 说明 |
|--- |--- |
| 字符串 | 基于ISO-8601持续时间格式PnDTnHnMn.nS的格式，天数被视为刚好24小时 |
| 整数 | 毫秒数 |

如果字符串表达式：接受的格式基于ISO-8601持续时间格式PnDTnHnMn.nS，天数被认为刚好是24小时。

字符串以可选符号开头，由ASCII负号或正号表示。 如果为负值，则整个期间将被否定。 ASCII字母“P”是下一个大写或小写。 然后有四个部分，每个部分包含一个数字和一个后缀。 各节的ASCII后缀为“D”、“H”、“M”和“S”，表示日、小时、分钟和秒，可使用大写或小写。 后缀必须按顺序出现。 ASCII字母“T”必须出现在小时、分钟或秒部分的第一次（如果有）之前。 四个部分中的至少一个必须存在，如果存在“T”，则“T”后面必须至少有一个部分。 每个部分的数字部分必须包含一个或多个ASCII数字。 数字可以用ASCII负号或正号作为前缀。 必须将天数、小时数和分钟数解析为。 必须解析到的秒数以及可选的分数。 小数点可以是点或逗号。 小数部分可以有0到9位数字。

## 签名和返回的类型

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
