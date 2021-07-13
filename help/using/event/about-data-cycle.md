---
product: adobe campaign
title: 事件数据周期
description: 了解事件数据周期
feature: 历程
role: User
level: Intermediate
exl-id: b362589a-32b0-4dbd-8ceb-a371e1e048ac
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 79%

---

# 数据周期 {#section_r1f_xqt_pgb}

事件是 POST API 调用。事件通过流式引入 API 发送到 Adobe Experience Platform。通过事务性消息传送 API 发送的事件的 URL 目标称为“入口”。事件的有效负载遵循 XDM 格式。

有效负载包含流式引入 API 工作所需的信息（在标题中）和 [!DNL Journey Orchestration] 工作所需的信息（事件 ID，有效负载主体的一部分）以及要在旅程中使用的信息（在主体中，例如放弃购物车的数量）。流式引入有两种模式，即验证和未验证。有关流式引入 API 的详细信息，请参阅[此链接](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=zh-Hans)。

事件通过流式引入 API 到达后，会流入名为 Pipeline 的内部服务，然后流入 Adobe Experience Platform。如果事件架构启用了实时客户资料服务标志，并且数据集 ID 也具有实时客户资料标志，则会流入实时客户资料服务。

对于系统生成的事件，Pipeline过滤器事件的有效负载包含由[!DNL Journey Orchestration]提供并包含在事件有效负载中的[!DNL Journey Orchestration]事件ID（请参阅以下事件创建过程）。 对于基于规则的事件，系统会使用eventID条件来标识该事件。 这些事件通过 [!DNL Journey Orchestration] 侦听，并触发相应的旅程。
