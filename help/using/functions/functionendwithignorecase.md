---
product: adobe campaign
solution: Journey Orchestration
title: endWithIgnoreCase
description: 了解函数endWithIgnoreCase
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 4%

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

## 签名和返回类型

`endWithIgnoreCase(<string>,<string>)`

返回布尔值。

## 示例

`endWithIgnoreCase("rowing is great', "AT")`

返回true。
