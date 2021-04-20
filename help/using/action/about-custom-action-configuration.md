---
product: adobe campaign
solution: Journey Orchestration
title: 关于自定义操作配置
description: 了解如何配置自定义操作
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 15%

---


# 关于自定义操作配置 {#concept_sxy_bzs_dgb}

如果您使用第三方系统发送消息，或希望[!DNL Journey Orchestration]向第三方系统发送API调用，则可在此配置其与[!DNL Journey Orchestration]的连接。 然后，技术用户定义的自定义操作将在您旅程的左侧调色板中的&#x200B;**[!UICONTROL Action]**&#x200B;类别中可用（请参阅[此页面](../building-journeys/about-action-activities.md)）。 以下是可通过自定义操作连接到的一些系统示例：Epsilon、Facebook、Adobe.io、Firebase等
限制列在[此页](../about/limitations.md)中。

以下是配置自定义操作所需的主要步骤：

1. 在&#x200B;**[!UICONTROL Actions]**&#x200B;列表中，单击&#x200B;**[!UICONTROL Add]**&#x200B;以创建新操作。 操作配置窗格将在屏幕右侧打开。

   ![](../assets/custom2.png)

1. 输入操作的名称。

   >[!NOTE]
   >
   >请勿使用空格或特殊字符。请勿使用超过 30 个字符。

1. 为您的操作添加描述。 此步骤是可选的。
1. 使用此操作的旅程数显示在&#x200B;**[!UICONTROL Used in]**&#x200B;字段中。 您可以单击&#x200B;**[!UICONTROL View journeys]**&#x200B;按钮来显示使用此操作的旅程列表。
1. 定义不同的&#x200B;**[!UICONTROL URL Configuration]**&#x200B;参数。 请参阅[此页](../action/url-configuration.md)。
1. 配置&#x200B;**[!UICONTROL Authentication]**&#x200B;部分。 此配置与数据源相同。  请参阅[此章节](../datasource/external-data-sources.md#section_wjp_nl5_nhb)。
1. 定义&#x200B;**[!UICONTROL Message parameters]**。 请参阅[此页](../action/defining-the-message-parameters.md)。
1. 单击 **[!UICONTROL Save]**.

   自定义操作现已配置好并准备在您的旅程中使用。 请参阅[此页](../building-journeys/about-action-activities.md)。

   >[!NOTE]
   >
   >在旅程中使用自定义操作时，大多数参数都是只读的。 只能修改&#x200B;**[!UICONTROL Name]**、**[!UICONTROL Description]**、**[!UICONTROL URL]**&#x200B;字段和&#x200B;**[!UICONTROL Authentication]**&#x200B;部分。
