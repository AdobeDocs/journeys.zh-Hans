---
title: serializeList
description: 了解函数serializeList
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
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

---


# serializeList {#serializeList}

将第一个参数中给定的列表（任何类型）转换为字符串。 第二个参数表示要使用的分隔符。 第三个参数是一个布尔值，它指示表达式的每个元素是否应包含引号。

## 类别

列表

## 函数语法

`serializeList(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 字符串 | 字符串 |
| Boolean | Boolean |
| DateTimeOnly | DateTimeOnly |
| 列表 | listString |
| 列表 | listBoolean |
| 列表 | listPoint |
| 列表 | listDecimal |
| 列表 | listDuration |
| 列表 | listDateTime |
| 列表 | listDateTimeOnly |

## 签名和返回类型

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

`serializeList(<listPoint>,<string>,<boolean>)`

返回字符串。

## 示例

`serializeList(["Hello","World"], " ", false)`

返回“Hello World”。

`serializeList(["Hello", "World"], ",", true)`

返回“Hello”、“World”。
