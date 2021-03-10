---
product: adobe campaign
solution: Journey Orchestration
title: substr
description: 了解函数子字符串
feature: 历程
role: 数据工程师
level: 富有经验
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 7%

---


# substr {#substr}

返回开始索引和结束索引之间的字符串表达式的子字符串。 如果未定义结束索引，则它位于开始索引和结束索引之间。

## 类别

字符串

## 函数语法

`substr(<parameters>)`

## 参数

| 参数 | 类型 |
|-------------|----------|
| 字符串 | 字符串 |
| beginIndex | 整数 |
| endIndex | 整数 |

## 签名和返回的类型

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

返回字符串。

## 示例

`substr("Hello World",6)`

返回“世界”。

`substr("Hello World", 0, 5)`

返回“Hello”。