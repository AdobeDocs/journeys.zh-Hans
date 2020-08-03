---
title: toTimeZone
description: 了解toTimeZone的函数
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
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 5%

---


# toTimeZone {#toTimeZone}

将字符串值转换为时区。

## 类别

转换

## 函数语法

`toTimeZone(<parameter>)`

## 参数

| 参数 | 说明 |
|--- |--- |
| 字符串 | 字符串值必须包含区域ID。 它可以是字段引用或表达式 |

## 签名和返回类型

`toTimeZone(<string>)`

返回时区。

## 示例

`toTimeZone("UTC")`

返回UTC。
