---
product: adobe campaign
title: filter
description: Learn about the function filter
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 10%

---

# filter{#filter}

Returns a listObject with objects having the key attribute matching one of the given key values.

## 类别

列表

## 函数语法

`filter(<parameters>)`

## 参数

| 参数 | 类型 | 描述 |
|-----------|------------------|------------------|
| listToFilter | listObject | 要过滤的对象列表。 它必须是字段引用。 |
| keyAttributeName | 字符串 | 给定列表对象中的属性名称，用作筛选的键 |
| keyValueList | list | 用于筛选的键值数组 |

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

以下是传入事件“myevent”中传递的有效负载示例：

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

Returns a listObject containing the two objects with &quot;product2&quot; and &quot;product3&quot; as id.
