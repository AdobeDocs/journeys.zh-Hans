---
product: adobe campaign
solution: Journey Orchestration
title: count
description: 了解函数计数
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 22%

---


# count {#count}

计算列表的元素，而不考虑null值。

## 类别

聚合

## 函数语法

`count(<listAny>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 列表 | listString |
| 列表 | listBoolean |
| 列表 | listInteger |
| 列表 | listDecimal |
| 列表 | listDuration |
| 列表 | listDateTime |
| 列表 | listDateTimeOnly |

## 签名和返回类型

`count(<listAny>)`

返回整数。

## 示例

`count([10,2,10,null])`

返回3。
