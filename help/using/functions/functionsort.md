---
title: 排序
description: 了解函数排序
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

---


# 排序 {#sort}

按自然顺序对值列表进行排序。 第一个参数是值列表，第二个参数是指示排序是升序(true)还是降序(false)的布尔值。

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
| Boolean | Boolean |

## 签名和返回类型

`sort(<listInteger>,<boolean>)`

返回整数列表。

`sort(<listDecimal>,<boolean>)`

返回小数位列表。

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

退货 `["A","B","C"]`。

`sort([1, 3, 2], false)`

退货 `[3, 2, 1]`。
