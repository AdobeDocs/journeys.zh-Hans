---
product: adobe campaign
solution: Journey Orchestration
title: 'Adobe Experience Platform 数据源 '
description: '了解如何配置Adobe Experience Platform数据源 '
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Adobe Experience Platform 数据源 {#concept_zrb_nqt_52b}

Adobe Experience Platform数据源定义与实时客户用户档案服务的连接。 此数据源是内置的并且已预配置。 无法删除。 此数据源旨在从实时客户用户档案服务中检索和使用数据（例如，检查进入旅程的人是否为女性）。 它允许您使用用户档案数据和体验事件数据。 有关实时客户用户档案服务的详细信息，请参阅此[页面](https://docs.adobe.com/content/help/zh-Hans/experience-platform/profile/home.html)。

>[!NOTE]
>
>您可以检索不到一年前创建的1000个最新体验事件。

要允许与实时客户用户档案服务建立连接，我们必须使用密钥来识别人，以及将密钥与命名空间相结合。 因此，仅当您的旅程开始包含密钥和命名空间的事件时，才能使用此数据源。 请参阅[此页](../building-journeys/journey.md)。

您可以编辑名为“ProfileFieldGroup”的预配置字段组，添加新字段组，并删除任何草稿或实时旅程中未使用的字段组。 请参阅[此页](../datasource/field-groups.md)。

以下是向内置数据源添加字段组的主要步骤。

1. 从数据源列表中，选择内置的Adobe Experience Platform数据源。

   这将打开屏幕右侧的数据源配置窗格。

   ![](../assets/journey23.png)

1. 单击&#x200B;**[!UICONTROL Add a New Field Group]**&#x200B;定义要检索的新系列字段。 请参阅[此页](../datasource/field-groups.md)。

   ![](../assets/journey24.png)

1. 从&#x200B;**[!UICONTROL Schema]**&#x200B;下拉列表中选择一个模式。 此领域提供列表用户档案和体验事件模式(在Adobe Experience Platform)。 模式创建不在[!DNL Journey Orchestration]中执行。 它在Adobe Experience Platform演出。
1. 选择要使用的字段。
1. 定义缓存持续时间。
1. 单击&#x200B;**[!UICONTROL Save]**。

将光标放在字段组的名称上时，您将在右侧看到两个图标。 它们允许您删除和重复字段组。 请注意，仅当字段组未用于任何实时或草稿旅程时，**[!UICONTROL Delete]**&#x200B;图标才可用（**[!UICONTROL Used in]**&#x200B;字段中显示的信息）。
