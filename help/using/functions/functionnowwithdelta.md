---
title: nowWithDelta
description: 立即了解函数WithDelta
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
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 4%

---


# nowWithDelta {#nowWithDelta}

返回包含偏移的当前日期时间。 如果指定了时区ID，则将应用时区偏移。 有关数据类型的详细信息，请参阅 [](../expression/data-types.md)。

## 类别

日期

## 函数语法

`nowWithDelta(<parameters>)`

## 参数

| 参数 | 说明 |
|--- |--- |
| 三角洲 | 正整数值 |
| 日期部分 | 年、月、日、小时、分钟或秒（字符串） |
| 时区id | 时区值的字符串表示形式。 有关详细信息，请参阅 [](../expression/data-types.md)。 时区ID必须是字符串常数。 它不能是字段引用或表达式。 |

## 签名和返回类型

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

返回dateTime。

## 示例

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

返回一个dateTime，恰好在2小时前。
