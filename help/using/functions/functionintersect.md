---
product: adobe campaign
title: intersect
description: 了解函数相交
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 12%

---

# 相交{#intersect}

返回两个输入列表中的公共值。 如果两个列表之一为空，则返回空列表。

## 类别

列表

## 函数语法

`intersect(<parameters>)`

## 参数

| 参数 | 类型 |
|-----------|------------------|
| 列表1 | 列表 |
| 列表2 | 列表 |

## 签名和返回的类型

`intersect(listString,listString)`:listString
`intersect(listDecimal,listDecimal)`:listDecimal
`intersect(listInteger,listInteger)`:listInteger
`intersect(listDateTime,listDateTime)`:listDateTime
`intersect(listDateTimeOnly,listDateTimeOnly)`:listDateTimeOnly
`intersect(listDateOnly,listDateOnly)`:listDateOnly
`intersect(listDuration,listDuration)`:listDuration
`intersect(listBoolean,listBoolean)`:listBoolean

返回列表。

## 示例

```json
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

返回结果 [&quot;sports&quot;、&quot;news&quot;]

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

返回用户档案属性和给定事件字段之间的常用项目。
