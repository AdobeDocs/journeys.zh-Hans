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
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1

---


# 关于事件 {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="关于事件"
>abstract="事件与人相关联。 它与人的行为有关（例如，某人购买了产品、访问了商店、退出了网站等）或者与某人有关的某些事情（例如，某人达到10 000个忠诚度积分）。 这就是旅程编排将在旅程中倾听的内容，以编排最佳的下一步行动。"

事件与人相关联。 它与人的行为有关（例如，某人购买了产品、访问了商店、退出了网站等）或者与某人有关的某些事情（例如，某人达到10 000个忠诚度积分）。 这就是旅程编排将在旅程中倾听的内容，以编排最佳的下一步行动。

此配置是必 **需的**，因为旅程安排旨在倾听事件，并且始终由技术用户执 **行**。

事件配置允许您定义“旅程安排”将作为事件接收的信息。 您可以使用多个事件（在旅程的不同步骤中），而多个旅程可以使用相同的事件。

如果您编辑草稿或实时旅程中使用的事件，则只能更改名称、说明或添加有效负荷字段。 我们严格限制草稿或实况旅程的版本，以避免旅程中断。

## 一般原则 {#section_r1f_xqt_pgb}

事件是POST API调用。 事件通过Streaming Ingestion API发送到Adobe Experience Cloud数据平台。 通过事务消息API发送的事件的URL目标称为“入口”。 事件的有效负荷遵循XDM格式。

有效负荷包含Streaming Ingestion API需要的工作信息（在标题中）和Journey Orchestration需要的工作信息(事件ID，有效负荷主体的一部分)以及要在旅程中使用的信息（在正文中，例如放弃的购物车数量）。 流摄取有两种模式：已验证和未验证。 有关流摄取API的详细信息，请参 [阅此链接](https://docs.adobe.com/content/help/en/experience-platform/xdm/api/getting-started.html)。

通过Streaming Ingestion API到达后，事件会流入称为Pipeline的内部服务，然后流入数据平台。 如果事件模式启用了实时客户用户档案服务标志和数据集ID，并且还具有实时客户用户档案标志，则该数据集ID将流入实时客户用户档案服务。

管道过滤器事件，其有效负荷包含由旅程编排提供并包含在事件有效负荷中的旅程编排eventID(请参阅下面的事件创建过程)。 这些事件通过旅程安排进行聆听，并触发相应的旅程。

## 创建新事件 {#section_tbk_5qt_pgb}

以下是配置新事件的主要步骤：

1. 在顶部菜单中，单击选项 **[!UICONTROL Events]** 卡。 将显示列表。 有关 [](../about/user-interface.md) 该界面的详细信息，请参阅。

   ![](../assets/journey5.png)

1. 单 **[!UICONTROL Add]** 击以创建新事件。 事件配置窗格将在屏幕的右侧打开。

   ![](../assets/journey6.png)

1. 输入事件的名称。

   >[!NOTE]
   >
   >请勿使用空格或特殊字符。 请勿使用30个以上的字符。

1. 为事件添加说明。 此步骤是可选的。
1. 定义模式和有效负荷字段：在这里，您可以选择事件信息（通常称为有效负荷），旅程安排将会收到这些信息。 然后，您就可以在您的旅程中使用这些信息。 请参见 [](../event/defining-the-payload-fields.md)。
1. 使用此事件的旅程数显示在字段中 **[!UICONTROL Used in]** 。 您可以单击图 **[!UICONTROL View journeys]** 标以使用此事件显示旅程的列表。
1. 添加命名空间。 此步骤是可选的，但建议您添加命名空间，以便利用实时客户用户档案服务中存储的信息。 它定义事件具有的键的类型。 请参见 [](../event/selecting-the-namespace.md)。
1. 定义键：从有效负荷字段中选择一个字段，或定义一个公式以标识与事件关联的人员。 如果您选择命名空间，则会自动设置此键（但仍可编辑）。 事实上，旅程安排会选取与命名空间对应的密钥(例如，如果您选择了电子邮件命名空间，则会选择电子邮件密钥)。 请参见 [](../event/defining-the-event-key.md)。
1. 添加条件。 此步骤是可选的。 这样，系统只能处理满足条件的事件。 条件只能基于事件中包含的信息。 请参见 [](../event/adding-a-condition.md)。
1. 单击 **[!UICONTROL Save]**.

   ![](../assets/journey7.png)

   现在，事件已配置好，可随时投入旅程。 接收事件需要其他配置步骤。 请参见 [](../event/additional-steps-to-send-events-to-journey-orchestration.md)。
