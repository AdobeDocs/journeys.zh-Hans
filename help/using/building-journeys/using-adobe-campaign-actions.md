---
title: 使用 Adobe Campaign 操作
description: 了解Adobe Campaign操作
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: e353d593ab2710f50a88a3715378c86c2e37b4f6
workflow-type: tm+mt
source-wordcount: '899'
ht-degree: 5%

---


# 使用 Adobe Campaign 操作 {#using_campaign_action}

如果您有Adobe Campaign Standard，可使用以下现成的操作活动: **[!UICONTROL Email]**, **[!UICONTROL Push]** 和 **[!UICONTROL SMS]**。

>[!NOTE]
>
>为此，您需要配置内置操作。 请参见[此页面](../action/working-with-adobe-campaign.md)。

对于这些渠道，您选择一个Adobe Campaign Standard事务消息 **模板**。 事实上， [!DNL Journey Orchestration] 这并不是传递解决方案的信息。 对于内置电子邮件、短信和推送渠道，我们依靠交易消息来执行消息发送。 这意味着，如果要在旅程中使用特定消息模板，则必须在Adobe Campaign Standard发布该模板。 请参阅 [本页](https://docs.adobe.com/content/help/zh-Hans/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html) ，了解如何使用此功能。

>[!NOTE]
>
>必须发布Campaign Standard事务性消息及其关联事件，才能用于Journey Orchestration。 如果事件已发布，但消息未发布，则Journey Orchestration界面中将不显示该消息。 如果消息已发布，但其关联的事件不可用，则消息将显示在Journey Orchestration界面中，但将不可用。

![](../assets/journey59.png)

您可以使用事件（也称为实时）或用户档案事务消息模板。

>[!NOTE]
>
>当我们发送实时事务性消息(rtEvent)或通过自定义操作与第三方系统发送消息时，对于疲劳、阻止列表或退订管理，需要特定设置。 例如，如果“取消订阅”属性存储在Adobe Experience Platform或第三方系统中，则必须在发送消息之前添加一个条件以检查此条件。

当您选择模板时，消息有效负荷中预期的所有字段将显示在活动配置窗格的和 **[!UICONTROL Address]** 下方 **[!UICONTROL Personalization Data]**。 您需要将每个字段与要使用的字段进行映射，事件或数据源中的字段。 您还可以使用高级表达式编辑器手动传递值，对检索到的信息执行数据处理（例如，将字符串转换为大写），或使用“if, then, else”等函数。 请参阅[此页](../expression/expressionadvanced.md)。

![](../assets/journey60.png)

## 电子邮件和短信 {#section_asc_51g_nhb}

对于 **[!UICONTROL Email]** 和 **[!UICONTROL SMS]**，参数是相同的。

>[!NOTE]
>
>对于电子邮件，如果您使用用户档案事务模板，则退订机制会通过Campaign Standard处理。 您只需在模板 **[!UICONTROL Unsubscription link]** 中添加内容块(了[解更多](https://docs.adobe.com/content/help/zh-Hans/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html))。 如果您使用基于事件的模板(rtEvent)，则需要在邮件中添加一个链接，该链接将人员的电子邮件传递到URL参数并指向退订登陆页。 您需要创建此登陆页，并确保将该人取消订阅的决定传输给Adobe。

首先，您需要选择交易消息模板。 请参见[此页面](../building-journeys/about-action-activities.md)。

提供两个类别: **[!UICONTROL Address]** 和 **[!UICONTROL Personalization Data]**。

您可以使用界面轻松定义 **[!UICONTROL Address]** 检索 **[!UICONTROL Personalization Data]** 位置或位置。 您可以浏览事件和可用数据源的字段。 您还可以使用高级表达式编辑器来处理更高级的用例，如使用需要传递参数或执行操作的数据源。 请参阅[此页](../expression/expressionadvanced.md)。

**[!UICONTROL Address]**

>[!NOTE]
>
>此类别仅在您选择“事件”事务性消息时才可见。 对于“用户档案”消息， **[!UICONTROL Address]** 系统将自动从Adobe Campaign Standard检索该字段。

这些字段是系统需要知道消息的发送位置的字段。 对于电子邮件模板，它是电子邮件地址。 对于SMS，它是手机号码。

![](../assets/journey61.png)

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>您无法在个性化数据中传递集合。 如果交易电子邮件或短信需要集合，则它将不起作用。 另请注意，个性化数据具有预期的格式(例如：字符串、小数等)。 必须注意遵守这些预期格式。

这些是Adobe Campaign Standard消息应用的字段。 这些字段可用于个性化消息、应用条件格式或选择特定消息变体。

![](../assets/journey62.png)

## 推送 {#section_im3_hvf_nhb}

在使用推送活动之前，您的移动应用程序需要配置Campaign Standard以发送推送通知。 请阅读 [本文](https://helpx.adobe.com/cn/campaign/kb/integrate-mobile-sdk.html) ，为移动设备采取必要的实施步骤。

首先，您需要从下拉列表和事务性消息中选择移动应用程序。 请参阅[此页](../building-journeys/about-action-activities.md)。

![](../assets/journey62bis.png)

提供两个类别: **[!UICONTROL Target]** 和 **[!UICONTROL Personalization Data]**。

**[!UICONTROL Target]**

>[!NOTE]
>
>此类别仅在您选择事件消息时才可见。 对于用户档案消息， **[!UICONTROL Target]** 系统使用Adobe Campaign Standard执行的协调自动检索字段。

在本节中，您需要定义 **[!UICONTROL Push platform]**。 下拉列表允许您选择( **[!UICONTROL Apple Push Notification Server]** iOS)或( **[!UICONTROL Firebase Cloud Messaging]** Android)。 您也可以从事件或数据源中选择特定字段，或定义高级表达式。

您还需要定义 **[!UICONTROL Registration Token]**。 表达式取决于事件有效负荷或其他信息中如何定义令牌 [!DNL Journey Orchestration] 。 它可以是简单字段或更复杂的表达式，以防令牌在集合中定义，例如：

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>您无法在个性化数据中传递集合。 如果交易推送需要集合，则它将不起作用。 另请注意，个性化数据具有预期的格式(例如：字符串、小数等)。 必须注意遵守这些预期格式。

这些是您的Adobe Campaign Standard消息中使用的事务模板所需的字段。 这些字段可用于个性化您的消息、应用条件格式或选择特定的消息变体。
