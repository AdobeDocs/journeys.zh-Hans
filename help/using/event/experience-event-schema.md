---
product: adobe campaign
title: 关于Journey Orchestration事件的ExperienceEvent架构
description: 了解用于Journey Orchestration事件的ExperienceEvent架构
feature: Journeys
role: User
level: Intermediate
exl-id: ffec0d42-8632-4806-97df-da2a2372ca53
source-git-commit: 3a0fc5cd6b7bc4177ab50986b11b020a11a72c9b
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 4%

---

# 关于的ExperienceEvent架构 [!DNL Journey Orchestration] 事件

[!DNL Journey Orchestration] 事件是通过流式摄取发送到Adobe Experience Platform的XDM体验事件。

因此，设置事件的重要先决条件 [!DNL Journey Orchestration] 您熟悉Adobe Experience Platform的Experience Data Model（或XDM）、如何构建XDM Experience Event架构，以及如何将XDM格式的数据流式传输到Adobe Experience Platform。

## 架构要求 [!DNL Journey Orchestration] 事件

设置事件的第一步 [!DNL Journey Orchestration] 是确保您定义了用于表示事件的XDM架构，并创建了数据集以在Adobe Experience Platform上记录事件的实例。 严格来说，没有必要为事件设置数据集，但将事件发送到特定数据集将允许您维护用户的事件历史记录，以供将来参考和分析，因此始终是很好的做法。 如果您还没有适合事件的架构和数据集，则可以在Adobe Experience Platform Web界面中完成这两项任务。

![](../assets/schema1.png)

任何将使用的XDM架构 [!DNL Journey Orchestration] 事件应满足以下要求：

* 架构必须是XDM ExperienceEvent类的。

   ![](../assets/schema2.png)

* 对于系统生成的事件，架构必须包括Orchestration eventID mixin。 [!DNL Journey Orchestration] 使用此字段标识历程中使用的事件。

   ![](../assets/schema3.png)

* 声明一个标识字段，用于标识事件的主体。 如果未指定标识，则可以使用标识映射。 不建议采取此做法。

   ![](../assets/schema4.png)

* 如果您希望此数据稍后可在历程中查找，请标记架构和数据集的配置文件。

   ![](../assets/schema5.png)

   ![](../assets/schema6.png)

* 您可以随意包含数据字段，以捕获要与事件一起包含的任何其他上下文数据，例如有关用户的信息、生成事件的设备、位置或与事件相关的任何其他有意义的情况。

   ![](../assets/schema7.png)

   ![](../assets/schema8.png)

## 利用架构关系{#leverage_schema_relationships}

Adobe Experience Platform 让您可以定义架构之间的关系，以便将一个数据集用作另一个数据集的查询表。

假设您的品牌数据模型具有一个用于捕获购买情况的模式。 此外，您还有一个产品目录架构。 您可以在购买架构中捕获产品ID，并使用关系从产品目录中查找更完整的产品详细信息。 例如，这样，您就可以为购买笔记本电脑的所有客户创建一个区段，而不必明确列出所有笔记本电脑ID或在事务性系统中捕获每个产品的详细信息。

要定义关系，您需要在源架构中有一个专用字段，在本例中是购买架构中的产品ID字段。 此字段需要引用目标架构中的产品ID字段。 必须为配置文件启用源表和目标表，并且目标架构必须将公共字段定义为其主要标识。

以下是为将产品ID定义为主要标识的配置文件启用的产品目录架构。

![](../assets/schema9.png)

以下是产品ID字段中定义关系的购买架构。

![](../assets/schema10.png)

>[!NOTE]
>
>在中了解有关架构关系的更多信息 [Experience Platform文档](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/configure-relationships-between-schemas.html?lang=en).

在Journey Orchestration中，您可以利用链接表中的所有字段：

* 配置单一事件时， [了解更多](../event/experience-event-schema.md#unitary_event_configuration)
* 在历程中使用条件时， [了解更多](../event/experience-event-schema.md#journey_conditions_using_event_context)
* 在自定义操作个性化中， [了解更多](../event/experience-event-schema.md#custom_action_personalization_with_journey_event_context)

### 单一事件配置{#unitary_event_configuration}

链接的架构字段在单一事件配置中可用：

* 浏览事件配置屏幕中的事件架构字段时。
* 在为系统生成的事件定义条件时。

![](../assets/schema11.png)

链接的字段不可用：

* 在事件键公式中
* 在事件id条件中（基于规则的事件）

要了解如何配置单一事件，请参阅此 [页面](../event/about-creating.md).

### 使用事件上下文的历程条件{#journey_conditions_using_event_context}

您可以使用查询表中的数据，该表链接到历程中使用的事件，以进行条件构建（表达式编辑器）。

在历程中添加条件、编辑表达式并在表达式编辑器中展开事件节点。

![](../assets/schema12.png)

要了解如何定义历程条件，请参阅此 [页面](../building-journeys/condition-activity.md).

### 使用历程事件上下文进行操作个性化{#custom_action_personalization_with_journey_event_context}

配置历程操作活动的操作参数时，链接的字段可用。

![](../assets/schema13.png)

要了解如何使用自定义操作，请参阅此 [页面](../building-journeys/using-custom-actions.md).

