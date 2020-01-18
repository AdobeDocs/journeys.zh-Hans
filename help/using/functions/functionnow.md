---
title: 现在
description: 立即了解该功能
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
source-git-commit: 654888ee62a7b9b6e3d34fc3963fb83cac719003

---


# 现在 {#now}

以日期时间格式返回当前日期。 有关数据类型的详细信息，请参阅 [](../expression/data-types.md)。

## 类别

日期

## 函数语法

`now(<parameter>)`

## 参数

| 参数 | 说明 |
|--- |--- |
| 字符串 |  |

## 签名和返回类型

`now()`

`"now(<timeZone id>")`

返回dateTime。

## 示例

`now()`

返回2019-06-03T06:30Z。

`toString(now())`

返回“2019-06-03T06:30Z”

`now("Europe/Paris")`

返回2019-06-03T08:30+02:00。