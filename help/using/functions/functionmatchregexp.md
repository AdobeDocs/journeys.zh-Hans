---
product: adobe campaign
title: matchRegExp
description: 了解函数matchRegExp
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: a5d063784b278120b61f8d2641264baf40e34a90
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 18%

---

# matchRegExp {#matchRegExp}

如果第一个参数中的字符串与第二个参数中的正则表达式匹配，则返回true。 有关更多信息，请参阅 [此页面](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

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

返回布尔值。

## 示例

`matchRegExp("username@adobe.com", "*adobe")`

返回真。
