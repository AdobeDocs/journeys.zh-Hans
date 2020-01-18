---
title: 配置活动
description: 了解如何为旅程简单用例配置活动
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# 配置活动{#concept_y44_hcy_w2b}

在我们的场景中，每当一个人在位于Spa旁的信标附近走动时，我们都需要收到一个活动。 技 **术用户需要配置** ，系统将在我们的旅程中侦听的事件。

有关活动配置的其他信息，请参阅 [](../event/about-events.md)。

1. 在顶部菜单中，单击选 **[!UICONTROL Events]**项卡并单**[!UICONTROL Add]** 击以创建新活动。

   ![](../assets/journeyuc1_1.png)

1. 我们输入名称时不带空格或特殊字符：“SpaBeacon”。

   ![](../assets/journeyuc1_2.png)

   <!--li>Select the **[!UICONTROL Mobile - Streaming Ingestion APIs]** event type. Events are sent from the customers' mobile phone through the Mobile SDK.![](../assets/journeyuc1_4.png" placement="break" width="800" id="image_qgr_2mn_z2b"/></li-->

1. 然后，我们选择架构并定义此事件预期的有效负荷。 从XDM标准化模型中选取所需字段。 我们需要Experience Cloud ID来识别实时客户档案数据库中的人员： _endUserID > experience > mcid > id_。 此活动会自动生成ID。 此ID存储在字段中( **[!UICONTROL eventID]**体&#x200B;_验>营销活动>安排> eventID_)。 推送事件的系统不应生成ID，它应使用有效负荷预览中可用的ID。 在我们的用例中，此ID用于标识信标位置。 每当某人在spa信标附近行走时，将发送包含此特定事件ID的活动。 这使系统能够了解触发事件发送的信标。

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >字段列表因架构而异。 根据架构定义，某些字段可能是必填的并且是预先选择的。

1. 我们需要选择一个命名空间。 将根据架构属性预先选择命名空间。 您可以保持预选。 有关命名空间的详细信息，请参 [](../event/selecting-the-namespace.md)阅。

   ![](../assets/journeyuc1_6.png)

1. 根据架构属性和选定的命名空间预选键。 你可以留着它。

   ![](../assets/journeyuc1_5.png)

1. 单击 **[!UICONTROL Save]**.

1. 单击该 **[!UICONTROL View Payload]**图标可预览系统预期的有效负荷，并将其共享给负责事件发送的人员。 此负载需要在Mobile services管理控制台的回传中配置。

   ![](../assets/journeyuc1_7.png)

   该活动已准备好用于您的旅程。 您现在需要配置移动应用程序，以便它能够将期望的有效负荷发送到流摄取API端点。 请参见 [](../event/additional-steps-to-send-events-to-journey-orchestration.md)。