---
title: endWith
description: 了解函数endWith
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a844adc1a073aebfb7fd8a719e52f305079260b7
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 9%

---


# endWith {#endWith}

如果第二个参数是第一个参数的后缀，则返回true。

## 类别

字符串

## 函数语法

`endWith(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 字符串 | 字符串 |
| 后缀 | 字符串 |

## 签名和返回类型

`endWith(<string>,<string>)`

返回布尔值。

## 示例

`endWith("Hello World", "World")`

返回true。

`endWith("Hello World", "Hello")`

返回false。
