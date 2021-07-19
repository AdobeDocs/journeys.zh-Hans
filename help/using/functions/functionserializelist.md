---
product: adobe campaign
title: serializeList
description: 了解函数serializeList
feature: 历程
role: Data Engineer
level: Experienced
exl-id: 84912d38-32ee-4cfe-8cb4-bad12f9c52af
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 20%

---

# serializeList {#serializeList}

将第一个参数中给定的列表（任何类型）转换为字符串。 第二个参数表示要使用的分隔符。 第三个参数是一个布尔值，用于指示表达式的每个元素是否应包含引号。

## 类别

列表

## 函数语法

`serializeList(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 字符串 | 字符串 |
| 布尔值 | 布尔值 |
| DateTimeOnly | DateTimeOnly |
| 列表 | listString |
| 列表 | listBoolean |
| 列表 | listPoint |
| 列表 | listDecimal |
| 列表 | listDuration |
| 列表 | listDateTime |
| 列表 | listDateTimeOnly |

## 签名和返回的类型

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
