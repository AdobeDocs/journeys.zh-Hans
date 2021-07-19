---
product: adobe campaign
title: 'Adobe Experience Platform 数据源 '
description: '了解如何配置Adobe Experience Platform数据源 '
feature: 历程
role: User
level: Intermediate
exl-id: 847fa819-2b92-49e5-8a5e-4f3f0acd5e35
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 11%

---

# Adobe Experience Platform 数据源 {#concept_zrb_nqt_52b}

Adobe Experience Platform数据源定义与实时客户资料服务的连接。 此数据源已内置并预配置。 无法删除。 此数据源旨在从实时客户资料服务中检索和使用数据（例如，检查进入旅程的人员是否为女性）。 它允许您使用用户档案数据和体验事件数据。 有关实时客户资料服务的更多信息，请参阅此[页面](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=zh-Hans)。

>[!NOTE]
>
>您可以检索不到一年前创建的1000个最新体验事件。

要允许连接到实时客户资料服务，我们必须使用键来标识人员，以及将键关联到的命名空间。 因此，仅当您的历程以包含键和命名空间的事件开头时，才能使用此数据源。 请参阅[此页](../building-journeys/journey.md)。

您可以编辑名为“ProfileFieldGroup”的预配置字段组，添加新字段组并删除未在任何草稿或实时历程中使用的字段组。 请参阅[此页](../datasource/field-groups.md)。

以下是向内置数据源添加字段组的主要步骤。

1. 从数据源列表中，选择内置的Adobe Experience Platform数据源。

   这将打开屏幕右侧的数据源配置窗格。

   ![](../assets/journey23.png)

1. 单击&#x200B;**[!UICONTROL Add a New Field Group]**&#x200B;以定义要检索的一系列新字段。 请参阅[此页](../datasource/field-groups.md)。

   ![](../assets/journey24.png)

1. 从&#x200B;**[!UICONTROL Schema]**&#x200B;下拉列表中选择一个架构。 此字段列出了Adobe Experience Platform中提供的配置文件和体验事件架构。 未在[!DNL Journey Orchestration]中执行架构创建。 它在Adobe Experience Platform表演。
1. 选择要使用的字段。
1. 定义缓存持续时间。
1. 单击&#x200B;**[!UICONTROL Save]**。

将光标放在字段组的名称上时，您将在右侧看到两个图标。 利用字段组，可删除和复制字段组。 请注意，仅当字段组未用在任何实时或草稿历程中时，**[!UICONTROL Delete]**&#x200B;图标才可用（信息显示在&#x200B;**[!UICONTROL Used in]**&#x200B;字段中）。
