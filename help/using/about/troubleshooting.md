---
title: 故障排除
description: 了解有关故障排除的更多信息
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: a65a5db5b35291cbc2635f9ae67fd8c8c5284575
workflow-type: tm+mt
source-wordcount: '1034'
ht-degree: 96%

---


# 故障排除{#concept_nlv_bcv_2fb}

在本部分中，您将了解如何在测试或发布之前对旅程进行故障排除。当旅程处于测试模式或旅程处于实时状态时，可以执行以下列出的所有检查。建议在测试模式下进行以下所有检查，然后继续发布。请参见 [](../building-journeys/testing-the-journey.md)。

## 测试前检查错误{#section_h3q_kqk_fhb}

测试和发布旅程之前，请验证所有活动均已正确配置。如果系统仍检测到错误，则无法执行测试或发布。

出现错误时，画布上的活动本身会显示警告符号。将光标放在感叹号上以显示错误消息。如果单击活动，您将看到带警告的错误行。例如，如果必填字段为空，则会显示错误。

![](../assets/journey63.png)

例如，在画布中，当两个活动断开连接时，系统将显示一条警告消息。

![](../assets/canvas-disconnected.png)

在 **[!UICONTROL Test]** 切换和 **[!UICONTROL Publish]**&#x200B;按钮旁边，会显示一个警告标记。此警告标记显示系统检测到的错误，并阻止测试模式激活或旅程发布。大多数时间，系统检测到的错误都与活动上可见的错误相关，但有时它们也与其他问题相关。在这种情况下，您可以显示它们，尝试使用错误描述来识别问题。如果您无法识别问题，可以复制详细信息并发送给管理员或支持团队。请注意，阻止测试的错误和阻止发布的错误是相似的。

系统检测到两种问题：错误和警告。错误阻止发布和测试激活。警告指示未阻止测试激活或发布的潜在问题。您将看到问题的描述和 ERR_XXX_XXX 类型的问题日志 ID。这将帮助技术支持人员确定问题。

**[!UICONTROL Test]** 切换和 **[!UICONTROL Publish]** 按钮旁边的符号上可以显示两种不同的颜色。出现错误时，该符号以红色显示。出现警告时，以橙色显示。

![](../assets/journey75.png)

旅程全局的错误和警告首先在列表中显示。之后，与特定活动相关的错误和警告按活动顺序或在旅程中的出现顺序从左到右列出。**[!UICONTROL Copy details]** 按钮可复制有关旅程的技术信息，供支持团队用于进行故障排除。

当操作或条件中发生错误时，单个旅程将停止。 使其继续的唯一方法是选中该框 **[!UICONTROL Add an alternative path in case of a timeout or an error]**。 请参见 [](../building-journeys/using-the-journey-designer.md#paths)。

## 检查事件是否正确发送{#section_rqz_11t_dgb}

旅程的起点永远是事件。您可以使用 Postman 等工具执行测试。

您可以检查通过这些工具发送的 API 调用是否正确发送。如果返回错误，则表示您的调用有问题。再次检查有效负载、标题（特别是组织 ID）以及目标 URL。您可以询问管理员要点击的正确 URL。

事件不会直接从源推送到 [!DNL Journey Orchestration]。Indeed, [!DNL Journey Orchestration] relies on Adobe Experience Platform’s streaming ingestion APIs. 因此，如果出现与事件相关的问题，您可以参阅本 [页](https://docs.adobe.com/content/help/zh-Hans/experience-platform/ingestion/streaming/troubleshooting.html)，了解流摄取 API 故障排除。

## 检查人员是否进入旅程{#section_x4v_zzs_dgb}

[!DNL Journey Orchestration] 报告实时衡量人员进入旅程。

如果您成功发送事件，但未看到有人进入旅程，则意味着在事件发送和事件接收之间出现问题。

以下是管理员应检查的一些事项：

* 是否确定期待传入事件的旅程处于测试模式或处于实时状态？
* 是否在从有效负载预览复制有效负载之前保存了您的事件？
* 您的事件有效负载是否包含事件 ID？
* 您是否点击了正确的 URL？
* 您是否使用“事件配置”窗格中的有效负载结构预览遵循了流摄取 API 的有效负载结构？请参见 [](../event/previewing-the-payload.md)。
* 您是否在事件标题中使用了正确的键/值对？

   ```
   X-gw-ims-org-id - your ORGID
   Content-type - application/json
   ```

## 检查人员在旅程中的导航方式{#section_l5y_yzs_dgb}

[!DNL Journey Orchestration] 报告测量旅程中个人的进度。很容易识别人员在何处被拦住以及为什么被拦住。

以下是一些要检查的内容：

* 是因为除人员外的情况吗？例如，条件为“性别=男性”，而该人员为女性。如果条件不太复杂，此检查可由商业用户执行。
* 是由于调用数据源时没有响应吗？当旅程正在测试时，此信息可在测试模式日志中查看。当旅程处于实时状态时，管理员可以测试对数据源的直接调用并检查收到的答案。管理员还可以重复旅程并进行测试。

## 检查消息是否发送成功{#section_qb1_yzs_dgb}

如果人员在旅程中以正确的方式流动，但没有收到他们应该收到的消息，您可以检查：

* 事务性消息正确包含了发送消息的请求。商业用户可以访问应发送的事务性消息，并检查最新执行的时间是否与旅程的执行时间对应。他还可以检查事务消息接收的最新 API 调用/事件。
* 事务性消息已成功发送消息。在事务性消息的发送日志中，您可以看到每个执行的状态。您可以看看其是绿色的还是红色的，以及出现了什么问题。商业用户可以访问此屏幕并将日志发送给管理员以进一步调查。

对于通过自定义操作发送的消息，在旅程测试中可以检查的唯一一点就是自定义操作系统的调用是否会导致错误。如果与自定义操作关联的对外部系统的调用不会导致错误，但也不会导致消息发送，则应对外部系统进行一些调查。

