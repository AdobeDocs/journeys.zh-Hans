---
product: adobe campaign
title: endWithIgnoreCase
description: 瞭解函式endWithIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3d14fe82-e287-4474-8d78-10efbf55d338
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 18%

---

# endWithIgnoreCase {#endWithIgnoreCase}

檢查第一個引數字串是否以特定字串（第二個引數字串）結尾，而不考慮大小寫。

## 类别

字符串

## 函式語法

`endWithIgnoreCase(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 字符串 | 字符串 |
| 字尾 | 字符串 |

## 簽章和傳回的型別

`endWithIgnoreCase(<string>,<string>)`

傳回布林值。

## 示例

`endWithIgnoreCase("rowing is great", "AT")`

傳回true。
