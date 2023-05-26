---
product: adobe campaign
title: endWithIgnoreCase
description: 了解函数endWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3d14fe82-e287-4474-8d78-10efbf55d338
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 18%

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

`endWithIgnoreCase("rowing is great", "AT")`

返回真。
