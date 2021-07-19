---
product: adobe campaign
title: updateTimeZone
description: 了解函数updateTimeZone
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 9%

---


# updateTimeZone {#updateTimeZone}

返回新的日期时间，并在同一时间返回新的时区。

## 类别

日期

## 函数语法

`updateTimeZone(<parameters>)`

## 参数

* 时区id:字符串
* dateTime

## 签名和返回的类型

`updateTimeZone(<dateTime>,<timeZone id>)`

返回日期时间。

## 示例

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

返回2019-08-28T17:15:30.123+02:00。

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`

Returns "2019-08-28T17:15:30.123+02:00".-->
