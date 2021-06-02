---
product: adobe campaign
title: in
description: 了解
feature: 历程
role: Data Engineer
level: Experienced
exl-id: 6a19ae25-99c9-47f9-8417-c3d247dbbe3f
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 13%

---

# in {#in}

检查第一个参数值是否在列表中。 对每个参数值使用等于来执行检查。 如果找到参数值，则返回true，否则返回false。

`<expression>`的类型必须与列表项匹配。 列表项目的类型必须相互匹配，作为提醒。

## 类别

列表

## 函数语法

`in(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 字符串 | 字符串 |
| 布尔值 | 布尔值 |
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

## 签名和返回的类型

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
