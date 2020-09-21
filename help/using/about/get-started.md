---
title: 入门
description: Journey Orchestration 入门
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: ht
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: ht
source-wordcount: '291'
ht-degree: 100%

---


# 入门{#concept_y4b_4qt_52b}

在 [!DNL Journey Orchestration] 中，有两种用户，每种用户都执行特定任务：**技术用户**&#x200B;和&#x200B;**商业用户。**&#x200B;用户访问权限通过产品资料和权限进行管理。请参阅 [](../about/access-management.md)以了解如何配置用户访问。

以下是配置和使用 [!DNL Journey Orchestration] 的主要步骤：

1. **配置事件**

   您需要定义预期信息以及如何处理信息。此配置是强制性的。此步骤由&#x200B;**技术用户**&#x200B;执行。

   有关详细信息，请参见 [](../event/about-events.md)。

   ![](../assets/journey7.png)

1. **配置数据源**

   您需要定义与系统的连接，以检索将在您的旅程中使用的其他信息，例如在您的条件中。在预配时还会配置内置 Adobe Experience Platform 数据源。如果您仅利用旅程中事件的数据，则不需要执行此步骤。此步骤由&#x200B;**技术用户**&#x200B;执行。

   有关详细信息，请参见 [](../datasource/about-data-sources.md)。

   ![](../assets/journey22.png)

1. **配置操作**

   如果您使用第三方系统来发送消息，则需要配置其与 [!DNL Journey Orchestration] 的连接。请参见 [](../action/about-custom-action-configuration.md)。

   如果您使用 Adobe Campaign Standard 来发送消息，则需要配置内置操作。请参见 [](../action/working-with-adobe-campaign.md)。

   这些步骤由&#x200B;**技术用户**&#x200B;执行。

   ![](../assets/custom2.png)

1. **设计您的旅程**

   结合不同的事件、编排和操作活动，构建多步跨渠道方案。此步骤由&#x200B;**商业用户**&#x200B;执行。

   有关详细信息，请参阅 [](../building-journeys/journey.md)。

   ![](../assets/journeyuc2_24.png)

1. **测试并发布旅程**

   您需要验证并激活旅程。此步骤由&#x200B;**商业用户**&#x200B;执行。

   有关详细信息，请参阅 [](../building-journeys/testing-the-journey.md)和 [](../building-journeys/publishing-the-journey.md)。

   ![](../assets/journeyuc2_32bis.png)

1. **监控您的旅程**

   使用专用的报告工具衡量旅程的有效性。此步骤由&#x200B;**商业用户**&#x200B;执行。

   有关详细信息，请参阅 [](../reporting/about-journey-reports.md)。

   ![](../assets/dynamic_report_journey_12.png)

