---
product: adobe campaign
title: concat
description: 了解函数连接
feature: Journeys
role: Developer
level: Experienced
exl-id: 7a516705-2bbe-4b42-97fc-aeae11082002
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
source-wordcount: '40'
ht-degree: 27%
---
# concat {#concat}

连接两个字符串参数或一个字符串列表。

## 类别

字符串

## 函数语法

`concat(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 列表 | listString |
| 字符串 | 字符串 |

## 签名和返回的类型

`concat(<string>,<string>)`

`concat(<listString>)`

返回字符串。

## 示例

`concat("Hello","World")`

返回“HelloWorld”。

`concat(["Hello"," ","World"])`

返回“Hello World”。
