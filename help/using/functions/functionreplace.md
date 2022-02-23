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

# 替换 {#replace}

将与目标字符串匹配的第一个实例替换为基本字符串中的替换字符串。

替换从字符串的开头到结尾，例如，将字符串“aaa”中的“aa”替换为“b”将生成“ba”而不是“ab”。

## 类别

字符串

## 函数语法

`replace(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|--------------|
| 基础 | 字符串 |
| Target | 字符串（正则表达式） |
| 替换 | 字符串 |

## 签名和返回的类型

`replace(<base>,<target>,<replacement>)`

返回字符串。

## 示例 1

`replace("Hello World", "l", "x")`

返回“Hexlo World”。

## 示例 2 {#example_2}

由于target参数是正则表达式，因此根据要替换的字符串，您可能需要对某些字符进行转义。 示例如下：

* 要评估的字符串： `|OFFER_A|OFFER_B`
* 由配置文件属性提供 `#{ExperiencePlatform.myFieldGroup.profile.myOffers}`
* 要替换的字符串： `|OFFER_A`
* 字符串替换为： `''`
* 您需要添加 `\\` 在 `|` 字符。

表达式为：

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|OFFER_A', '')`

返回的字符串为： `|OFFER_B`

您还可以构建要从给定属性替换的字符串：

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|' + #{ExperiencePlatform.myFieldGroup.profile.myOfferCode}, '')`
