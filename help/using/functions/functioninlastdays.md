---
title: inLastDays
description: 了解LastDays中的函数
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# inLastDays {#inLastDays}

如果给定的日期或dateTime介于现在和现在——增量天数之间，则返回true。

## 类别

日期

## 函数语法

`inLastDays(<dateTime>,<delta>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 日期时间 | dateTime |
| δ | 整数 |

## 签名和返回类型

`inLastDays(<dateTime>,<integer>)`

返回布尔值。

## 示例

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4))`

返回true。
