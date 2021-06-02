---
product: adobe campaign
title: distinct
description: 了解不同的函数
feature: 历程
role: Data Engineer
level: Experienced
exl-id: 034e4d77-2f0e-4117-9fd4-b9e35ef71a39
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 15%

---

# distinct {#distinct}

返回列表的非重复值，但不包含空值。

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

返回小数列表。

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

返回`[10, 2]`。
