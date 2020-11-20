---
product: adobe campaign
solution: Journey Orchestration
title: startWith
description: 了解函数的开头
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 9%

---


# startWith {#startWith}

如果第二个参数是第一个参数的前缀，则返回true。

## 类别

字符串

## 函数语法

`startWith(<parameters>)`

## 参数

| 参数 | 类型 |
|-------------|--------|
| 字符串 | 字符串 |
| 前缀 | 字符串 |

## 签名和返回类型

`startWith(<string>,<string>)`

返回布尔值。

## 示例

`startWith("Hello World", "Hello")`

返回true。

`startWith("Hello World", "World")`

返回false。
