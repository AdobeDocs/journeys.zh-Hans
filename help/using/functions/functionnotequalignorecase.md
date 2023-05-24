---
product: adobe campaign
title: notEqualIgnoreCase
description: 瞭解函式notEqualIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 13%

---

# notEqualIgnoreCase {#notEqualIgnoreCase}

檢查第一個引數字串與第二個引數字串是否不同，忽略大小寫考量。

## 类别

字符串

## 函式語法

`notEqualIgnoreCase(<parameters>)`

## 参数

* 字符串

## 簽章和傳回的型別

`notEqualIgnoreCase(<string>,<string>)`

傳回布林值。

## 示例

`notEqualIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad")`
