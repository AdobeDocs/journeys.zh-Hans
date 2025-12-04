---
product: adobe campaign
title: containIgnoreCase
description: 了解函数containIgnoreCase
feature: Journeys
role: Developer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 22%

---

# containIgnoreCase {#containIgnoreCase}

检查第二个参数字符串是否包含在第一个参数字符串中，而不考虑大小写。

## 类别

字符串

## 函数语法

`containIgnoreCase(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 字符串 | 字符串 |
| 搜索字符串 | 字符串 |

## 签名和返回的类型

`containIgnoreCase(<string>,<string>)`

返回布尔值。

## 示例

`containIgnoreCase("rowing is great", "GREAT")`

返回真。
