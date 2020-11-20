---
product: adobe campaign
solution: Journey Orchestration
title: distinctCountWithNull
description: 了解函数distinctCountWithNull
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '47'
ht-degree: 23%

---


# distinctCountWithNull {#distinctCountWithNull}

计算包括null值在内的不同值的数量。

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

## 签名和返回类型

`distinctCountwithNull(<listAny>)`

返回整数。

## 示例

`distinctCountWithNull([10,2,10,null])`

返回3。
