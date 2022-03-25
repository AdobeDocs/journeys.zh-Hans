---
product: adobe campaign
title: 使用 Adobe Campaign 操作
description: 了解Adobe Campaign操作
feature: Journeys
role: User
level: Intermediate
exl-id: b2e5c333-d0d8-4fe1-a6b8-5f2e6b3624a4
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 5%

---

# 使用 Adobe Campaign Standard {#using_campaign_action}

如果您拥有Adobe Campaign Standard，则可以使用以下现成的操作活动： **[!UICONTROL Email]**, **[!UICONTROL Push]** 和 **[!UICONTROL SMS]**.

>[!NOTE]
>
>为此，您需要配置内置操作。 请参见[此页面](../action/working-with-adobe-campaign.md)。

对于每个渠道，您都可以选择Adobe Campaign Standard事务型消息传递 **模板**. 的确， [!DNL Journey Orchestration] 不是消息发送解决方案。 对于内置的电子邮件、短信和推送渠道，我们依赖事务型消息传送来执行消息发送。 这意味着如果要在历程中使用特定消息模板，则必须在Adobe Campaign Standard中发布该模板。 请参阅 [本页](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=zh-Hans) 了解如何使用此功能。

>[!NOTE]
>
>必须发布Campaign Standard事务型消息及其关联事件，才能在Journey Orchestration中使用。 如果事件已发布但消息未显示，则该事件将不会显示在Journey Orchestration界面中。 如果消息已发布，但未发布其关联事件，则它将在Journey Orchestration界面中可见，但将不可用。

![](../assets/journey59.png)

您可以使用事件（也称为实时）或用户档案事务型消息传递模板。

>[!NOTE]
>
>当我们发送实时事务型消息(rtEvent)，或通过自定义操作与第三方系统路由消息时，需要设置特定设置才能进行疲劳、阻止列表或退订管理。 例如，如果“取消订阅”属性存储在Adobe Experience Platform或第三方系统中，则必须在发送消息之前添加条件才能检查此条件。

选择模板时，消息有效负荷中预期的所有字段都会显示在活动配置窗格中的活动下方 **[!UICONTROL Address]** 和 **[!UICONTROL Personalization Data]**. 您需要将每个字段与要使用的字段进行映射（来自事件或来自数据源）。 您还可以使用高级表达式编辑器手动传递值，对检索到的信息执行数据操作（例如，将字符串转换为大写），或使用诸如“if， then， else”之类的函数。 请参阅[此页](../expression/expressionadvanced.md)。

![](../assets/journey60.png)

## 电子邮件和短信 {#section_asc_51g_nhb}

对于 **[!UICONTROL Email]** 和 **[!UICONTROL SMS]**，则参数相同。

>[!NOTE]
>
>对于电子邮件，如果您使用用户档案事务型模板，则会通过Campaign Standard即装即用地处理退订机制。 只需添加 **[!UICONTROL Unsubscription link]** 模板中的内容块([了解更多](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html))。 如果您使用基于事件的模板(rtEvent)，则需要在消息中添加一个链接，以在URL参数中传递人员电子邮件并指向退订登陆页面。 您需要创建此登陆页面，并确保将人员取消订阅的决定传输到Adobe。

首先，您需要选择事务型消息传递模板。 请参见[此页面](../building-journeys/about-action-activities.md)。

提供了两个类别： **[!UICONTROL Address]** 和 **[!UICONTROL Personalization Data]**.

您可以轻松定义检索位置 **[!UICONTROL Address]** 或 **[!UICONTROL Personalization Data]** 使用界面。 您可以浏览事件和可用数据源的字段。 您还可以使用高级表达式编辑器来处理更高级的用例，例如使用需要传递参数或执行操作的数据源。 请参阅[此页](../expression/expressionadvanced.md)。

**[!UICONTROL Address]**

>[!NOTE]
>
>仅当您选择“事件”事务型消息时，才会显示此类别。 对于“用户档案”消息， **[!UICONTROL Address]** 字段会由系统自动从Adobe Campaign Standard中检索。

这些是系统需要知道消息发送位置的字段。 对于电子邮件模板，它是电子邮件地址。 对于短信，是手机号码。

![](../assets/journey61.png)

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>您无法在个性化数据中传递集合。 如果事务型电子邮件或短信需要收藏集，则它将不起作用。 另请注意，个性化数据具有预期的格式(示例：字符串、小数等)。 您必须谨慎遵循这些预期格式。

这些是Adobe Campaign Standard消息所需的字段。 这些字段可用于个性化消息、应用条件格式或选择特定消息变体。

![](../assets/journey62.png)

## 推送 {#section_im3_hvf_nhb}

在使用推送活动之前，需要配置您的移动设备应用程序以及Campaign Standard以发送推送通知。 使用 [文章](https://helpx.adobe.com/cn/campaign/kb/integrate-mobile-sdk.html) 为移动设备采取必要的实施步骤。

首先，您需要从下拉列表和事务型消息中选择一个移动设备应用程序。 请参阅[此页](../building-journeys/about-action-activities.md)。

![](../assets/journey62bis.png)

提供了两个类别： **[!UICONTROL Target]** 和 **[!UICONTROL Personalization Data]**.

**[!UICONTROL Target]**

>[!NOTE]
>
>仅当您选择事件消息时，才会显示此类别。 对于用户档案消息， **[!UICONTROL Target]** 字段由系统使用Adobe Campaign Standard执行的协调自动检索。

在此部分中，您需要定义 **[!UICONTROL Push platform]**. 下拉列表允许您选择 **[!UICONTROL Apple Push Notification Server]** (iOS)或 **[!UICONTROL Firebase Cloud Messaging]** (Android)。 您也可以从事件或数据源中选择特定字段，或定义高级表达式。

您还需要定义 **[!UICONTROL Registration Token]**. 表达式取决于令牌在事件有效负载中或在其他 [!DNL Journey Orchestration] 信息。 它可以是一个简单的字段或更复杂的表达式，以防令牌在例如的集合中定义：

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>您无法在个性化数据中传递集合。 如果事务型推送期望收藏集，则它将不起作用。 另请注意，个性化数据具有预期的格式(示例：字符串、小数等)。 您必须谨慎遵循这些预期格式。

这些是Adobe Campaign Standard消息中使用的事务型模板所需的字段。 这些字段可用于个性化您的消息、应用条件格式或选择特定的消息变体。
