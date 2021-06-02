---
product: adobe campaign
title: matchRegExp
description: 了解函数matchRegExp
feature: 历程
role: Data Engineer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 6%

---

# matchRegExp {#matchRegExp}

如果第一个参数中的字符串与第二个参数中的正则表达式匹配，则返回true。 有关更多信息，请参阅[此页面](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html)。

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

在此，您可以检查字符串是否满足正则表达式（java语法）：以“Hello”开头，然后是任何类型的字符串，以“World”结尾。
