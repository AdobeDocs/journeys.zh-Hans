---
product: adobe campaign
title: 关于自定义操作配置
description: 了解如何配置自定义操作
feature: 历程
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 15%

---

# 关于自定义操作配置 {#concept_sxy_bzs_dgb}

如果您使用第三方系统来发送消息，或者如果您希望[!DNL Journey Orchestration]向第三方系统发送API调用，则可以在此配置其与[!DNL Journey Orchestration]的连接。 然后，技术用户定义的自定义操作将在历程左侧面板的&#x200B;**[!UICONTROL Action]**&#x200B;类别中可用（请参阅[此页面](../building-journeys/about-action-activities.md)）。 以下是可通过自定义操作连接到的一些系统示例：Epsilon、Facebook、Adobe.io、Firebase等
[此页面](../about/limitations.md)中列出了限制。

以下是配置自定义操作所需的主要步骤：

1. 在&#x200B;**[!UICONTROL Actions]**&#x200B;列表中，单击&#x200B;**[!UICONTROL Add]**&#x200B;以创建新操作。 操作配置窗格将在屏幕右侧打开。

   ![](../assets/custom2.png)

1. 输入操作的名称。

   >[!NOTE]
   >
   >请勿使用空格或特殊字符。请勿使用超过 30 个字符。

1. 向操作添加描述。 此步骤是可选的。
1. 使用此操作的历程数显示在&#x200B;**[!UICONTROL Used in]**&#x200B;字段中。 您可以单击&#x200B;**[!UICONTROL View journeys]**&#x200B;按钮以显示使用此操作的历程列表。
1. 定义不同的&#x200B;**[!UICONTROL URL Configuration]**&#x200B;参数。 请参阅[此页](../action/url-configuration.md)。
1. 配置&#x200B;**[!UICONTROL Authentication]**&#x200B;部分。 此配置与数据源的配置相同。  请参阅[此小节](../datasource/external-data-sources.md#section_wjp_nl5_nhb)。
1. 定义&#x200B;**[!UICONTROL Message parameters]**。 请参阅[此页](../action/defining-the-message-parameters.md)。
1. 单击 **[!UICONTROL Save]**。

   自定义操作现已配置完成，可随时用于您的历程。 请参阅[此页](../building-journeys/about-action-activities.md)。

   >[!NOTE]
   >
   >在历程中使用自定义操作时，大多数参数都是只读的。 您只能修改&#x200B;**[!UICONTROL Name]**、**[!UICONTROL Description]**、**[!UICONTROL URL]**&#x200B;字段和&#x200B;**[!UICONTROL Authentication]**&#x200B;部分。
