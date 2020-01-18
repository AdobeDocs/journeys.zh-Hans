---
title: matchRegExp
description: 了解函数matchRegExp
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

---


# matchRegExp {#matchRegExp}

如果第一个参数中的字符串与第二个参数中的正则表达式匹配，则返回true。 有关详细信息，请参 [阅此页](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html)。

## 类别

字符串

## 函数语法

`matchRegExp(<parameters>)`

## 参数

| 参数 | 类型 |
|--- |--- |
| 字符串 | 字符串 |
| regexp | 字符串 |

## 签名和返回类型

`matchRegExp(<string>,<string>)`

返回true。

## 示例

`matchRegExp("Hello World", "Hello\s+World")`

返回true。

说明：

在此，您检查字符串是否满足正则表达式（java语法）:以“Hello”开头，然后是任何类型的字符串，最后是“World”。
