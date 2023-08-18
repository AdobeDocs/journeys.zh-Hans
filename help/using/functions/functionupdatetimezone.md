---
product: adobe campaign
title: updateTimeZone
description: 了解函数updateTimeZone
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2ce60ed2-161a-4b98-9694-eb47cc0e04a9
source-git-commit: d5531d0aad22f33da2cc5612cc289c600411fd8c
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 11%

---

# updateTimeZone {#updateTimeZone}

返回新的日期时间，同一时刻具有新的时区。

## 类别

日期

## 函数语法

`updateTimeZone(<parameters>)`

## 参数

* 时区id：字符串
* dateTime

## 签名和返回的类型

`updateTimeZone(<dateTime>,<timeZone id>)`

返回日期时间。

## 示例

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

返回2019-08-28T17:15:30.123+02:00。

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`
Returns "2019-08-28T17:15:30.123+02:00".-->

`updateTimeZone(@{MyExpEvent.timestamp}, "Australia/Sydney")`

如果时间戳字段的值为 `2021-11-16T16:55:12.939318+01:00`，则函数会返回 `2021-11-17T02:55:12.942115+11:00`.
