---
title: replaceAll
description: 了解函数replaceAll
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 5%

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
