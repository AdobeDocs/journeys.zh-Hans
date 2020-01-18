---
title: 不同
description: 了解功能的独特性
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


# 不同 {#distinct}

返回不带空值的列表的不同值。

## 类别

列表

## 函数语法

`distinct(<parameter>)`

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

`distinct(<listInteger>)`

返回整数列表。

`distinct(<listDecimal>)`

返回小数位列表。

`distinct(<listString>)`

返回字符串列表。

`distinct(<listDateTimeOnly>)`

返回不考虑时区的日期时间列表。

`distinct(<listDateTime>)`

返回datetimes列表。

`distinct(<listBoolean>)`

返回布尔值列表。

`distinct(<listDuration>)`

返回持续时间列表。

## 示例

`distinct([10,2,10,null])`

退货 `[10, 2]`。
