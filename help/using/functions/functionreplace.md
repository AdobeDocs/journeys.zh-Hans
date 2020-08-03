---
title: replace
description: 了解函数替换
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c
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
