---
product: adobe campaign
title: in
description: 了解中的函数
feature: Journeys
role: Developer
level: Experienced
exl-id: 6a19ae25-99c9-47f9-8417-c3d247dbbe3f
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
source-wordcount: '113'
ht-degree: 24%
---
# in {#in}

检查第一个参数值是否在列表中。 检查通过对每个参数值执行Equal。 如果找到参数值，则返回true；否则，返回false。

`<expression>`的类型必须与列表项匹配。 作为提醒，列表的项目类型必须匹配。

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
| 日期时间 | 日期时间 |
| DateTimeOnly | DateTimeOnly |
| 列表 | listString |
| 列表 | listBoolean |
| 列表 | listInteger |
| 列表 | listDecimal |
| 列表 | listDuration |
| 列表 | listDateTime |
| 列表 | listDateTimeOnly |
| 列表 | listDateOnly |

## 签名和返回的类型

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<dateOnly>,<listDateOnly>)`

`in(<duration>,<listDuration>)`

返回布尔值。

## 示例

`in(4,[4,5,3,4])`

返回真。

`in(8,[4,5,3,4])`

返回假。

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`
