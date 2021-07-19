---
product: adobe campaign
title: sort
description: 了解函数排序
feature: 历程
role: Data Engineer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 17%

---

# 排序 {#sort}

按自然顺序对值列表进行排序。 第一个参数是值列表，第二个是布尔值，用于指示排序是升序(true)还是降序(false)。

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

返回小数列表。

`sort(<listString>,<boolean>)`

返回字符串列表。

`sort(<listDateTimeOnly>,<boolean>)`

返回不考虑时区的日期时间列表。

`sort(<listDateTime>,<boolean>)`

返回datetimes列表。

`sort(<listBoolean>,<boolean>)`

返回布尔值列表。

## 示例

`sort(["A", "C", "B"], true)`

返回结果 `["A","B","C"]`.

`sort([1, 3, 2], false)`

返回结果 `[3, 2, 1]`.
