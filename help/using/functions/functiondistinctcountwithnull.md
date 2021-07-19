---
product: adobe campaign
title: distinctCountWithNull
description: 了解distinctCountWithNull函数
feature: 历程
role: Data Engineer
level: Experienced
exl-id: b8380d30-160e-45c2-b187-34eb42845923
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 33%

---

# distinctCountWithNull {#distinctCountWithNull}

计算不同值的数量，包括空值。

## 类别

聚合

## 函数语法

`distinctCountWithNull(<listAny>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 列表 | listString |
| 列表 | listBoolean |
| 列表 | listInteger |
| 列表 | listDecimal |
| 列表 | listDuration |
| 列表 | listDateTime |
| 列表 | listDateTimeOnly |

## 签名和返回的类型

`distinctCountwithNull(<listAny>)`

返回整数。

## 示例

`distinctCountWithNull([10,2,10,null])`

返回3。
