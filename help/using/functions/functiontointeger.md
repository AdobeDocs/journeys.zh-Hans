---
title: toInteger
description: 了解函数toInteger
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 7%

---


# toInteger {#toInteger}

将参数值转换为整数。

## 类别

转换

## 函数语法

`toInteger(<parameter>)`

## 参数

| 参数 | 说明 |
|--- |--- |
| 字符串 | 将字符串值转换为整数 |
| dateTime | 将日期转换为毫秒数（纪元毫秒） |
| 小数 | 通过删除小数部分转换为整数(示例：1.5变为1) |
| 布尔 | 如果为true，则将布尔值转换为1；如果为false，则将布尔值转换为0 |

## 签名和返回类型

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

返回整数。

## 示例

`toInteger(4)`

返回4。
