---
product: adobe campaign
solution: Journey Orchestration
title: containWithIgnoreCase
description: 了解函数containWithIgnoreCase
feature: 历程
role: 数据工程师
level: 富有经验
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 9%

---


# containWithIgnoreCase {#containWithIgnoreCase}

检查第二个参数字符串是否包含在第一个参数字符串中，而不考虑大小写。

## 类别

字符串

## 函数语法

`containWithIgnoreCase(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 字符串 | 字符串 |
| 搜索 | 字符串 |

## 签名和返回的类型

`containWithIgnoreCase(<string>,<string>)`

返回布尔值。

## 示例

`containWithIgnoreCase("rowing is great', "GREAT")`

返回true。
