---
product: adobe campaign
title: 关于自定义操作配置
description: 了解如何配置自定义操作
feature: Journeys
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 11%

---

# 关于自定义操作配置 {#concept_sxy_bzs_dgb}


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_


如果您使用第三方系统发送消息，或者您希望[!DNL Journey Orchestration]向第三方系统发送API调用，则可以在此处配置其与[!DNL Journey Orchestration]的连接。 技术用户定义的自定义操作随后将显示在历程左侧面板的&#x200B;**[!UICONTROL Action]**&#x200B;类别中（请参阅[此页面](../building-journeys/about-action-activities.md)）。 以下是一些可通过自定义操作连接到的系统示例：Epsilon、Facebook、Adobe.io、Firebase等。

[此页面](../about/limitations.md)列出了限制。

在自定义操作参数中，您可以传递简单的集合以及对象集合。 有关限制，请参阅[此页面](../usecase/collections.md#limitations)。 另请注意，参数具有预期格式（例如：字符串、小数等）。 必须注意遵守这些预期格式。 请参阅此[用例](../usecase/collections.md)。

以下是配置自定义操作所需的主要步骤：

1. 从&#x200B;**[!UICONTROL Actions]**&#x200B;列表中，单击&#x200B;**[!UICONTROL Add]**&#x200B;以创建新操作。 操作配置窗格将在屏幕右侧打开。

   ![](../assets/custom2.png)

1. 输入操作的名称。

   >[!NOTE]
   >
   >请勿使用空格或特殊字符。请勿使用超过 30 个字符。

1. 向操作添加描述。 此步骤是可选的。
1. 使用此操作的历程数显示在&#x200B;**[!UICONTROL Used in]**&#x200B;字段中。 您可以单击&#x200B;**[!UICONTROL View journeys]**&#x200B;按钮以显示使用此操作的历程列表。
1. 定义不同的&#x200B;**[!UICONTROL URL Configuration]**&#x200B;参数。 请参阅[此页](../action/url-configuration.md)。
1. 配置&#x200B;**[!UICONTROL Authentication]**&#x200B;部分。 此配置与数据源的配置相同。  请参阅[此小节](../datasource/external-data-sources.md#section_wjp_nl5_nhb)。
1. 定义&#x200B;**[!UICONTROL Action parameters]**。 请参阅[此页](../action/defining-the-message-parameters.md)。
1. 单击 **[!UICONTROL Save]**。

   自定义操作现已配置完毕，可随时用于您的历程。 请参阅[此页](../building-journeys/about-action-activities.md)。

   >[!NOTE]
   >
   >在历程中使用自定义操作时，大多数参数均为只读。 您只能修改&#x200B;**[!UICONTROL Name]**、**[!UICONTROL Description]**、**[!UICONTROL URL]**&#x200B;字段和&#x200B;**[!UICONTROL Authentication]**&#x200B;部分。
