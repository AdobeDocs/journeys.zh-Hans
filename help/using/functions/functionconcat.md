---
title: concat
description: 了解函数概念
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

---


# concat {#concat}

连接两个字符串参数或字符串列表。

## 类别

字符串

## 函数语法

`concat(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 列表 | listString |
| 字符串 | 字符串 |

## 签名和返回类型

`concat(<string>,<string>)`

`concat(<listString>)`

返回字符串。

## 示例

`concat("Hello","World")`

返回“HelloWorld”。

`concat(["Hello"," ","World"])`

返回“Hello World”。
