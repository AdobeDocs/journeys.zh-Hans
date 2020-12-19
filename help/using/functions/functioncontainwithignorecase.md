---
product: adobe campaign
solution: Journey Orchestration
title: containWithIgnoreCase
description: 了解函数containWithIgnoreCase
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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
| 搜索字符串 | 字符串 |

## 签名和返回类型

`containWithIgnoreCase(<string>,<string>)`

返回布尔值。

## 示例

`containWithIgnoreCase("rowing is great', "GREAT")`

返回true。
