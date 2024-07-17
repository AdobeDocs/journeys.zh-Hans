---
product: adobe campaign
title: replaceAll
description: 了解函数replaceAll
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d60059e5-6bf8-4a57-88a4-5323d5f0fa0b
source-git-commit: 8980df5cc238a7195f01a1631e418a8de677fbea
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 10%

---

# replaceAll {#replaceAll}

使用基本字符串中的替换字符串替换匹配目标字符串的所有匹配项。

例如，替换操作从字符串的开头到结尾进行，将字符串“aaa”中的“aa”替换为“b”将导致“ba”而不是“ab”。

## 类别

字符串

## 函数语法

`replaceAll(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|--------------|
| 基础 | 字符串 |
| 目标 | 字符串(RegExp) |
| 替换 | 字符串 |

## 签名和返回的类型

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

返回字符串。

## 示例{#example}

`replaceAll("Hello World", "l", "x")`

返回“Hexxo Worxd”。

由于target参数是RegExp，因此根据要替换的字符串，您可能需要转义某些字符。 请参阅[此页面](../functions/functionreplace.md#example_2)中的示例。
