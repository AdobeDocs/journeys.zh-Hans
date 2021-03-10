---
product: adobe campaign
solution: Journey Orchestration
title: distinctCountWithNull
description: 了解函数distinctCountWithNull
feature: 历程
role: 数据工程师
level: 富有经验
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 23%

---


# distinctCountWithNull {#distinctCountWithNull}

计算包括空值在内的不同值的数量。

## 类别

聚合

## 函数语法

`distinctCountWithNull(<listAny>)`

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

## 签名和返回的类型

`distinctCountwithNull(<listAny>)`

返回整数。

## 示例

`distinctCountWithNull([10,2,10,null])`

返回3。
