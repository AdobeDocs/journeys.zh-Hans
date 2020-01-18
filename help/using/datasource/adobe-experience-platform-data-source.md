---
title: 'Adobe Experience platform数据源 '
description: '了解如何配置Adobe Experience platform数据源 '
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7e69b19f2b7099e5c015dd1052a58728cf143ffa

---


# Adobe Experience platform数据源 {#concept_zrb_nqt_52b}

Experience Platform数据源定义与实时客户档案服务的连接。 此数据源是内置的并且已预配置。 无法删除。 此数据源旨在从实时客户档案服务中检索和使用数据（例如，检查进入旅程的人是否为女性）。 它允许您使用个人资料数据和体验事件数据。 有关实时客户档案服务的详细信息，请参阅本 [页](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)。

>[!NOTE]
>
>您可以检索不到一年前创建的1000个最新体验活动。

要允许与实时客户档案服务连接，我们必须使用密钥来标识人物，并使用与密钥相关联的命名空间。 因此，仅当您的旅程以包含键和命名空间的事件开头时，您才能使用此数据源。 请参见 [](../building-journeys/journey.md)。

您可以编辑名为“ProfileFieldGroup”的预配置字段组，添加新字段组，并删除未用于任何草稿或实时旅程的字段组。 请参见 [](../datasource/field-groups.md)。

以下是向内置数据源添加字段组的主要步骤。

1. 从数据源列表中，选择内置的Experience Platform数据源。

   这将打开屏幕右侧的数据源配置窗格。

   ![](../assets/journey23.png)

1. 单击 **[!UICONTROL Add a New Field Group]**以定义要检索的新系列字段。 请参见[](../datasource/field-groups.md)。

   ![](../assets/journey24.png)

1. 从下拉菜单中选择 **[!UICONTROL Schema]**一个架构。 此字段列出平台中可用的配置文件和体验事件架构。 在旅程安排中不执行架构创建。 它在数据平台中执行。
1. 选择要使用的字段。
1. 定义缓存持续时间。
1. 单击 **[!UICONTROL Save]**。

将光标放在字段组的名称上时，您将在右侧看到两个图标。 它们允许您删除和复制字段组。 请注意， **[!UICONTROL Delete]**仅当字段组未用于任何实时或拟定旅程时，该图标才可用(字段中显示的**[!UICONTROL Used in]** 信息)。
