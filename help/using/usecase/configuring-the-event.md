---
product: adobe campaign
title: 配置事件
description: 了解如何为历程简单用例配置事件
feature: Journeys
role: User
level: Intermediate
exl-id: 7423f4eb-005d-43a5-a403-97bee1e8d480
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 10%

---

# 配置事件{#concept_y44_hcy_w2b}

在我们的方案中，每当有人靠近位于spa旁边的信标时，我们都需要接收一个事件。 此 **技术用户** 需要配置系统将在我们的历程中侦听的事件。

有关事件配置的其他信息，请参阅 [此页面](../event/about-events.md).

1. 在顶部菜单中，单击 **[!UICONTROL Events]** 选项卡，然后单击 **[!UICONTROL Add]** 以创建新事件。

   ![](../assets/journeyuc1_1.png)

1. 我们输入名称，但不包括空格或特殊字符：“SpaBeacon”。

   ![](../assets/journeyuc1_2.png)

1. 然后，我们选择架构并定义此事件所需的有效负载。 我们从XDM标准化模型中选择所需的字段。 我们需要在Real-time Customer Profile数据库中识别人员的Experience CloudID： _endUserIDs > experience > mcid > id_. 系统会自动为此事件生成ID。 此ID存储在 **[!UICONTROL eventID]** 字段(_experience > campaign > orchestration > eventID_)。 推送事件的系统不应生成ID，它应使用有效负载预览中可用的ID。 在我们的用例中，此ID用于标识信标位置。 每次有人接近spa信标时，都将发送一个包含此特定事件ID的事件。 这允许系统知道哪些信标触发了事件发送。

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >字段列表因架构而异。 根据架构定义，某些字段可能是必填字段，并且已预先选择。

1. 我们需要选择命名空间。根据模式属性预先选择命名空间。您可以使命名空间保持处于预选状态。有关命名空间的更多信息，请参阅[此页面](../event/selecting-the-namespace.md)。

   ![](../assets/journeyuc1_6.png)

1. 根据模式属性和选定的命名空间预先选择密钥。 你可以留着它。

   ![](../assets/journeyuc1_5.png)

1. 单击 **[!UICONTROL Save]**。

1. 单击 **[!UICONTROL View Payload]** 图标以预览系统所需的有效负载，并将其与负责事件发送的人共享。 此有效负载需要在Mobile Services管理控制台的回发中进行配置。

   ![](../assets/journeyuc1_7.png)

   该事件已准备好在您的历程中使用。 您现在需要配置移动应用程序，以便能够将预期的有效负载发送到流摄取API端点。 请参阅[此页](../event/additional-steps-to-send-events-to-journey-orchestration.md)。
