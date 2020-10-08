---
title: sort
description: 了解函数排序
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 10%

---


# sort {#sort}

按自然顺序对列表值进行排序。 第一个参数是值的列表，第二个参数是指示排序是升序(true)还是降序(false)的布尔值。

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

## 签名和返回类型

`sort(<listInteger>,<boolean>)`

返回整数列表。

`sort(<listDecimal>,<boolean>)`

返回一列表小数。

`sort(<listString>,<boolean>)`

返回一列表字符串。

`sort(<listDateTimeOnly>,<boolean>)`

返回日期时间列表，不考虑时区。

`sort(<listDateTime>,<boolean>)`

返回datetimes的列表。

`sort(<listBoolean>,<boolean>)`

返回一列表布尔语。

## 示例

`sort(["A", "C", "B"], true)`

退货 `["A","B","C"]`。

`sort([1, 3, 2], false)`

退货 `[3, 2, 1]`。
