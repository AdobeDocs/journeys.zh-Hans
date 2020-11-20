---
product: adobe campaign
solution: Journey Orchestration
title: startWithIgnoreCase
description: 了解函数startWithIgnoreCase
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%

---


# startWithIgnoreCase {#startWithIgnoreCase}

如果第二个参数是第一个参数的前缀而不考虑大小写，则返回true。

## 类别

字符串

## 函数语法

`startWithIgnoreCase(<parameters>)`

## 参数

| 参数 | 类型 |
|-------------|--------|
| 字符串 | 字符串 |
| 前缀 | 字符串 |

## 签名和返回类型

`startWithIgnoreCase(<string>,<string>)`

返回布尔值。

## 示例

`startWith("rowing is great', "RO")`

返回true。
