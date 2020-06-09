---
title: 关于事件
description: 了解如何配置事件
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
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 74%

---


# 关于事件 {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="关于事件"
>abstract="事件与个人相关联。它与个人的行为有关（例如，某人购买了产品、访问了商店、退出了网站等）或者与个人相关的某件事情有关（例如，某人达到 10 000 个忠诚点）。This is what [!DNL Journey Orchestration] will listen to in journeys to orchestrate the best next actions."

事件与个人相关联。它与个人的行为有关（例如，某人购买了产品、访问了商店、退出了网站等）或者与个人相关的某件事情有关（例如，某人达到 10 000 个忠诚点）。This is what [!DNL Journey Orchestration] will listen to in journeys to orchestrate the best next actions.

This configuration is **mandatory**, as [!DNL Journey Orchestration] is designed to listen to events, and always performed by a **technical user**.

The event configuration allows you to define the information [!DNL Journey Orchestration] will receive as events. 您可以使用多个事件（在旅程的不同步骤中），而多个旅程可以使用相同的事件。

如果您编辑在草稿或实时旅程中使用的事件，则只能更改名称、描述或添加有效负载字段。我们严格限制草稿或实时旅程的版本，以避免中断旅程。

## 一般原则 {#section_r1f_xqt_pgb}

事件是 POST API 调用。事件通过流式引入 API 发送到 Adobe Experience Cloud Data Platform。通过事务性消息传送 API 发送的事件的 URL 目标称为“入口”。事件的有效负载遵循 XDM 格式。

The payload contains information required by Streaming Ingestion APIs to work (in the header) and the information required by [!DNL Journey Orchestration] to work (the event ID, part of the payload body) and information to be used in journeys (in the body, for example, the amount of an abandoned cart). 流式引入有两种模式，即验证和未验证。有关流式引入 API 的详细信息，请参阅[此链接](https://docs.adobe.com/content/help/zh-Hans/experience-platform/xdm/api/getting-started.html)。

事件通过流式引入 API 到达后，会流入称为“Pipeline”的内部服务，然后流入 Data Platform。如果事件架构启用了实时客户资料服务标志，并且数据集 ID 也具有实时客户资料标志，则会流入实时客户资料服务。

The Pipeline filters events which have a payload containing [!DNL Journey Orchestration] eventIDs (see the event creation process below) provided by [!DNL Journey Orchestration] and contained in event payload. These events are listened by [!DNL Journey Orchestration] and the corresponding journey is triggered.

## 创建新事件 {#section_tbk_5qt_pgb}

以下是配置新事件的主要步骤：

1. 在顶部菜单中，单击&#x200B;**[!UICONTROL Events]**&#x200B;选项卡。将显示事件列表。有关该界面的详细信息，请参见 [](../about/user-interface.md)。

   ![](../assets/journey5.png)

1. 单击&#x200B;**[!UICONTROL Add]**&#x200B;以创建新事件。事件配置窗格将在屏幕右侧打开。

   ![](../assets/journey6.png)

1. 输入事件的名称。

   >[!NOTE]
   >
   >请勿使用空格或特殊字符。请勿使用超过 30 个字符。

1. 向事件添加描述。此步骤是可选的。
1. Define the schema and payload fields: this is where you select the event information (usually called a payload) [!DNL Journey Orchestration] expects to receive. 然后，您便能够在旅程中使用这些信息。请参见 [](../event/defining-the-payload-fields.md)。
1. 使用此事件的旅程数显示在&#x200B;**[!UICONTROL Used in]**&#x200B;字段中。您可以单击 **[!UICONTROL View journeys]**&#x200B;图标，以显示使用此事件的旅程列表。
1. 添加命名空间。此步骤是可选的，但还是建议您添加命名空间，以便您利用实时客户资料服务中存储的信息。它定义事件具有的键类型。请参见 [](../event/selecting-the-namespace.md)。
1. 定义键：从有效负载字段中选择一个字段或定义一个公式以标识与事件关联的个人。如果您选择命名空间，此键将自动设置（但仍可编辑）。Indeed, [!DNL Journey Orchestration] picks the key that should correspond to the namespace (for example, if you select an email namespace, the email key will be selected). 请参见 [](../event/defining-the-event-key.md)。
1. 添加条件。此步骤是可选的。这允许系统仅处理符合条件的事件。此条件只能基于事件中包含的信息。请参见 [](../event/adding-a-condition.md)。
1. 单击 **[!UICONTROL Save]**.

   ![](../assets/journey7.png)

   事件现已配置完毕，可随时投入旅程。还需要其他配置步骤以接收事件。请参见 [](../event/additional-steps-to-send-events-to-journey-orchestration.md)。
