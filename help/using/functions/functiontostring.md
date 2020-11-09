---
title: toString
description: 了解函数toString
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: bcb8a71a27e2b9e37af7d0260cec04ed0fda24ee
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 4%

---


# toString {#toString}

根据参数值的类型，将参数值转换为字符串值。 For more information on data types, refer to [this page](../expression/data-types.md).

## 类别

转换

## 函数语法

`toString(<parameter>)`

## 参数

| 参数 | 说明 |
|--- |--- |
| dateTime | 以UTC日期格式转换日期 |
| dateTimeOnly | 以UTC日期格式转换日期 |
| 持续时间 | 以字符串形式转换为相应的毫秒数 |
| 时区 | 转换为时区id字符串表示法(JODA id) |
| 整数 | 转换为值的字符串表示形式（1变为“1”） |
| 小数 | 转换为值的字符串表示形式（1.5变为“1.5”） |
| 布尔 | 如果为true，则将布尔值转换为“true”；如果为false，则将布尔值转换为“false” |

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
