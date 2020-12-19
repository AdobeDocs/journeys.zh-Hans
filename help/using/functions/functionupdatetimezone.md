---
product: adobe campaign
solution: Journey Orchestration
title: updateTimeZone
description: 了解函数updateTimeZone
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# updateTimeZone {#updateTimeZone}

返回新的日期时间，同时返回一个新时区。

## 类别

日期

## 函数语法

`updateTimeZone(<parameters>)`

## 参数

* 时区id:字符串
* dateTime

## 签名和返回类型

`updateTimeZone(<dateTime>,<timeZone id>)`

返回日期时间。

## 示例

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

返回2019-08-28T17:15:30.123+02:00。

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`

Returns "2019-08-28T17:15:30.123+02:00".-->
