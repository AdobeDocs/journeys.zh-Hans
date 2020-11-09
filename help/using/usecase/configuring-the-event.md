---
title: 配置事件
description: 了解如何为旅程简单用例配置事件
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: bcb8a71a27e2b9e37af7d0260cec04ed0fda24ee
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 8%

---


# 配置事件{#concept_y44_hcy_w2b}

在我们的场景中，每当一个人走近Spa旁边的信标时，我们都需要收到事件。 技 **术用户** 需要配置系统在旅程中将监听的事件。

有关事件配置的其他信息，请参 [阅本页](../event/about-events.md)。

1. In the top menu, click the **[!UICONTROL Events]** tab and click **[!UICONTROL Add]** to create a new event.

   ![](../assets/journeyuc1_1.png)

1. 我们输入名称时不加空格或特殊字符：“SpaBeacon”。

   ![](../assets/journeyuc1_2.png)

1. 然后，我们选择模式并定义此事件预期的有效负荷。 从XDM标准化模型中选取所需的字段。 我们需要Experience CloudID来识别实时客户用户档案数据库中的人： _endUserIDs > experience > mcid > id_。 此事件会自动生成ID。 此ID存储在字 **[!UICONTROL eventID]** 段(_体验>活动>业务流程>事件ID_)中。 推送事件的系统不应生成ID，它应使用有效负荷预览中可用的ID。 在我们的用例中，此ID用于标识信标位置。 每次有人在spa信标附近散步时，都会发送包含此特定事件ID的事件。 这使系统能够知道哪个信标触发了事件发送。

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >字段的列表因模式而异。 根据模式定义，某些字段可能是必填字段并且是预选字段。

1. 我们需要选择命名空间。根据模式属性预先选择命名空间。您可以使命名空间保持处于预选状态。For more information on namespaces, see [this page](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc1_6.png)

1. 根据模式属性和选定的命名空间预选键。 你可以留着它。

   ![](../assets/journeyuc1_5.png)

1. 单击 **[!UICONTROL Save]**.

1. 单击该 **[!UICONTROL View Payload]** 图标以预览系统预期的有效负荷，并将其共享给负责事件发送的人员。 此负载需要在Mobile Services管理控制台的回传中配置。

   ![](../assets/journeyuc1_7.png)

   事件随时可用于您的旅程。 现在，您需要配置移动应用程序，以便它能够将期望的有效负荷发送到流摄取API端点。 请参阅[此页](../event/additional-steps-to-send-events-to-journey-orchestration.md)。