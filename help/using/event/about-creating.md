---
product: adobe campaign
title: 创建事件
description: 了解如何创建事件
feature: Journeys
role: User
level: Intermediate
exl-id: 2ae8854a-c3e7-469d-9f89-25b54bc3e894
source-git-commit: bdc9ac3f54fae1dfd6f24a54a2687a0834f69c36
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 58%

---

# 创建新事件 {#section_tbk_5qt_pgb}

以下是配置新事件的主要步骤：

1. 在顶部菜单中，单击&#x200B;**[!UICONTROL Events]**&#x200B;选项卡。将显示事件列表。请参阅 [此页面](../about/user-interface.md) 以了解有关该界面的详细信息。

   ![](../assets/journey5.png)

1. 单击&#x200B;**[!UICONTROL Add]**&#x200B;以创建新事件。事件配置窗格将在屏幕右侧打开。输入事件的名称。您还可以添加描述。

   ![](../assets/journey6.png)

   >[!NOTE]
   >
   >请勿使用空格或特殊字符。请勿使用超过 30 个字符。

1. 在 **[!UICONTROL Event ID type]** 字段中，选择要使用的事件类型。

   ![](../assets/journey6bis.png)

   * **基于规则**&#x200B;的事件：此类型的事件不生成 eventID。在 **事件ID条件** 字段中，您只需定义一个规则，系统将使用该规则来识别将触发历程的相关事件。 此规则可以基于事件有效负荷中可用的任何字段，例如用户档案的位置或添加到用户档案购物车的项目数。

   * **系统生成** events：此类型需要eventID。 创建事件时会自动生成此eventID字段，并将其添加到有效负载预览。 推送事件的系统不应生成 ID，它应传递有效负荷预览中可用的 ID。请参阅[此章节](../event/previewing-the-payload.md)。

   >[!NOTE]
   >
   >有关事件类型的更多信息，请参阅 [本节](../event/about-events.md).
1. 使用此事件的旅程数显示在&#x200B;**[!UICONTROL Used in]**&#x200B;字段中。您可以单击 **[!UICONTROL View journeys]**&#x200B;图标，以显示使用此事件的旅程列表。
1. 定义架构和有效负载字段：在这里，您可以选择 [!DNL Journey Orchestration] 预期接收的事件信息（通常称为有效负载）。然后，您便能够在旅程中使用这些信息。请参阅[此页](../event/defining-the-payload-fields.md)。
   >[!NOTE]
   >
   >当您选择 **[!UICONTROL System Generated]** 类型，则只有具有eventID类型mixin的架构可用。 当您选择 **[!UICONTROL Rule Based]** 类型，则所有体验事件架构都可用。

1. 对于基于规则的事件，请单击 **[!UICONTROL Event ID condition]** 字段。 使用简单表达式编辑器，定义系统将使用的条件，以识别将触发历程的事件。
   ![](../assets/alpha-event6.png)

   在我们的示例中，我们根据用户档案所在的城市编写了条件。 这意味着每当系统收到与此条件(**[!UICONTROL City]** 字段和 **[!UICONTROL Paris]** 值)，则会将其传递给Journey Orchestration。

   >[!NOTE]
   >
   >定义时，高级表达式编辑器不可用 **[!UICONTROL Event ID condition]**. 在简单表达式编辑器中，并非所有运算符都可用，它们取决于数据类型。 例如，对于字符串类型的字段，可以使用“包含”或“等于”。

1. 添加命名空间。此步骤是可选的，但还是建议您添加命名空间，以便您利用实时客户资料服务中存储的信息。它定义事件具有的键类型。请参阅[此页](../event/selecting-the-namespace.md)。
1. 定义键：从有效负载字段中选择一个字段或定义一个公式以标识与事件关联的个人。如果您选择命名空间，此键将自动设置（但仍可编辑）。事实上，[!DNL Journey Orchestration] 会选取应与命名空间对应的键（例如，如果您选择了电子邮件命名空间，则会自动选择电子邮件键）。请参阅[此页](../event/defining-the-event-key.md)。
1. 单击 **[!UICONTROL Save]**。

   ![](../assets/journey7.png)

   事件现已配置完毕，可随时投入旅程。还需要其他配置步骤以接收事件。请参阅[此页](../event/additional-steps-to-send-events-to-journey-orchestration.md)。
