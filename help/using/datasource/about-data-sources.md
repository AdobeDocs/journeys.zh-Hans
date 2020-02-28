---
title: 关于数据源
description: '了解如何配置数据源 '
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
source-git-commit: 690f8c1732c7d54c234e9ba633a2cf014492f423

---


# 关于数据源 {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id=&quot;jo_datasources&quot;
>title=&quot;关于数据源&quot;
>abstract=&quot;数据源配置始终由技术用户执行。 数据源配置允许您定义与系统的连接，以检索将在您的旅程中使用的其他信息，例如：条件定义、操作中的参数和个性化数据、自定义等待定义、自定义时区定义。”

数据源配置允许您定义与系统的连接，以检索将在您的旅程中使用的其他信息，例如：

* [条件定义](../building-journeys/condition-activity.md)
* 操作中的参数和个性化数 [据](../action/action.md)
* [自定义等待定义](../building-journeys/wait-activity.md#custom)
* [自定义时区定义](../building-journeys/timezone-management.md)

如果您的旅程只利用来自事件有效负荷的本地数据，则不需要此配置。 例如，如果您的旅程由一个事件组成，后跟一个只使用该事件数据的电子邮件活动，则无需配置数据源。

数据源有两种类型：

* 预配置的Experience platform数据源，用于定义与实时客户档案服务的连接。 这是一个内置的数据源。 请参见 [](../datasource/adobe-experience-platform-data-source.md)。
* 允许您定义与外部系统连接的外部数据源。 这些是您可以创建的。 请参见 [](../datasource/external-data-sources.md)。

对于每个数据源，您定义要使用字段组检索的信息。 字段组是从数据源检索的字段集。 请参见 [](../datasource/field-groups.md)。

有关如何配置Experience Platform数据源和外部数据源以及如何在旅程中查找和使用数据的详细信息，请观看此教 [程视频](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/configure-data-sources.html)。

以下是主要的数据源配置步骤：

>[!NOTE]
>
>数据源配置始终由技术用户 **执行**。

1. 在顶部菜单中，单击选 **[!UICONTROL Data Sources]** 项卡。

   此时将显示数据源列表。 有关 [](../about/user-interface.md) 该界面的详细信息，请参阅。

   ![](../assets/journey18.png)

1. 然后，您可以向内置数据源添加字段组(请参阅 [](../datasource/adobe-experience-platform-data-source.md))，或创建新的外部数据源(请参阅 [](../datasource/external-data-sources.md))和关联的字段组(请参阅 [](../datasource/field-groups.md))。

   ![](../assets/journey23.png)

1. 单击 **[!UICONTROL Save]**.

   数据源现已配置好，可在您的旅程中使用。
