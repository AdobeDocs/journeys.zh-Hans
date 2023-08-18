---
product: adobe campaign
title: journeyStep 事件身份字段
description: journeyStep 事件身份字段
feature: Journeys
role: User
level: Intermediate
exl-id: 9c0ff38f-51dd-40bd-8c19-d142b9c23308
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 27%

---

# journeyStep 事件身份字段 {#sharing-identity-fields}

此mixin特定于journeyStepEvent：此事件与历程相关，不具有identityMap，因此不能描述配置文件身份（如果有）。

对于journeyStepEvent，我们还需要添加与标识相关的字段：

## profileId

配置文件标识符

类型：字符串

## profileName

配置文件标识符命名空间

类型：字符串
