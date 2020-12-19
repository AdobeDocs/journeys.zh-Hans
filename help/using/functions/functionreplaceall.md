---
product: adobe campaign
solution: Journey Orchestration
title: replaceAll
description: 了解函数replaceAll
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# replaceAll {#replaceAll}

用基字符串中的替换字符串替换与目标字符串匹配的所有匹配项。

例如，替换从字符串的开头到结尾，将字符串“aaa”替换为“b”将导致“ba”而不是“ab”。

## 类别

字符串

## 函数语法

`replaceAll(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|--------------|
| 基础 | 字符串 |
| 目标 | 字符串 |
| 替换 | 字符串 |

## 签名和返回类型

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

返回字符串。

## 示例

`replaceAll("Hello World", "l", "x")`

返回“Hexxo Worxd”。
