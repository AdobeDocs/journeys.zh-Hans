---
product: adobe campaign
title: Adobe Experience Platform 数据源
description: 了解如何配置Adobe Experience Platform数据源
feature: Journeys
role: User
level: Intermediate
exl-id: 847fa819-2b92-49e5-8a5e-4f3f0acd5e35
product_v2:
  - id: cf67d108-ecf9-4fde-af49-3a3c39083bc8
    internal-label: Journey Orchestration
feature_v2:
  - id: 7de3230f-9523-5ba5-8d5c-2313288b27ef
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: 255cd6677e7c9ebff63ea9a1028a042c19e63ecc
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 25%
---
# Adobe Experience Platform 数据源 {#concept_zrb_nqt_52b}


>[!CAUTION]
>
>**希望了解 Adobe Journey Optimizer**？ 请单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取 Journey Optimizer 文档。
>
>
>_本文档参考已被 Journey Optimizer 取代的旧版 Journey Orchestration 资料。 如果您对访问 Journey Orchestration 或 Journey Optimizer 有任何疑问，请联系帐户团队。_


Adobe Experience Platform数据源定义与实时客户资料服务的连接。 此数据源是内置且预配置的。 无法删除它。 此数据源旨在检索和使用来自Real-time Customer Profile Service的数据（例如，检查进入历程的人员是否为女性）。 该数据源允许您使用轮廓数据和体验事件数据。 有关Real-time Customer Profile Service的详细信息，请参阅此[页](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hans)。

>[!NOTE]
>
>您可以检索在不到一年前创建的1000个最新体验事件。

要允许与Real-time Customer Profile Service的连接，我们必须使用键来识别人员，并使用命名空间来将键进行上下文化。 因此，仅当历程以包含键和命名空间的事件开始时，才能使用此数据源。 请参阅[此页](../building-journeys/journey.md)。

您可以编辑名为“ProfileFieldGroup”的预配置字段组、添加新字段组并删除任何草稿或实时历程中未使用的字段组。 请参阅[此页](../datasource/field-groups.md)。

以下是向内置数据源添加字段组的主要步骤。

1. 从数据源列表中，选择内置的Adobe Experience Platform数据源。

   这将打开屏幕右侧的数据源配置窗格。

   ![](../assets/journey23.png)

1. 单击&#x200B;**[!UICONTROL Add a New Field Group]**&#x200B;可定义要检索的一系列新字段。 请参阅[此页](../datasource/field-groups.md)。

   ![](../assets/journey24.png)

1. 从&#x200B;**[!UICONTROL Schema]**&#x200B;下拉列表中选择架构。 此字段列出Adobe Experience Platform中可用的配置文件和Experience Events架构。 未在[!DNL Journey Orchestration]中执行架构创建。 它在Adobe Experience Platform中执行。
1. 选择要使用的字段。
1. 单击&#x200B;**[!UICONTROL Save]**。

将光标放在字段组的名称上时，您会在右侧看到两个图标。 它们允许您删除和复制字段组。 请注意，仅当字段组未在任何实时或草稿历程中使用（**[!UICONTROL Used in]**&#x200B;字段中显示的信息）时，**[!UICONTROL Delete]**&#x200B;图标才可用。
