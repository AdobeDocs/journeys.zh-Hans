---
title: updateTimeZone
description: 了解函数updateTimeZone
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
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 4%

---


# updateTimeZone {#updateTimeZone}

返回新的日期时间，同时返回一个新时区。

## 类别

日期

## 函数语法

`updateTimeZone(<parameters>)`

## 参数

* 时区id: 字符串
* dateTime

## 签名和返回类型

`updateTimeZone(<dateTime>,<timeZone id>)`

返回日期时间。

## 示例

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

返回2019-08-28T17:15:30.123+02:00。

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`

Returns "2019-08-28T17:15:30.123+02:00".-->
