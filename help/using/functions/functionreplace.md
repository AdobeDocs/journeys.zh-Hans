---
product: adobe campaign
solution: Journey Orchestration
title: replace
description: 了解函数替换
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 6%

---


# replace {#replace}

用基字符串中的替换字符串替换与目标字符串匹配的第一个匹配项。

替换从字符串的开头到结尾，例如，将字符串&quot;aaa&quot;中的&quot;aa&quot;替换为&quot;b&quot;将导致&quot;ba&quot;而不是&quot;ab&quot;。

## 类别

字符串

## 函数语法

`replace(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|--------------|
| 基 | 字符串 |
| 目标 | 字符串 |
| 替换 | 字符串 |

## 签名和返回的类型

`replace(<base>,<target>,<replacement>)`

返回字符串。

## 示例

`replace("Hello World", "l", "x")`

返回“Hexlo World”。
