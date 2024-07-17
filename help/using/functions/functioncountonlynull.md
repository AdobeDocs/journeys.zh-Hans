---
product: adobe campaign
title: countOnlyNull
description: 了解函数countOnlyNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: e6170a21-0418-4311-a43b-fd4f323cd020
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 32%

---

# countOnlyNull {#countOnlyNull}

计算列表中的空值的数量。

## 类别

聚合

## 函数语法

`countOnlyNull(<listAny>)`

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
| 列表 | listDateOnly |

## 签名和返回的类型

`countOnlyNull(<listAny>)`

返回整数。

## 示例

`countOnlyNull([10,2,10,null])`

返回1。
