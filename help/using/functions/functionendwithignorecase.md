---
product: adobe campaign
solution: Journey Orchestration
title: endWithIgnoreCase
description: 了解函数endWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 5%

---


# endWithIgnoreCase {#endWithIgnoreCase}

检查第一个参数字符串是否以特定字符串（第二个参数字符串）结尾，而不考虑大小写。

## 类别

字符串

## 函数语法

`endWithIgnoreCase(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 字符串 | 字符串 |
| 后缀 | 字符串 |

## 签名和返回的类型

`endWithIgnoreCase(<string>,<string>)`

返回布尔值。

## 示例

`endWithIgnoreCase("rowing is great', "AT")`

返回true。
