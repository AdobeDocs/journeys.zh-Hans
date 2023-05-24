---
product: adobe campaign
title: replace
description: 瞭解函式取代
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

以基礎字串中的取代字串取代符合目標字串的第一個專案。

取代會從字串的開頭到結尾進行，例如，將字串「aaa」中的「aa」取代為「b」將會產生「ba」而不是「ab」。

## 类别

字符串

## 函式語法

`replace(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|--------------|
| 基底 | 字符串 |
| Target | 字串(RegExp) |
| 取代 | 字符串 |

## 簽章和傳回的型別

`replace(<base>,<target>,<replacement>)`

傳回字串。

## 示例 1

`replace("Hello World", "l", "x")`

傳回「Hexlo World」。

## 示例 2 {#example_2}

由於目標引數是RegExp，因此根據您要取代的字串，您可能需要逸出部分字元。 示例如下：

* 要評估的字串： `|OFFER_A|OFFER_B`
* 由設定檔屬性提供 `#{ExperiencePlatform.myFieldGroup.profile.myOffers}`
* 要取代的字串： `|OFFER_A`
* 字串取代為： `''`
* 您需要新增 `\\` 早於 `|` 字元。

運算式為：

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|OFFER_A', '')`

傳回的字串是： `|OFFER_B`

您也可以建置要由指定屬性取代的字串：

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|' + #{ExperiencePlatform.myFieldGroup.profile.myOfferCode}, '')`
