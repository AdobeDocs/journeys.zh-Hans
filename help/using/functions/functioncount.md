---
product: adobe campaign
title: count
description: 了解函数计数
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 46528642-18d5-4ca9-a344-de2c7f939d00
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 30%

---

# 计数 {#count}

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
| 列表 | listDateOnly |

## 签名和返回类型

`count(<listAny>)`

返回整数。

## 示例

`count([10,2,10,null])`

返回3。
