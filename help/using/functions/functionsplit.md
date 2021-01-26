---
product: adobe campaign
solution: Journey Orchestration
title: 拆分
description: 了解函数拆分
translation-type: tm+mt
source-git-commit: 135485c097f99483c2ddb3d03e0552f9ac134b44
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 4%

---


# 拆分{#split}

用分隔符字符串(第二个参数字符串，可以是常规表达式)拆分第一个参数字符串，以生成字符串列表（令牌）。

## 类别

字符串

## 函数语法

`split(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 输入字符串 | 字符串 |
| 分隔线 | 字符串 |

## 签名和返回类型

`split(<input string>, <separator string>)`

返回listString。

## 示例

`split(["A_B_C"], "_")`

返回`["A","B","C"]`

事件字段为“事件.appVersion”且值为：&quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

返回`["20", "45", "2", "3434"]`
