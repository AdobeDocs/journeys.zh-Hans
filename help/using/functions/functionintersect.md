---
product: adobe campaign
title: intersect
description: 了解函数intersect
feature: Journeys
role: Developer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 12%

---

# intersect{#intersect}

返回两个输入列表中的公用值。 如果两个列表之一为null，则返回空列表。

## 类别

列表

## 函数语法

`intersect(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 列表1 | list |
| 列表2 | list |

## 签名和返回的类型

`intersect(listString,listString)`：列表字符串
`intersect(listDecimal,listDecimal)`： listDecimal
`intersect(listInteger,listInteger)`： listInteger
`intersect(listDateTime,listDateTime)`： listDateTime
`intersect(listDateTimeOnly,listDateTimeOnly)`： listDateTimeOnly
`intersect(listDateOnly,listDateOnly)`： listDateOnly
`intersect(listDuration,listDuration)`： listDuration
`intersect(listBoolean,listBoolean)`：列表布尔值

返回列表。

## 示例

```json
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

返回[&quot;sports&quot;，&quot;news&quot;]

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

返回配置文件属性和给定类别列表之间的通用项目。

```json
intersect(
    #{ExperienceDataPlatform.profile.interests},
        @{myEvent.sport_interests}
)
```

返回用户档案属性和给定事件字段之间的公用项。
