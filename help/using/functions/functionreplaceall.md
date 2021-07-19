---
product: adobe campaign
title: replaceAll
description: 了解函数replaceAll
feature: 历程
role: Data Engineer
level: Experienced
exl-id: d60059e5-6bf8-4a57-88a4-5323d5f0fa0b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 17%

---

# replaceAll {#replaceAll}

将与目标字符串匹配的所有发生次数替换为基本字符串中的替换字符串。

替换从字符串的开头到结尾，例如，将字符串“aaa”中的“aa”替换为“b”将生成“ba”而不是“ab”。

## 类别

字符串

## 函数语法

`replaceAll(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|--------------|
| 基础 | 字符串 |
| Target | 字符串 |
| 替换 | 字符串 |

## 签名和返回的类型

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

返回字符串。

## 示例

`replaceAll("Hello World", "l", "x")`

返回“Hexxo Worxd”。
