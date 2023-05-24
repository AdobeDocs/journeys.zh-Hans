---
product: adobe campaign
title: containIgnoreCase
description: 瞭解函式containIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 22%

---

# containIgnoreCase {#containIgnoreCase}

檢查第二個引數字串是否包含在第一個引數字串中，而不考慮大小寫。

## 类别

字符串

## 函式語法

`containIgnoreCase(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 字符串 | 字符串 |
| 字串已搜尋 | 字符串 |

## 簽章和傳回的型別

`containIgnoreCase(<string>,<string>)`

傳回布林值。

## 示例

`containIgnoreCase("rowing is great", "GREAT")`

傳回true。
