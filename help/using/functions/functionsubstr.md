---
title: substr
description: 了解函数子字符串
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 6%

---


# substr {#substr}

返回开始索引和结束索引之间的字符串表达式的子字符串。 如果未定义结束索引，则它介于开始索引和结束索引之间。

## 类别

字符串

## 函数语法

`substr(<parameters>)`

## 参数

| 参数 | 类型 |
|-------------|----------|
| 字符串 | 字符串 |
| beginIndex | 整数 |
| endIndex | 整数 |

## 签名和返回类型

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

返回字符串。

## 示例

`substr("Hello World",6)`

返回“世界”。

`substr("Hello World", 0, 5)`

返回“Hello”。