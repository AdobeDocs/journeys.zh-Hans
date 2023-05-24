---
product: adobe campaign
title: updateTimeZone
description: 瞭解函式updateTimeZone
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

傳回新的日期時間，並在同一時間點使用新的時區。

## 类别

日期

## 函式語法

`updateTimeZone(<parameters>)`

## 参数

* 時區id：字串
* dateTime

## 簽章和傳回的型別

`updateTimeZone(<dateTime>,<timeZone id>)`

傳回日期時間。

## 示例

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

傳回2019-08-28T17:15:30.123+02:00。

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`
Returns "2019-08-28T17:15:30.123+02:00".-->

`updateTimeZone(@{MyExpEvent.timestamp}, "Australia/Sydney")`

如果時間戳記欄位的值為 `2021-11-16T16:55:12.939318+01:00`，則函式會傳回 `2021-11-17T02:55:12.942115+11:00`.
