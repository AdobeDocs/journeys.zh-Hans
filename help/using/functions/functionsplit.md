---
product: adobe campaign
title: split
description: 了解函数拆分
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 44499a09-19e2-4085-bf2f-7d9080ec382d
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '65'
ht-degree: 15%

---

# split {#split}

使用分隔符字符串（第二个参数字符串，可以是正则表达式）拆分第一个参数字符串以生成字符串（令牌）列表。

## 类别

字符串

## 函数语法

`split(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 输入字符串 | 字符串 |
| 分隔符字符串 | 字符串 |

## 签名和返回的类型

`split(<input string>, <separator string>)`

返回listString。

## 示例

`split(["A_B_C"], "_")`

返回`["A","B","C"]`

具有事件字段“event.appVersion”且值为“20.45.2.3434”的示例

`split(@{event.appVersion}, "\\.")`

返回`["20", "45", "2", "3434"]`
