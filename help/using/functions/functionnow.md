---
product: adobe campaign
solution: Journey Orchestration
title: now
description: 立即了解该功能
feature: 历程
role: 数据工程师
level: 富有经验
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 11%

---


# now {#now}

以日期时间格式返回当前日期。 有关数据类型的详细信息，请参阅[此页](../expression/data-types.md)。

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

`now("<timeZone id>")`

返回dateTime。

## 示例

`now()`

返回2019-06-03T06:30Z。

`toString(now())`

返回“2019-06-03T06:30Z”

`now("Europe/Paris")`

返回2019-06-03T08:30+02:00。