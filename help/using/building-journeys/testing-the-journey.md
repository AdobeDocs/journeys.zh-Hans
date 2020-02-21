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
source-git-commit: 6274426ec04315149fb430b847498c0e20164bae

---


# 测试旅程{#testing_the_journey}

在能够测试旅程之前，您必须解决所有错误（如果有）。 请参见 [](../about/troubleshooting.md#section_h3q_kqk_fhb)。

您可以使用测试配置文件在发布之前测试旅程。 这使您能够分析个人在旅程中的流动情况，并在发布前进行疑难解答。

>[!NOTE]
>
>在测试模式下，所有等待活动都会自动设置为最后5秒。 这样，您就可以快速访问测试结果。

要使用测试模式，请执行以下步骤：

1. 在测试您的旅程之前，请验证该旅程是否有效且没有错误。 您将无法启动包含错误的旅程测试。 请参见 [](../about/troubleshooting.md#section_h3q_kqk_fhb)。出现错误时将显示警告符号。

1. 要激活测试模式，请单击位 **[!UICONTROL Test]** 于右上角的切换按钮。

   ![](../assets/journeytest1.png)

1. 单击 **[!UICONTROL Trigger an event]** 以配置活动并将其发送到旅程。 确保发送与测试配置文件相关的事件。 请参阅 [触发活动](#firing_events)。

   ![](../assets/journeyuctest1.png)

1. 收到事件后，单击该按 **[!UICONTROL Show log]** 钮以查看测试结果并进行验证。 请参 [阅查看日志](#viewing_logs)。

   ![](../assets/journeyuctest2.png)

1. 如果出现任何错误，请取消激活测试模式，修改您的旅程并再次测试它。 当测试结果确定时，您可以发布您的旅程。 请参见 [](../building-journeys/publishing-the-journey.md)。

## 重要说明 {#important_notes}

* 提供了一个接口，用于将事件触发到所测试的旅程，但事件也可由第三方系统（如Postman）发送。
* 只有在实时客户档案服务中标记为“测试档案”的个人才能进入测试旅程。 创建测试配置文件的过程与在数据平台中创建配置文件的过程相同。 您只需确保测试配置文件标志为真。 您可以使用数据平台界面中的“区段”部分在数据平台中创建测试配置文件的区段，并查看非穷尽列表。 目前无法显示完整列表。
* 测试模式仅在使用命名空间的草稿旅程中可用。 事实上，测试模式需要检查进入旅程的人员是否是测试档案，因此必须能够访问数据平台。
* 在测试会话期间，可以进入旅程的测试配置文件的最大数量为100。
* 禁用测试模式后，它将从过去输入该模式或当前使用该模式的所有人员中抢占旅程。
* 您可以根据需要多次启用／禁用测试模式。
* 在激活测试模式时，您无法修改旅程。 在测试模式下，您可以直接发布旅程，无需先前取消激活测试模式。

## 触发活动 {#firing_events}

通过 **[!UICONTROL Trigger an event]** 此按钮，您可以配置一个事件，该事件将使人员进入旅程。

作为入门项目，您必须知道在数据平台中哪些配置文件标记为测试配置文件。 事实上，测试模式只允许在旅程中使用这些配置文件，且活动必须包含ID。 期望的ID取决于事件配置。 例如，它可以是ECID。

此屏幕允许您配置在活动中传递的字段以及活动发送的执行。 该界面可帮助您在事件有效负荷中传递正确的信息，并确保信息类型正确。 测试模式保存测试会话中使用的最后一个参数以供以后使用。

![](../assets/journeytest4.png)

该界面允许您传递简单的事件参数。 如果要在事件中传递集合或其他高级对象，可单击以查看有 **[!UICONTROL Code View]** 效负荷的整个代码并对其进行修改。 例如，您可以复制和粘贴由技术用户准备的活动信息。

![](../assets/journeytest5.png)

技术用户还可以使用此界面编写事件负载和触发事件，而无需使用第三方工具。

## 查看日志 {#viewing_logs}

通过 **[!UICONTROL Show log]** 该按钮可以查看测试结果。 此页以JSON格式显示旅程的当前信息。 通过按钮可复制整个节点。 您需要手动刷新页面以更新旅程的测试结果。

![](../assets/journeytest3.png)

此时会显示旅程中当前的个人数（从技术上讲，他们称为实例）。 以下是为每个人显示的有用信息：

* _Id_:旅程中个人的内部ID。 这可用于调试目的。
* _currentstep_:个体在旅程中所处的步骤。 我们建议向活动中添加标签以更轻松地识别它们。
* _currentstep_ > phase:个人旅程的状态（正在运行、已完成、错误或超时）。 请参阅下文以了解更多信息。
* _currentstep_ > _extraInfo_:错误的描述和其他上下文信息。
* _externalKeys_:在事件中定义的键公式的值。
* _richedData_:旅程使用数据源时已检索到的数据。
* _transitionHistory_:个人遵循的步骤列表。 对于事件，将显示有效负荷。

