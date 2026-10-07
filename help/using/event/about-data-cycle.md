---
product: adobe campaign
title: 事件数据周期
description: 了解事件数据周期
feature: Journeys
role: User
level: Intermediate
exl-id: b362589a-32b0-4dbd-8ceb-a371e1e048ac
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 79%
---
# 数据周期 {#section_r1f_xqt_pgb}

事件是 POST API 调用。 事件通过流式引入 API 发送到 Adobe Experience Platform。 通过事务性消息传送 API 发送的事件的 URL 目标称为“入口”。 事件的有效负载遵循 XDM 格式。

有效负载包含流式引入 API 工作所需的信息（在标题中）和 [!DNL Journey Orchestration] 工作所需的信息（事件 ID，有效负载主体的一部分）以及要在旅程中使用的信息（在主体中，例如放弃购物车的数量）。 流摄取有两种模式，即经过身份验证和未经身份验证。 有关流式引入 API 的详细信息，请参阅[此链接](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=zh-Hans)。

事件通过流式摄取 API 到达后，会流入称为“管道”的内部服务，然后流入 Adobe Experience Platform。 如果事件架构启用了实时客户轮廓服务标志，并且数据集 ID 也具有实时客户轮廓标志，则会流入实时客户轮廓服务。

对于系统生成的事件，Pipeline会筛选有效负载由[!DNL Journey Orchestration]提供并包含在事件有效负载中的事件，这些有效负载包含[!DNL Journey Orchestration]个事件ID（请参阅下面的事件创建流程）。 对于基于规则的事件，系统会使用eventID条件标识事件。 这些事件通过 [!DNL Journey Orchestration] 侦听，并触发相应的旅程。
