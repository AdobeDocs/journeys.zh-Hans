---
product: adobe campaign
title: 配置事件
description: 了解如何为历程简单用例配置事件
feature: 历程
role: User
level: Intermediate
exl-id: 7423f4eb-005d-43a5-a403-97bee1e8d480
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 10%

---

# 配置事件{#concept_y44_hcy_w2b}

在我们的情景中，每当某人在位于SPA旁边的信标附近走动时，我们都需要接收一个事件。 **技术用户**&#x200B;需要配置系统将在我们的历程中侦听的事件。

有关事件配置的其他信息，请参阅[此页面](../event/about-events.md)。

1. 在顶部菜单中，单击&#x200B;**[!UICONTROL Events]**&#x200B;选项卡，然后单击&#x200B;**[!UICONTROL Add]**&#x200B;以创建新事件。

   ![](../assets/journeyuc1_1.png)

1. 我们输入名称时不带空格或特殊字符：&quot;SpaBeacon&quot;。

   ![](../assets/journeyuc1_2.png)

1. 然后，我们选择架构并定义此事件所需的有效负载。 我们从XDM标准化模型中选择所需的字段。 我们需要Experience CloudID来识别实时客户资料数据库中的人员：_endUserIDs > experience > mcid > id_。 将自动为此事件生成ID。 此ID存储在&#x200B;**[!UICONTROL eventID]**&#x200B;字段(_experience > campaign > orchestration > eventID_)中。 推送事件的系统不应生成ID，它应使用有效负荷预览中提供的ID。 在我们的用例中，此ID用于标识信标位置。 每次人员在Spa信标附近走动时，都会发送一个包含此特定事件ID的事件。 这允许系统知道哪些信标触发了事件发送。

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >字段列表因架构而异。 根据架构定义，某些字段可能是必填的，并且是预选的。

1. 我们需要选择命名空间。根据模式属性预先选择命名空间。您可以使命名空间保持处于预选状态。有关命名空间的更多信息，请参阅[此页面](../event/selecting-the-namespace.md)。

   ![](../assets/journeyuc1_6.png)

1. 根据模式属性和选择的命名空间预先选择键。 你可以留着它。

   ![](../assets/journeyuc1_5.png)

1. 单击 **[!UICONTROL Save]**。

1. 单击&#x200B;**[!UICONTROL View Payload]**&#x200B;图标可预览系统预期的有效负载，并将其共享给负责事件发送的人员。 需要在Mobile Services管理控制台的回发中配置此负载。

   ![](../assets/journeyuc1_7.png)

   事件已准备好用在您的历程中。 现在，您需要配置移动应用程序，以便它可以将预期的有效负载发送到流摄取API端点。 请参阅[此页](../event/additional-steps-to-send-events-to-journey-orchestration.md)。
