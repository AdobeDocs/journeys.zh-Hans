---
product: adobe campaign
title: serializeList
description: 了解函数serializeList
feature: Journeys
role: Developer
level: Experienced
exl-id: 84912d38-32ee-4cfe-8cb4-bad12f9c52af
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 22%
---
# serializeList {#serializeList}

将第一个参数中给定的列表（任何类型）转换为字符串。 第二个参数表示要使用的分隔符。 第三个参数是一个布尔值，指示表达式的每个元素是否应包含引号。

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
| 列表 | listDateOnly |

## 签名和返回的类型

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDateOnly>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

`serializeList(<listPoint>,<string>,<boolean>)`

返回字符串。

## 示例

`serializeList(["Hello","World"], " ", false)`

返回“Hello World”。

`serializeList(["Hello", "World"], ",", true)`

返回“Hello”、“World”。
