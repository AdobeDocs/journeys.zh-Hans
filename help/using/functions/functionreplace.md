---
product: adobe campaign
solution: Journey Orchestration
title: replace
description: 了解函数替换
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 5%

---


# replace {#replace}

用基字符串中的替换字符串替换与目标字符串匹配的第一个匹配项。

例如，替换从字符串的开头到结尾，将字符串“aaa”替换为“b”将导致“ba”而不是“ab”。

## 类别

字符串

## 函数语法

`replace(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|--------------|
| 基础 | 字符串 |
| 目标 | 字符串 |
| 替换 | 字符串 |

## 签名和返回类型

`replace(<base>,<target>,<replacement>)`

返回字符串。

## 示例

`replace("Hello World", "l", "x")`

返回“Hexlo World”。
