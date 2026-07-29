---
product: adobe campaign
title: journeyStep 事件身份标识字段
description: journeyStep 事件身份标识字段
feature: Journeys
role: User
level: Intermediate
exl-id: 9c0ff38f-51dd-40bd-8c19-d142b9c23308
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 58%

---

# journeyStep 事件身份标识字段 {#sharing-identity-fields}


>[!CAUTION]
>
>**希望了解 Adobe Journey Optimizer**？ 请单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取 Journey Optimizer 文档。
>
>
>_本文档参考已被 Journey Optimizer 取代的旧版 Journey Orchestration 资料。 如果您对访问 Journey Orchestration 或 Journey Optimizer 有任何疑问，请联系帐户团队。_


此mixin特定于journeyStepEvent：此事件与历程相关，不具有identityMap，因此不能描述配置文件身份（如果有）。

对于journeyStepEvent，我们还需要添加与标识相关的字段：

## profileId

配置文件标识符

类型：字符串

## profileName

配置文件标识符命名空间

类型：字符串
