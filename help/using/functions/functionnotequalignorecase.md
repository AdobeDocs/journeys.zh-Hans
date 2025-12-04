---
product: adobe campaign
title: notEqualIgnoreCase
description: 了解函数notEqualIgnoreCase
feature: Journeys
role: Developer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 13%

---

# notEqualIgnoreCase {#notEqualIgnoreCase}

检查第一个参数字符串与第二个参数字符串是否不同，忽略大小写注意事项。

## 类别

字符串

## 函数语法

`notEqualIgnoreCase(<parameters>)`

## 参数

* 字符串

## 签名和返回的类型

`notEqualIgnoreCase(<string>,<string>)`

返回布尔值。

## 示例

`notEqualIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad")`
