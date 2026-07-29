---
product: adobe campaign
title: substr
description: 了解函数substr
feature: Journeys
role: Developer
level: Experienced
exl-id: dda01de5-b865-4323-ac36-2e3d90d213ee
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '65'
ht-degree: 18%

---

# substr {#substr}

返回字符串表达式在开始索引和结束索引之间的子字符串。 如果未定义结束索引，则它介于开始索引和结束索引之间。

## 类别

字符串

## 函数语法

`substr(<parameters>)`

## 参数

| 参数 | 类型 |
|-------------|----------|
| 字符串 | 字符串 |
| beginindex | 整数 |
| endIndex | 整数 |

## 签名和返回的类型

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

返回字符串。

## 示例

`substr("Hello World",6)`

返回“World”。

`substr("Hello World", 0, 5)`

返回“Hello”。
