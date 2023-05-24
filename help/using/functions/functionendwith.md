---
product: adobe campaign
title: endWith
description: 瞭解函式endWith
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 6eee6057-1daf-4b9d-ae94-2b35843e3a49
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 25%

---

# endWith {#endWith}

如果第二個引數是第一個引數的尾碼，則傳回true。

## 类别

字符串

## 函式語法

`endWith(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 字符串 | 字符串 |
| 字尾 | 字符串 |

## 簽章和傳回的型別

`endWith(<string>,<string>)`

傳回布林值。

## 示例

`endWith("Hello World", "World")`

傳回true。

`endWith("Hello World", "Hello")`

傳回false。
