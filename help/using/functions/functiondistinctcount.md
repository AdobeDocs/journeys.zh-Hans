---
title: distinctCount
description: 了解distinctCount函数
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
