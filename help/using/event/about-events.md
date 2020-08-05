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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 97%

---


# 关于事件 {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="关于事件"
>abstract="事件与个人相关联。它与个人的行为有关（例如，某人购买了产品、访问了商店、退出了网站等）或者与个人相关的某件事情有关（例如，某人达到 10 000 个忠诚点）。这就是 [!DNL Journey Orchestration] 在旅程中将侦听的内容，以编排最佳的后续行动。"

事件与个人相关联。它与个人的行为有关（例如，某人购买了产品、访问了商店、退出了网站等）或者与个人相关的某件事情有关（例如，某人达到 10 000 个忠诚点）。这就是 [!DNL Journey Orchestration] 在旅程中将侦听的内容，以编排最佳的后续行动。

此配置是&#x200B;**强制性的**，因为 [!DNL Journey Orchestration] 设计用于侦听事件，并且始终由&#x200B;**技术用户**&#x200B;执行。

事件配置允许您定义 [!DNL Journey Orchestration] 将作为事件接收的信息。您可以使用多个事件（在旅程的不同步骤中），而多个旅程可以使用相同的事件。

如果您编辑在草稿或实时旅程中使用的事件，则只能更改名称、描述或添加有效负载字段。我们严格限制草稿或实时旅程的版本，以避免中断旅程。

## 一般原则 {#section_r1f_xqt_pgb}

事件是 POST API 调用。事件通过流式引入 API 发送到 Adobe Experience Platform。通过事务性消息传送 API 发送的事件的 URL 目标称为“入口”。事件的有效负载遵循 XDM 格式。

有效负载包含流式引入 API 工作所需的信息（在标题中）和 [!DNL Journey Orchestration] 工作所需的信息（事件 ID，有效负载主体的一部分）以及要在旅程中使用的信息（在主体中，例如放弃购物车的数量）。流式引入有两种模式，即验证和未验证。有关流式引入 API 的详细信息，请参阅[此链接](https://docs.adobe.com/content/help/zh-Hans/experience-platform/xdm/api/getting-started.html)。

事件通过流摄取API到达后，流入名为Pipeline的内部服务，然后流入Adobe Experience Platform。 如果事件架构启用了实时客户资料服务标志，并且数据集 ID 也具有实时客户资料标志，则会流入实时客户资料服务。

Pipeline 过滤器事件的有效负载包含由 [!DNL Journey Orchestration] 提供并包含在事件有效负载中的 [!DNL Journey Orchestration] 事件 ID（请参阅以下事件创建流程）。这些事件通过 [!DNL Journey Orchestration] 侦听，并触发相应的旅程。

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
1. 定义架构和有效负载字段：在这里，您可以选择 [!DNL Journey Orchestration] 预期接收的事件信息（通常称为有效负载）。然后，您便能够在旅程中使用这些信息。请参见 [](../event/defining-the-payload-fields.md)。
1. 使用此事件的旅程数显示在&#x200B;**[!UICONTROL Used in]**&#x200B;字段中。您可以单击 **[!UICONTROL View journeys]**&#x200B;图标，以显示使用此事件的旅程列表。
1. 添加命名空间。此步骤是可选的，但还是建议您添加命名空间，以便您利用实时客户资料服务中存储的信息。它定义事件具有的键类型。请参见 [](../event/selecting-the-namespace.md)。
1. 定义键：从有效负载字段中选择一个字段或定义一个公式以标识与事件关联的个人。如果您选择命名空间，此键将自动设置（但仍可编辑）。事实上，[!DNL Journey Orchestration] 会选取应与命名空间对应的键（例如，如果您选择了电子邮件命名空间，则会自动选择电子邮件键）。请参见 [](../event/defining-the-event-key.md)。
1. 添加条件。此步骤是可选的。这允许系统仅处理符合条件的事件。此条件只能基于事件中包含的信息。请参见 [](../event/adding-a-condition.md)。
1. 单击 **[!UICONTROL Save]**.

   ![](../assets/journey7.png)

   事件现已配置完毕，可随时投入旅程。还需要其他配置步骤以接收事件。请参见 [](../event/additional-steps-to-send-events-to-journey-orchestration.md)。
