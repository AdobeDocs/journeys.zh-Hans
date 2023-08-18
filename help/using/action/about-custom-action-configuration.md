---
product: adobe campaign
title: 关于自定义操作配置
description: 了解如何配置自定义操作
feature: Journeys
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 7ad2419854b4fcecae7fbb20bdd6a6f2fbc04988
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 12%

---

# 关于自定义操作配置 {#concept_sxy_bzs_dgb}

如果您使用第三方系统来发送消息，或者您需要 [!DNL Journey Orchestration] 要将API调用发送到第三方系统，您可以在此处配置其与 [!DNL Journey Orchestration]. 随后，技术用户定义的自定义操作将位于历程的左侧面板的 **[!UICONTROL Action]** 类别(请参阅 [此页面](../building-journeys/about-action-activities.md). 以下是一些可通过自定义操作连接到的系统示例：Epsilon、Facebook、Adobe.io、Firebase等。

中列出了限制 [此页面](../about/limitations.md).

在自定义操作参数中，您可以传递简单的集合以及对象集合。 有关限制，请参阅 [此页面](../usecase/collections.md#limitations). 另请注意，参数具有预期格式（例如：字符串、小数等）。 必须注意遵守这些预期格式。 请参阅此 [用例](../usecase/collections.md).

以下是配置自定义操作所需的主要步骤：

1. 从 **[!UICONTROL Actions]** 列表，单击 **[!UICONTROL Add]** 以创建新操作。 操作配置窗格将在屏幕右侧打开。

   ![](../assets/custom2.png)

1. 输入操作的名称。

   >[!NOTE]
   >
   >请勿使用空格或特殊字符。请勿使用超过 30 个字符。

1. 向操作添加描述。 此步骤是可选的。
1. 使用此操作的旅程数显示在 **[!UICONTROL Used in]** 字段。 您可以单击 **[!UICONTROL View journeys]** 按钮以显示使用此操作的历程列表。
1. 定义不同的 **[!UICONTROL URL Configuration]** 参数。 请参阅[此页](../action/url-configuration.md)。
1. 配置 **[!UICONTROL Authentication]** 部分。 此配置与数据源的配置相同。  请参阅[此章节](../datasource/external-data-sources.md#section_wjp_nl5_nhb)。
1. 定义 **[!UICONTROL Action parameters]**. 请参阅[此页](../action/defining-the-message-parameters.md)。
1. 单击 **[!UICONTROL Save]**。

   自定义操作现已配置完毕，可随时用于您的历程。 请参阅[此页](../building-journeys/about-action-activities.md)。

   >[!NOTE]
   >
   >在历程中使用自定义操作时，大多数参数均为只读。 您只能修改 **[!UICONTROL Name]**， **[!UICONTROL Description]**， **[!UICONTROL URL]** 字段和 **[!UICONTROL Authentication]** 部分。
