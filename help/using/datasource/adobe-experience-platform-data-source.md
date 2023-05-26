---
product: adobe campaign
title: Adobe Experience Platform 数据源
description: 了解如何配置Adobe Experience Platform数据源
feature: Journeys
role: User
level: Intermediate
exl-id: 847fa819-2b92-49e5-8a5e-4f3f0acd5e35
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 14%

---

# Adobe Experience Platform 数据源 {#concept_zrb_nqt_52b}

Adobe Experience Platform数据源定义与Real-time Customer Profile服务的连接。 此数据源是内置的，并且已预配置。 无法删除它。 此数据源旨在检索和使用来自Real-time Customer Profile Service的数据（例如，检查进入历程的人员是否为女性）。 该数据源允许您使用用户档案数据和体验事件数据。有关Real-time Customer Profile服务的详细信息，请参阅此 [页面](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hans).

>[!NOTE]
>
>您可以检索不到一年前创建的1000个最新体验事件。

要允许与Real-time Customer Profile Service的连接，我们必须使用键来标识人员，并使用命名空间来将键上下文化。 因此，仅当历程以包含键和命名空间的事件开始时，才能使用此数据源。 请参阅[此页](../building-journeys/journey.md)。

您可以编辑名为“ProfileFieldGroup”的预配置字段组、添加新字段组并删除未在任何草稿或实时历程中使用的字段组。 请参阅[此页](../datasource/field-groups.md)。

以下是向内置数据源添加字段组的主要步骤。

1. 从数据源列表中，选择内置的Adobe Experience Platform数据源。

   这将打开屏幕右侧的数据源配置窗格。

   ![](../assets/journey23.png)

1. 单击 **[!UICONTROL Add a New Field Group]** 以定义要检索的一系列新字段。 请参阅[此页](../datasource/field-groups.md)。

   ![](../assets/journey24.png)

1. 从中选择架构 **[!UICONTROL Schema]** 下拉菜单。 此字段列出Adobe Experience Platform中可用的配置文件和Experience Events架构。 架构创建不执行于 [!DNL Journey Orchestration]. 它在Adobe Experience Platform中执行。
1. 选择要使用的字段。
1. 单击&#x200B;**[!UICONTROL Save]**。

将光标放在字段组的名称上时，您会在右侧看到两个图标。 它们允许您删除和复制字段组。 请注意 **[!UICONTROL Delete]** 图标仅在字段组未在任何实时或草稿历程中使用时可用(信息显示在 **[!UICONTROL Used in]** 字段)。
