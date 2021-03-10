---
product: adobe campaign
solution: Journey Orchestration
title: matchRegExp
description: 了解函数matchRegExp
feature: 历程
role: 数据工程师
level: 富有经验
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 5%

---


# matchRegExp {#matchRegExp}

如果第一个参数中的字符串与第二个参数中的常规表达式匹配，则返回true。 有关详细信息，请参阅[此页](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html)。

## 类别

字符串

## 函数语法

`matchRegExp(<parameters>)`

## 参数

| 参数 | 类型 |
|--- |--- |
| 字符串 | 字符串 |
| regexp | 字符串 |

## 签名和返回的类型

`matchRegExp(<string>,<string>)`

返回true。

## 示例

`matchRegExp("Hello World", "Hello\s+World")`

返回true。

解释：

在此，您检查字符串是否满足常规表达式（java语法）：开始，然后是任何类型的字符串，最后是“World”。
