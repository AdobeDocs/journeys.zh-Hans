---
title: notEqualWithIgnoreCase
description: 了解函数notEqualWithIgnoreCase
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
source-wordcount: '37'
ht-degree: 10%

---


# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

检查带有第二个参数字符串的第一个参数字符串是否不同，忽略大小写注意事项。

## 类别

字符串

## 函数语法

`notEqualWithIgnoreCase(<parameters>)`

## 参数

* 字符串

## 签名和返回类型

`notEqualWithIgnoreCase(<string>,<string>)`

返回布尔值。

## 示例

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
