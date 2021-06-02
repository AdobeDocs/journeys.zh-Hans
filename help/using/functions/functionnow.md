---
product: adobe campaign
title: now
description: 立即了解该函数
feature: 历程
role: Data Engineer
level: Experienced
exl-id: ab1f9efe-cbb7-4e3a-ace0-24f2fb6165cb
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 14%

---

# now {#now}

以日期时间格式返回当前日期。 有关数据类型的更多信息，请参阅[此页面](../expression/data-types.md)。

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
