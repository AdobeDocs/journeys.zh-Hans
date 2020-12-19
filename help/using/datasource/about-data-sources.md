---
product: adobe campaign
solution: Journey Orchestration
title: 关于数据源
description: '了解如何配置数据源 '
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 关于数据源 {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="关于数据源"
>abstract="数据源配置操作必须始终由技术用户执行。数据源配置允许您定义与系统的连接，以检索将在您的旅程中使用的其他信息，例如：条件定义、操作中的参数和个性化数据、自定义等待定义、时区定义。"

数据源配置允许您定义与系统的连接，以检索将在您的旅程中使用的其他信息，例如：

* [条件定义](../building-journeys/condition-activity.md)
* [操作](../action/action.md)中的参数和个性化数据
* [自定义等待定义](../building-journeys/wait-activity.md#custom)
* [时区定义](../building-journeys/timezone-management.md)

如果您的旅程只利用来自事件有效负载的本地数据，则不需要此配置。例如，如果您的旅程由一个事件组成，后跟一个只使用事件数据的电子邮件活动，则无需配置数据源。

数据源有两种类型：

* 预配置的 Adobe Experience Platform 数据源，它定义与实时客户资料服务的连接。这是一种内置数据源。请参阅[此页](../datasource/adobe-experience-platform-data-source.md)。
* 外部数据源，它允许您定义与外部系统的连接。这些是您可以创建的数据源。请参阅[此页](../datasource/external-data-sources.md)。

对于每个数据源，您定义要使用字段组检索的信息。字段组是可从数据源检索的字段集。请参阅[此页](../datasource/field-groups.md)。

有关如何配置 Adobe Experience Platform 数据源和外部数据源以及如何在旅程中查找和使用数据的更多信息，请观看此[教程视频](https://docs.adobe.com/content/help/zh-Hans/journey-orchestration-learn/tutorials/configure-data-sources.html)。

以下是主要的数据源配置步骤：

>[!NOTE]
>
>数据源配置操作必须始终由&#x200B;**技术用户**&#x200B;执行。

1. 在顶部菜单中，单击 **[!UICONTROL Data Sources]**&#x200B;选项卡。

   将显示数据源列表。有关该接口的详细信息，请参见[此页](../about/user-interface.md)。

   ![](../assets/journey18.png)

1. 然后，您可以向内置数据源添加字段组（请参阅[此页](../datasource/adobe-experience-platform-data-source.md)）或创建新的外部数据源（请参阅[此页](../datasource/external-data-sources.md)）和相关字段组（请参阅[此页](../datasource/field-groups.md)）。

   ![](../assets/journey23.png)

1. 单击 **[!UICONTROL Save]**.

   数据源现已配置完毕，可随时用于您的旅程。
