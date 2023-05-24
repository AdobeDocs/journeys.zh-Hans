---
product: adobe campaign
title: split
description: 瞭解函式分割
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 44499a09-19e2-4085-bf2f-7d9080ec382d
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 19%

---

# split {#split}

以分隔字串分割第一個引數字串（第二個引數字串，可以是規則運算式），以產生字串清單（代號）。

## 类别

字符串

## 函式語法

`split(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 輸入字串 | 字符串 |
| 分隔符號字串 | 字符串 |

## 簽章和傳回型別

`split(<input string>, <separator string>)`

傳回listString。

## 示例

`split(["A_B_C"], "_")`

返回结果 `["A","B","C"]`

具有值「20.45.2.3434」的事件欄位「event.appVersion」的範例

`split(@{event.appVersion}, "\\.")`

返回结果 `["20", "45", "2", "3434"]`
