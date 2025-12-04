---
product: adobe campaign
title: endWith
description: 了解函数endWith
feature: Journeys
role: Developer
level: Experienced
exl-id: 6eee6057-1daf-4b9d-ae94-2b35843e3a49
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 25%

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

## 签名和返回的类型

`endWith(<string>,<string>)`

返回布尔值。

## 示例

`endWith("Hello World", "World")`

返回真。

`endWith("Hello World", "Hello")`

返回假。
