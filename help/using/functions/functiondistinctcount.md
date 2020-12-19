---
product: adobe campaign
solution: Journey Orchestration
title: distinctCount
description: 了解distinctCount函数
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# distinctCount{#distinctCount}

计算忽略null值的不同值的数量。

## 类别

聚合

## 函数语法

`distinctCount(<listAny>)`

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

`distinctCount(<listAny>)`

返回整数。

## 示例

`distinctCount([10,2,10,null])`

返回2。
