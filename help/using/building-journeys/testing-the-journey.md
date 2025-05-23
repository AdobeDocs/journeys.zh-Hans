---
product: adobe campaign
title: 测试历程
description: 了解历程测试
feature: Journeys
role: User
level: Intermediate
exl-id: be413905-0631-4229-a954-80a92651206d
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '1619'
ht-degree: 4%

---

# 测试历程{#testing_the_journey}


>[!CAUTION]
>
>**正在查找Adobe Journey Optimizer**？ 单击[此处](https://experienceleague.adobe.com/zh-hans/docs/journey-optimizer/using/ajo-home){target="_blank"}获取Journey Optimizer文档。
>
>
>_本文档参考已被Journey Optimizer替换的旧版Journey Orchestration资料。 如果您对访问Journey Orchestration或Journey Optimizer有任何疑问，请联系您的帐户团队。_


在能够测试历程之前，您必须解决所有错误（如果有）。 请参阅[此小节](../about/troubleshooting.md#section_h3q_kqk_fhb)。

您可以在发布历程之前使用测试用户档案测试历程。 这使您可以分析个人如何在历程中流动，并在发布前进行故障排除。

只有测试配置文件才能进入处于测试模式的历程。 您可以创建新的测试配置文件，或将现有配置文件转换为测试配置文件。 请参阅此[章节](../building-journeys/creating-test-profiles.md)。

要使用测试模式，请执行以下步骤：

1. 在测试旅程之前，请验证其是否有效以及是否没有错误。 您将无法启动出现错误的历程测试。 请参阅[此部分](../about/troubleshooting.md#section_h3q_kqk_fhb)。 出现错误时，将显示警告符号。

1. 要激活测试模式，请单击右上角的&#x200B;**[!UICONTROL Test]**&#x200B;切换开关。

   ![](../assets/journeytest1.png)

1. 使用左下角的&#x200B;**[!UICONTROL Wait time]**&#x200B;参数定义每个等待活动和事件超时在测试模式下的停留时间。 等待和事件超时的默认时间为10秒。 这将确保您快速获得测试结果。 仅当您在历程中删除一个或多个等待活动时，才会显示此参数。

   ![](../assets/journeytest_wait.png)

   >[!NOTE]
   >
   >当在历程中使用具有超时的反应事件时，等待时间的默认值和最小值为40秒。 请参阅[此小节](../building-journeys/reaction-events.md)。

1. 单击&#x200B;**[!UICONTROL Trigger an event]**&#x200B;配置事件并将其发送到历程。

   ![](../assets/journeyuctest1.png)

1. 配置所需的不同字段。 在&#x200B;**配置文件标识符**&#x200B;字段中，输入用于标识测试配置文件的字段的值。 例如，它可以是电子邮件地址。 确保发送与测试用户档案相关的事件。 请参阅[触发您的事件](#firing_events)。

   ![](../assets/journeyuctest1-bis.png)

1. 收到事件后，单击&#x200B;**[!UICONTROL Show log]**&#x200B;按钮查看测试结果并进行验证。 请参阅[查看日志](#viewing_logs)。

   ![](../assets/journeyuctest2.png)

1. 如果有任何错误，请取消激活测试模式，修改历程并再次进行测试。当测试得出结果时，您可以发布旅程。 请参阅[此页](../building-journeys/publishing-the-journey.md)。

## 重要说明 {#important_notes}

* 提供了一个界面来触发已测试历程的事件，但事件也可以由第三方系统(如Postman)发送。
* 只有在Real-time Customer Profile Service中标记为“测试配置文件”的个人才能进入测试历程。 请参阅此[章节](../building-journeys/creating-test-profiles.md)。
* 测试模式仅适用于使用命名空间的草稿历程。 测试模式需要检查进入旅程的人员是否为测试用户档案，因此必须能够访问Adobe Experience Platform。
* 在测试会话期间可进入历程的测试用户档案的最大数量为100。
* 禁用测试模式时，它会从过去进入该模式或当前进入该模式的所有人员中清空历程。 它还会清除报表。
* 您可以根据需要多次启用/禁用测试模式。
* 激活测试模式后，您无法修改历程。 在测试模式下时，您可以直接发布历程，而无需先停用测试模式。
* 在达到拆分时，始终选择顶部分支。 如果希望测试选择其他路径，可以重新组织拆分分支的位置。
* 为优化性能并防止使用过时资源，所有处于测试模式且一周内未触发的历程都将切换回草稿状态。

## 将配置文件转换为测试配置文件{#turning-profile-into-test}

您可以将现有配置文件转换为测试配置文件。 在Adobe Experience Platform中，您可以通过API调用更新用户档案属性，但无法通过界面执行此操作。

最简单的方法是使用&#x200B;**更新配置文件**&#x200B;操作活动，并将测试配置文件布尔字段从false更改为true。 请参阅[此小节](../building-journeys/update-profiles.md#using-the-test-mode)。

## 创建测试用户档案{#create-test-profile}

如果要创建新的测试用户档案，此过程与在Adobe Experience Platform中创建用户档案时相同。 它是通过API调用执行的。 查看此[页面](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hans)

您必须使用包含“配置文件测试详细信息”mixin的配置文件架构。 testProfile标志是此mixin的一部分。

创建配置文件时，请确保传递值： testProfile = true。

请注意，您还可以更新现有配置文件，将其testProfile标志更改为“true”。

以下是创建测试用户档案的API调用示例：

```
curl -X POST \
'https://dcs.adobedc.net/collection/xxxxxxxxxxxxxx' \
-H 'Cache-Control: no-cache' \
-H 'Content-Type: application/json' \
-H 'Postman-Token: xxxxx' \
-H 'cache-control: no-cache' \
-H 'x-api-key: xxxxx' \
-H 'x-gw-ims-org-id: xxxxx' \
-d '{
"header": {
"msgType": "xdmEntityCreate",
"msgId": "xxxxx",
"msgVersion": "xxxxx",
"xactionid":"xxxxx",
"datasetId": "xxxxx",
"imsOrgId": "xxxxx",
"source": {
"name": "Postman"
},
"schemaRef": {
"id": "https://example.adobe.com/mobile/schemas/xxxxx",
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"body": {
"xdmMeta": {
"schemaRef": {
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"xdmEntity": {
"_id": "xxxxx",
"_mobile":{
"ECID": "xxxxx"
},
"testProfile":true
}
}
}'
```

## 触发您的事件 {#firing_events}

使用&#x200B;**[!UICONTROL Trigger an event]**&#x200B;按钮可配置使人员进入历程的事件。

>[!NOTE]
>
>在测试模式下触发事件时，将生成一个实际事件，这意味着该事件还将点击侦听此事件的其他历程。

作为先决条件，您必须知道哪些配置文件在Adobe Experience Platform中标记为测试配置文件。 事实上，测试模式仅在历程中允许这些用户档案，并且事件必须包含ID。 预期ID取决于事件配置。 例如，它可以是ECID或电子邮件地址。 需要将此键的值添加到&#x200B;**配置文件标识符**&#x200B;字段中。

>[!NOTE]
>
>对于需要枚举的字段，将显示下拉列表。 只需选择一个可用值。

如果您的历程包含多个事件，请使用下拉列表选择一个事件。然后，对于每个事件，配置传递的字段以及事件发送的执行。 界面可帮助您在事件有效载荷中传递正确的信息并确保信息类型正确无误。 测试模式会保存测试会话中使用的最后一个参数以供将来使用。

![](../assets/journeytest4.png)

利用接口，可传递简单的事件参数。 如果要在事件中传递集合或其他高级对象，则可以单击&#x200B;**[!UICONTROL Code View]**&#x200B;查看有效负载的整个代码并对其进行修改。 例如，您可以复制并粘贴技术用户准备的事件信息。

![](../assets/journeytest5.png)

技术用户还可以使用此界面来撰写事件负载和触发事件，而无需使用第三方工具。

单击&#x200B;**[!UICONTROL Send]**&#x200B;按钮后，测试将开始。 个人在历程中的进度由视觉流表示。 当个人在历程中移动时，路径将逐渐变为绿色。 如果发生错误，则会在相应的步骤上显示警告符号。 您可以将光标放在错误上以显示有关错误的更多信息，并访问完整的详细信息（如果可用）。

![](../assets/journeytest6.png)

当您在事件配置屏幕中选择不同的测试用户档案并再次运行测试时，可视流将被清除并显示新用户的路径。

在测试中打开历程时，显示的路径对应于上次执行的测试。

无论事件是通过界面还是外部(例如，使用Postman)触发，可视流均起作用。

## 基于规则的历程的测试模式 {#test-rule-based}

测试模式也可用于使用基于规则的事件的历程。 有关基于规则的事件的详细信息，请参阅[此页面](../event/about-events.md)。

触发事件时，**事件配置**&#x200B;屏幕允许您定义要在测试中传递的事件参数。 您可以单击右上角的工具提示图标来查看事件ID条件。 作为规则评估一部分的每个字段旁边还提供了工具提示。

![](../assets/alpha-event8.png)

有关如何使用测试模式的详细信息，请参阅[此页面](../building-journeys/testing-the-journey.md)。

## 查看日志 {#viewing_logs}

**[!UICONTROL Show log]**&#x200B;按钮允许您查看测试结果。 此页面以JSON格式显示历程的当前信息。 使用按钮可复制整个节点。 您需要手动刷新页面以更新历程的测试结果。

![](../assets/journeytest3.png)

>[!NOTE]
>
>在测试日志中，如果在调用第三方系统（数据源或操作）时出错，则显示错误代码和错误响应。

将显示历程中当前存在的个人（技术上称为实例）的数量。 以下是为每个人显示的有用信息：

* _Id_：历程中个人的内部ID。 这可用于调试目的。
* _currentstep_：个人在历程中的步骤。 我们建议向您的活动添加标签以更轻松地对其进行识别。
* _currentstep_ >阶段：个人历程的状态（正在运行、已完成、出错或超时）。 有关详细信息，请参阅下文。
* _currentstep_ > _extraInfo_：错误的描述和其他上下文信息。
* _currentstep_ > _fetchErrors_：有关在此步骤中发生的数据错误的获取信息。
* _externalKeys_：事件中定义的键公式的值。
* _扩充数据_：如果历程使用数据源，则历程已检索的数据。
* _transitionHistory_：个人执行的步骤列表。 对于事件，将显示有效负载。
* _actionExecutionErrors_ ：有关所发生错误的信息。

以下是个人旅程的不同状态：

* _正在运行_：个人当前正在历程中。
* _已完成_：个人已到达历程的结尾。
* _错误_：个人在历程中因错误而停止。
* _超时_：个人在历程中停止，因为步骤耗时过长。

当使用测试模式触发事件时，将自动使用源名称生成数据集。

当使用测试模式触发事件时，将自动使用源名称生成数据集。

测试模式会自动创建体验事件并将其发送到Adobe Experience Platform。 此体验事件的源名称是“Journey Orchestration测试事件”。
