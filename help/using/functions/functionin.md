---
title: in
description: 了解
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
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

---


# in {#in}

检查第一个参数值是否在列表中。 检查通过“等于”(Equal)对每个参数值执行。 如果找到参数值，则返回true，否则返回false。

类型必须 `<expression>` 与列表项匹配。 列表中项目的类型必须相互匹配以作为提醒。

## 类别

列表

## 函数语法

`in(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 字符串 | 字符串 |
| Boolean | Boolean |
| 整数 | 整数 |
| 小数 | 小数 |
| 持续时间 | 持续时间 |
| DateTime | DateTime |
| DateTimeOnly | DateTimeOnly |
| 列表 | listString |
| 列表 | listBoolean |
| 列表 | listInteger |
| 列表 | listDecimal |
| 列表 | listDuration |
| 列表 | listDateTime |
| 列表 | listDateTimeOnly |

## 签名和返回类型

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<duration>,<listDuration>)`

返回布尔值。

## 示例

`in(4,[4,5,3,4])`

返回true。

`in(8,[4,5,3,4])`

返回false。

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`
