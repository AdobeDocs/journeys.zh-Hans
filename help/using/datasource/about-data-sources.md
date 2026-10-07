---
product: adobe campaign
title: 关于数据源
description: 了解如何配置数据源
feature: Journeys
role: User
level: Intermediate
exl-id: 2371d2c9-3035-46ac-9c76-755fb453c24e
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
source-wordcount: '362'
ht-degree: 95%
---
# 关于数据源 {#concept_s1s_dqt_52b}


>[!CAUTION]
>
>**希望了解 Adobe Journey Optimizer**？ 请单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取 Journey Optimizer 文档。
>
>
>_本文档参考已被 Journey Optimizer 取代的旧版 Journey Orchestration 资料。 如果您对访问 Journey Orchestration 或 Journey Optimizer 有任何疑问，请联系帐户团队。_



>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="关于数据源"
>abstract="数据源配置允许您定义与系统的连接，以检索将在您的历程中使用的其他信息。"

数据源配置允许您定义与系统的连接，以检索将在您的历程中使用的其他信息，例如：

* [条件定义](../building-journeys/condition-activity.md)
* [操作](../action/action.md)中的参数和个性化数据
* [自定义等待定义](../building-journeys/wait-activity.md#custom)
* [时区定义](../building-journeys/timezone-management.md)

如果您的历程只利用来自事件负载的本地数据，则不需要此配置。 例如，如果您的历程由一个事件组成，后跟一个只使用事件数据的电子邮件活动，则无需配置数据源。

数据源有两种类型：

* 预配置的 Adobe Experience Platform 数据源，它定义与实时客户轮廓服务的连接。 这是一种内置数据源。 请参阅[此页](../datasource/adobe-experience-platform-data-source.md)。
* 外部数据源，它允许您定义与外部系统的连接。 这些是您可以创建的数据源。 请参阅[此页](../datasource/external-data-sources.md)。

对于每个数据源，您都可以使用字段组定义要检索的信息。 字段组是可从数据源检索的字段集。 请参阅[此页](../datasource/field-groups.md)。

以下是主要的数据源配置步骤：

>[!NOTE]
>
>数据源配置操作必须始终由&#x200B;**技术用户**&#x200B;执行。

1. 在菜单窗格中，选择&#x200B;**[!UICONTROL Admin]**。 在&#x200B;**[!UICONTROL Data sources]**&#x200B;部分中，单击&#x200B;**[!UICONTROL Manage]**。

   将显示数据源列表。 有关该界面的更多信息，请参阅[此页面](../about/user-interface.md)。

   ![](../assets/journey18.png)

1. 然后，您可以将字段组添加到内置数据源（请参阅[此页面](../datasource/adobe-experience-platform-data-source.md)）或创建新的外部数据源（请参阅[此页面](../datasource/external-data-sources.md)）和关联的字段组（请参阅](../datasource/field-groups.md)此页面[）。

   ![](../assets/journey23.png)

1. 单击 **[!UICONTROL Save]**。

   数据源现已配置完毕，可随时用于您的历程。
