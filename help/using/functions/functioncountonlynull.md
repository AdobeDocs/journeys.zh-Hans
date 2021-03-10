---
product: adobe campaign
solution: Journey Orchestration
title: countOnlyNull
description: 了解函数countOnlyNull
feature: 历程
role: 数据工程师
level: 富有经验
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 24%

---


# countOnlyNull {#countOnlyNull}

计算列表中空值的数量。

## 类别

聚合

## 函数语法

`countOnlyNull(<listAny>)`

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

`countOnlyNull(<listAny>)`

返回整数。

## 示例

`count([10,2,10,null])`

返回1。
