---
title: 'Adobe Experience Platform 数据源 '
description: '了解如何配置Adobe Experience Platform数据源 '
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 10%

---


# Adobe Experience Platform 数据源 {#concept_zrb_nqt_52b}

Adobe Experience Platform数据源定义与实时客户用户档案服务的连接。 此数据源是内置的并且已预配置。 无法删除。 此数据源旨在从实时客户用户档案服务中检索和使用数据（例如，检查进入旅程的人是否为女性）。 它允许您使用用户档案数据和体验事件数据。 有关实时客户用户档案服务的详细信息，请参阅本 [页](https://docs.adobe.com/content/help/zh-Hans/experience-platform/profile/home.html)。

>[!NOTE]
>
>您可以检索不到一年前创建的1000个最新体验事件。

要允许与实时客户用户档案服务建立连接，我们必须使用密钥来识别人，以及将密钥与命名空间相结合。 因此，仅当您的旅程开始包含密钥和命名空间的事件时，才能使用此数据源。 请参见 [](../building-journeys/journey.md)。

您可以编辑名为“ProfileFieldGroup”的预配置字段组，添加新字段组，并删除任何草稿或实时旅程中未使用的字段组。 请参见 [](../datasource/field-groups.md)。

以下是向内置数据源添加字段组的主要步骤。

1. 从数据源列表中，选择内置的Adobe Experience Platform数据源。

   这将打开屏幕右侧的数据源配置窗格。

   ![](../assets/journey23.png)

1. 单击 **[!UICONTROL Add a New Field Group]** 以定义要检索的新系列字段。 请参见 [](../datasource/field-groups.md)。

   ![](../assets/journey24.png)

1. 从下拉菜单中选择 **[!UICONTROL Schema]** 一个模式。 此领域提供列表用户档案和体验事件模式(在Adobe Experience Platform)。 模式创建不在中执 [!DNL Journey Orchestration]行。 它在Adobe Experience Platform演出。
1. 选择要使用的字段。
1. 定义缓存持续时间。
1. 单击 **[!UICONTROL Save]**。

将光标放在字段组的名称上时，您将在右侧看到两个图标。 它们允许您删除和重复字段组。 请注意， **[!UICONTROL Delete]** 仅当字段组未用于任何实时或草稿旅程时，该图标才可用(字段中显示 **[!UICONTROL Used in]** 的信息)。
