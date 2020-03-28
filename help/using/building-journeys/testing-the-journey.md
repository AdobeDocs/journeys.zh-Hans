---
title: 测试旅程
description: '了解旅程测试 '
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
source-git-commit: e53ecd96bbb308fe109843de6f64cde4cba5e246

---


# 测试旅程{#testing_the_journey}

在能够测试旅程之前，您必须解决所有错误（如果有）。 请参见 [](../about/troubleshooting.md#section_h3q_kqk_fhb)。

您可以在发布之前使用测试用户档案测试您的旅程。 这使您能够分析个人在旅程中的流动情况，并在发布前进行疑难解答。

要使用测试模式，请执行以下步骤：

1. 在测试您的旅程之前，请验证该旅程是否有效且没有错误。 您将无法启动包含错误的旅程测试。 请参见 [](../about/troubleshooting.md#section_h3q_kqk_fhb)。出现错误时将显示警告符号。

1. 要激活测试模式，请单击位 **[!UICONTROL Test]** 于右上角的切换按钮。

   ![](../assets/journeytest1.png)

1. 使用左 **下角的“在test** （等待）”参数定义每个等待活动在测试模式下的持续时间。 默认时间为10秒。 这将确保您快速获得测试结果。 此参数仅在您的旅程中丢弃了一个或多个等待活动时才显示。

   ![](../assets/journeytest_wait.png)

1. 单击 **[!UICONTROL Trigger an event]** 以配置事件并将其发送到旅程。 确保发送与测试事件相关的用户档案。 请参阅 [释放您的事件](#firing_events)。

   ![](../assets/journeyuctest1.png)

1. 收到事件后，单击按钮以 **[!UICONTROL Show log]** 视图测试结果并进行验证。 请参 [阅查看日志](#viewing_logs)。

   ![](../assets/journeyuctest2.png)

1. 如果出现任何错误，请取消激活测试模式，修改您的旅程并再次测试它。 当测试结果确定时，您可以发布您的旅程。 请参见 [](../building-journeys/publishing-the-journey.md)。

## 重要说明 {#important_notes}

* 提供了一个接口，用于向所测试的旅程发射事件，但事件也可以由第三方系统（如Postman）发送。
* 只有在实时客户用户档案服务中标为“测试用户档案”的个人才能进入测试旅程。 创建测试用户档案的过程与在数据平台中创建用户档案的过程相同。 您只需确保测试用户档案标志为真。 您可以使用数据平台界面中的“区段”部分在数据平台中创建测试用户档案的区段，并查看非穷尽列表。 目前无法显示完整列表。
* 测试模式仅在使用命名空间的草稿旅程中可用。 事实上，测试模式需要检查进入旅程的人员是否是测试用户档案，因此必须能够到达数据平台。
* 在测试会话期间，可以进入旅程的测试用户档案数最多为100。
* 禁用测试模式后，它将从过去输入该模式或当前使用该模式的所有人员中抢占旅程。
* 您可以根据需要多次启用／禁用测试模式。
* 在激活测试模式时，您无法修改旅程。 在测试模式下，您可以直接发布旅程，无需先前取消激活测试模式。

## 发射事件 {#firing_events}

该 **[!UICONTROL Trigger an event]** 按钮允许您配置一个事件，让人员进入旅程。

作为入门项目，您必须知道在数据平台中哪些用户档案标记为测试用户档案。 事实上，测试模式只允许旅程中的这些用户档案，并且事件必须包含ID。 期望的ID取决于事件配置。 例如，它可以是ECID。

如果您的旅程包含多个事件，请使用下拉列表选择事件。 然后，为每个事件配置所传递的字段和执行事件发送。 该界面可帮助您在事件有效负荷中传递正确的信息，并确保信息类型正确。 测试模式保存测试会话中使用的最后一个参数以供以后使用。

![](../assets/journeytest4.png)

该界面允许您传递简单的事件参数。 如果要在事件中传递集合或其他高级对象，可以单击以查看有 **[!UICONTROL Code View]** 效负荷的整个代码并对其进行修改。 例如，您可以复制和粘贴由技术用户准备的事件信息。

![](../assets/journeytest5.png)

技术用户还可以使用此界面来合成事件负载和触发事件，而无需使用第三方工具。

## 查看日志 {#viewing_logs}

通 **[!UICONTROL Show log]** 过按钮可视图测试结果。 此页以JSON格式显示旅程的当前信息。 通过按钮可复制整个节点。 您需要手动刷新页面以更新旅程的测试结果。

![](../assets/journeytest3.png)

>[!NOTE]
>
>在测试日志中，如果在调用第三方系统（数据源或操作）时出错，则显示错误代码和错误响应。

此时会显示旅程中当前的个人数（从技术上讲，他们称为实例）。 以下是为每个人显示的有用信息：

* _Id_:旅程中个人的内部ID。 这可用于调试目的。
* _currentstep_:个体在旅程中所处的步骤。 我们建议向您的活动添加标签以更轻松地识别它们。
* _currentstep_ > phase:个人旅程的状态（正在运行、已完成、错误或超时）。 请参阅下文以了解更多信息。
* _currentstep_ > _extraInfo_:错误的描述和其他上下文信息。
* _currentstep_ > _fetchErrors_:有关获取此步骤中发生的数据错误的信息。
* _externalKeys_:在事件中定义的键公式的值。
* _richedData_:旅程使用数据源时已检索到的数据。
* _transitionHistory_:列表个人所遵循的步骤。 对于事件，将显示有效负荷。
* _actionExecutionErrors_ :有关所发生错误的信息。

