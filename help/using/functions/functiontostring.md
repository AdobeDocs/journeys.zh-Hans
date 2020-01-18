---
title: toString
description: 了解toString函数
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


# toString {#toString}

根据参数值的类型，将参数值转换为字符串值。 有关数据类型的详细信息，请参阅 [](../expression/data-types.md)。

## 类别

转化

## 函数语法

`toString(<parameter>)`

## 参数

| 参数 | 说明 |
|--- |--- |
| dateTime | 转换UTC日期格式的日期 |
| dateTimeOnly | 转换UTC日期格式的日期 |
| 持续时间 | 以字符串形式转换为相应的毫秒数 |
| 时区 | 转换为时区ID字符串表示(JODA ID) |
| 整数 | 转换为值的字符串表示形式（1变为“1”） |
| 小数点 | 转换为值的字符串表示形式（1.5变为“1.5”） |
| 布尔值 | 如果为true，则将布尔值转换为“true”；如果为false，则将布尔值转换为“false” |

## 签名和返回类型

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<timeZone>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

返回字符串。

## 示例

`toString(4)`

返回“4”。
