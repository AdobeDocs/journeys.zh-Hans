---
product: adobe campaign
title: filter
description: 了解函数过滤器
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 3c1c188c-0ffd-44c5-b1b3-1758ed12235e
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 10%

---

# filter{#filter}

返回一个listObject，其中的对象具有匹配给定键值之一的键属性。

## 类别

列表

## 函数语法

`filter(<parameters>)`

## 参数

| 参数 | 类型 | 描述 |
|-----------|------------------|------------------|
| listToFilter | listObject | 要过滤的对象列表。 它必须是字段引用。 |
| keyAttributeName | 字符串 | 给定列表对象中的属性名称，用作筛选键 |
| keyValueList | list | 用于过滤的键值数组 |

## 签名和返回的类型

`filter(listObject, string, listString)`

`filter(listObject, string, listInteger)`

`filter(listObject, string, listDecimal)`

`filter(listObject, string, listDateTime)`

`filter(listObject, string, listDateTimeOnly)`

`filter(listObject, string, listDateOnly)`

`filter(listObject, string, listDuration)`

`filter(listObject, string, listBoolean)`

返回listObject。

## 示例

以下是在传入事件“myevent”中传递的有效负载示例：

```json
"productListItems": [{
   "id": "product1",
   "name": "the product 1",
   "price": 20
},{
   "id": "product2",
   "name": "the product 2",
   "price": 30
},{
   "id": "product3",
   "name": "the product 3",
   "price": 50
}]
```

您可以使用以下表达式：

```json
filter(
 @{myevent.productListItems},
 "id", 
 ["product2", "product3", "product4"]
)
```

返回包含两个对象的listObject，其中“product2”和“product3”作为ID。
