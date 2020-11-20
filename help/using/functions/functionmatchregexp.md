---
product: adobe campaign
solution: Journey Orchestration
title: matchRegExp
description: 了解函数matchRegExp
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 4%

---


# matchRegExp {#matchRegExp}

如果第一个参数中的字符串与第二个参数中的常规表达式匹配，则返回true。 有关详细信息，请参 [阅此页](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html)。

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

返回真。

## 示例

`matchRegExp("Hello World", "Hello\s+World")`

返回true。

说明：

在此，您检查字符串是否满足常规表达式（java语法）:开始语中带有“Hello”，然后带有任何字符串并以“World”结尾。
