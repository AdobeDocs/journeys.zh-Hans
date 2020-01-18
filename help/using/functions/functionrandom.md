---
title: 随机
description: 了解函数随机性
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

---


# 随机 {#random}

生成0到1之间的随机数。

## 类别

数学

## 函数语法

`random(<parameters>)`

## 签名和返回类型

`random()`

返回小数点。

## 示例

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

说明：如果成功率没有值／为null，则将应用默认值，并将是介于0和1 * 100（即0到100）之间的随机数。
