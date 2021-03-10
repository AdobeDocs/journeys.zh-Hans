---
product: adobe campaign
solution: Journey Orchestration
title: sort
description: 了解函数排序
feature: 历程
role: 数据工程师
level: 富有经验
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 11%

---


# sort {#sort}

按自然顺序对值的列表排序。 第一个参数是值的列表，第二个参数是指示排序是升序(true)还是降序(false)的布尔值。

## 类别

列表

## 函数语法

`sort(<parameters>)`

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
| 布尔值 | 布尔值 |

## 签名和返回的类型

`sort(<listInteger>,<boolean>)`

返回整数列表。

`sort(<listDecimal>,<boolean>)`

返回一列表小数。

`sort(<listString>,<boolean>)`

返回字符串列表。

`sort(<listDateTimeOnly>,<boolean>)`

返回日期时间列表，不考虑时区。

`sort(<listDateTime>,<boolean>)`

返回datetime的列表。

`sort(<listBoolean>,<boolean>)`

返回一列表布尔语。

## 示例

`sort(["A", "C", "B"], true)`

返回`["A","B","C"]`。

`sort([1, 3, 2], false)`

返回`[3, 2, 1]`。
