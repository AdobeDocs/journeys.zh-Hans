---
product: adobe campaign
title: 关于自定义操作配置
description: Learn how to configure a custom action
feature: Journeys
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 7ce4ddec60f62662d67351b8ca70d7763e76b977
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 15%

---

# 关于自定义操作配置 {#concept_sxy_bzs_dgb}

如果您使用第三方系统来发送消息，或者 [!DNL Journey Orchestration] 要向第三方系统发送API调用，您可以在此配置其与 [!DNL Journey Orchestration]. The custom action defined by technical users will then be available in the left palette of your journey, in the **[!UICONTROL Action]** category (see [this page](../building-journeys/about-action-activities.md). 以下是可通过自定义操作连接到的一些系统示例：Epsilon、Facebook、Adobe.io、Firebase等
Limitations are listed in [this page](../about/limitations.md).

以下是配置自定义操作所需的主要步骤：

1. From the **[!UICONTROL Actions]** list, click **[!UICONTROL Add]** to create a new action. 操作配置窗格将在屏幕右侧打开。

   ![](../assets/custom2.png)

1. 输入操作的名称。

   >[!NOTE]
   >
   >请勿使用空格或特殊字符。请勿使用超过 30 个字符。

1. Add a description to your action. 此步骤是可选的。
1. 使用此操作的历程数显示在 **[!UICONTROL Used in]** 字段。 You can click the **[!UICONTROL View journeys]** button to display the list of  journeys using this action.
1. 定义不同的 **[!UICONTROL URL Configuration]** 参数。 请参阅[此页](../action/url-configuration.md)。
1. 配置 **[!UICONTROL Authentication]** 中。 此配置与数据源的配置相同。  请参阅[此小节](../datasource/external-data-sources.md#section_wjp_nl5_nhb)。
1. 定义 **[!UICONTROL Action parameters]**. 请参阅[此页](../action/defining-the-message-parameters.md)。
1. 单击 **[!UICONTROL Save]**。

   自定义操作现已配置完成，可随时用于您的历程。 请参阅[此页](../building-journeys/about-action-activities.md)。

   >[!NOTE]
   >
   >在历程中使用自定义操作时，大多数参数都是只读的。 您只能修改 **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** 字段和 **[!UICONTROL Authentication]** 中。
