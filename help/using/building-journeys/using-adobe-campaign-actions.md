---
title: 使用Adobe Campaign操作
description: 了解Adobe Campaign操作
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# 使用Adobe Campaign操作 {#using_campaign_action}

如果您有Adobe Campaign Standard，则可以执行以下现成操作： **[!UICONTROL Email]**和**[!UICONTROL Push]****[!UICONTROL SMS]**。

>[!NOTE]
>
>为此，您需要配置内置操作。 请参阅[](../action/working-with-adobe-campaign.md)。

对于每个渠道，您都可以选择Adobe Campaign Standard交易消息传递 **模板**。 事实上，旅程编排不是发送信息的解决方案。 对于内置电子邮件、短信和推送渠道，我们依靠交易消息来执行消息发送。 这意味着，如果要在旅程中使用某个消息模板，则必须在Adobe Campaign standard中发布该模板。 请参阅本 [页](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html) ，了解如何使用此功能。

![](../assets/journey59.png)

您可以使用活动（也称为实时）或个人资料事务消息传递模板。

>[!NOTE]
>
>当我们发送实时交易消息(rtEvent)或通过自定义操作与第三方系统发送消息时，对于疲劳、黑名单或取消订阅管理，需要特定设置。 例如，如果“黑名单”或“取消订阅”属性存储在平台或第三方系统中，则必须在发送消息之前添加一个条件以检查此条件。

当您选择模板时，消息有效负荷中所需的所有字段将显示在和下的活动配置窗格 **[!UICONTROL Address]**中**[!UICONTROL Personalization Data]**。 您需要将每个字段与要使用的字段进行映射，无论是从事件还是从数据源。 您还可以使用高级表达式编辑器手动传递值，对检索到的信息执行数据处理（例如，将字符串转换为大写），或使用“if, then, else”等函数。 请参见 [](../expression/expressionadvanced.md)。

![](../assets/journey60.png)

## 电子邮件和短信 {#section_asc_51g_nhb}

对于 **[!UICONTROL Email]**和**[!UICONTROL SMS]**，参数是相同的。

>[!NOTE]
>
>对于电子邮件，如果您使用配置文件事务模板，取消订阅机制将由Campaign standard现成处理。 您只需在模板 **[!UICONTROL Unsubscription link]**中添加内容块(了[解更多](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html))。 如果您使用基于事件的模板(rtEvent)，则需要在邮件中添加一个链接，该链接将人员的电子邮件传递到URL参数中并指向取消订阅的登录页面。 您需要创建此登录页面，并确保将该人取消订阅的决定传输到Adobe。

首先，您需要选择交易消息模板。 请参见 [](../building-journeys/about-action-activities.md)。

有两种类别可用： **[!UICONTROL Address]**和**[!UICONTROL Personalization Data]**。

您可以轻松定义检索位置或使用 **[!UICONTROL Address]**该界**[!UICONTROL Personalization Data]** 面的位置。 您可以浏览事件和可用数据源的字段。 您还可以使用高级表达式编辑器处理更高级的用例，如使用需要传递参数或执行操作的数据源。 请参见 [](../expression/expressionadvanced.md)。

**[!UICONTROL Address]**

>[!NOTE]
>
>仅当您选择“事件”事务消息时，此类别才可见。 对于“配置文件”消息， **[!UICONTROL Address]**系统会从Adobe Campaign standard自动检索该字段。

这些字段是系统需要知道消息发送位置的字段。 对于电子邮件模板，它是电子邮件地址。 对于SMS，这是手机号码。

![](../assets/journey61.png)

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>您无法在个性化数据中传递集合。 如果交易电子邮件或短信需要集合，则它将无法正常工作。 另请注意，个性化数据具有预期的格式(例如：字符串、小数等)。 您必须注意遵守这些预期格式。

这些是Adobe Campaign standard消息应用的字段。 这些字段可用于个性化消息、应用条件格式或选择特定消息变体。

![](../assets/journey62.png)

## 推送 {#section_im3_hvf_nhb}

在使用推送活动之前，您的移动应用程序需要与Campaign standard一起配置以发送推送通知。 阅读本 [文](https://helpx.adobe.com/campaign/kb/integrate-mobile-sdk.html) ，为移动设备采取必要的实施步骤。

首先，您需要从下拉列表中选择一个移动应用程序并生成一条交易消息。 请参见 [](../building-journeys/about-action-activities.md)。

![](../assets/journey62bis.png)

有两种类别可用： **[!UICONTROL Target]**和**[!UICONTROL Personalization Data]**。

**[!UICONTROL Target]**

>[!NOTE]
>
>仅当您选择活动消息时，此类别才可见。 对于配置文件消 **[!UICONTROL Target]**息，系统会使用Adobe Campaign standard执行的对帐功能自动检索字段。

在本节中，您需要定义 **[!UICONTROL Push platform]**。 下拉列表允许您选择(iOS)**[!UICONTROL Apple Push Notification Server]** 或( **[!UICONTROL Firebase Cloud Messaging]**Android)。 您也可以从事件或数据源中选择特定字段，或定义高级表达式。

您还需要定义 **[!UICONTROL Registration Token]**。 表达式取决于在事件有效负荷或其他旅程安排信息中定义令牌的方式。 它可以是简单字段或更复杂的表达式，以防令牌在代码集中定义：

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>您无法在个性化数据中传递集合。 如果交易推送期望集合，则它将不起作用。 另请注意，个性化数据具有预期的格式(例如：字符串、小数等)。 您必须注意遵守这些预期格式。

这些字段是Adobe Campaign standard消息中使用的事务模板所需的字段。 这些字段可用于个性化您的消息、应用条件格式或选择特定的消息变体。
