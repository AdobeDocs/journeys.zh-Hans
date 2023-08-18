---
product: adobe campaign
title: replace
description: 了解函数替换
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: f30377c2-4d5e-4905-a972-8f4ccb272bc0
source-git-commit: 8980df5cc238a7195f01a1631e418a8de677fbea
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 10%

---

# replace {#replace}

使用基本字符串中的替换字符串替换匹配目标字符串的第一个匹配项。

例如，替换操作从字符串的开头到结尾进行，将字符串“aaa”中的“aa”替换为“b”将导致“ba”而不是“ab”。

## 类别

字符串

## 函数语法

`replace(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|--------------|
| 基础 | 字符串 |
| Target | 字符串(RegExp) |
| 替换 | 字符串 |

## 签名和返回的类型

`replace(<base>,<target>,<replacement>)`

返回字符串。

## 示例 1

`replace("Hello World", "l", "x")`

返回“Hexlo World”。

## 示例 2 {#example_2}

由于target参数是RegExp，因此根据要替换的字符串，您可能需要转义某些字符。 示例如下：

* 要计算的字符串： `|OFFER_A|OFFER_B`
* 由配置文件属性提供 `#{ExperiencePlatform.myFieldGroup.profile.myOffers}`
* 要替换的字符串： `|OFFER_A`
* 字符串替换为： `''`
* 您需要添加 `\\` 早于 `|` 字符。

表达式为：

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|OFFER_A', '')`

返回的字符串是： `|OFFER_B`

您还可以构建要替换给定属性的字符串：

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|' + #{ExperiencePlatform.myFieldGroup.profile.myOfferCode}, '')`
