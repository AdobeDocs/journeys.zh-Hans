---
product: adobe campaign
solution: Journey Orchestration
title: 使用 Adobe Campaign 操作
description: 了解Adobe Campaign操作
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# 使用 Adobe Campaign 操作 {#using_campaign_action}

如果您有Adobe Campaign Standard，可使用以下现成的操作活动:**[!UICONTROL Email]**、**[!UICONTROL Push]**&#x200B;和&#x200B;**[!UICONTROL SMS]**。

>[!NOTE]
>
>为此，您需要配置内置操作。 请参见[此页面](../action/working-with-adobe-campaign.md)。

对于这些渠道中的每个，您都选择一个Adobe Campaign Standard事务消息&#x200B;**template**。 事实上，[!DNL Journey Orchestration]不是消息发送解决方案。 对于内置电子邮件、短信和推送渠道，我们依靠交易消息来执行消息发送。 这意味着，如果要在旅程中使用特定消息模板，则必须在Adobe Campaign Standard发布该模板。 请参阅[此页](https://docs.adobe.com/content/help/zh-Hans/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)以了解如何使用此功能。

>[!NOTE]
>
>必须发布Campaign Standard事务性消息及其关联事件，才能用于Journey Orchestration。 如果事件已发布，但消息未发布，则Journey Orchestration界面中将不显示该消息。 如果消息已发布，但其关联的事件不可用，则消息将显示在Journey Orchestration界面中，但将不可用。

![](../assets/journey59.png)

您可以使用事件（也称为实时）或用户档案事务消息模板。

>[!NOTE]
>
>当我们发送实时事务性消息(rtEvent)或通过自定义操作与第三方系统发送消息时，对于疲劳、阻止列表或退订管理，需要特定设置。 例如，如果“取消订阅”属性存储在Adobe Experience Platform或第三方系统中，则必须在发送消息之前添加一个条件以检查此条件。

选择模板后，消息有效负荷中预期的所有字段都会显示在&#x200B;**[!UICONTROL Address]**&#x200B;和&#x200B;**[!UICONTROL Personalization Data]**&#x200B;下的活动配置窗格中。 您需要将每个字段与要使用的字段进行映射，事件或数据源中的字段。 您还可以使用高级表达式编辑器手动传递值，对检索到的信息执行数据处理（例如，将字符串转换为大写），或使用“if, then, else”等函数。 请参阅[此页](../expression/expressionadvanced.md)。

![](../assets/journey60.png)

## 电子邮件和SMS {#section_asc_51g_nhb}

对于&#x200B;**[!UICONTROL Email]**&#x200B;和&#x200B;**[!UICONTROL SMS]**，参数相同。

>[!NOTE]
>
>对于电子邮件，如果您使用用户档案事务模板，则退订机制会通过Campaign Standard处理。 您只需在模板中添加&#x200B;**[!UICONTROL Unsubscription link]**&#x200B;内容块（[了解更多](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html)）。 如果您使用基于事件的模板(rtEvent)，则需要在邮件中添加一个链接，该链接将人员的电子邮件传递到URL参数并指向退订登陆页。 您需要创建此登陆页，并确保将该人取消订阅的决定传输给Adobe。

首先，您需要选择交易消息模板。 请参见[此页面](../building-journeys/about-action-activities.md)。

提供两个类别:**[!UICONTROL Address]**&#x200B;和&#x200B;**[!UICONTROL Personalization Data]**。

您可以使用接口轻松定义检索&#x200B;**[!UICONTROL Address]**&#x200B;或&#x200B;**[!UICONTROL Personalization Data]**&#x200B;的位置。 您可以浏览事件和可用数据源的字段。 您还可以使用高级表达式编辑器来处理更高级的用例，如使用需要传递参数或执行操作的数据源。 请参阅[此页](../expression/expressionadvanced.md)。

**[!UICONTROL Address]**

>[!NOTE]
>
>此类别仅在您选择“事件”事务性消息时才可见。 对于“用户档案”消息，系统会从Adobe Campaign Standard自动检索&#x200B;**[!UICONTROL Address]**&#x200B;字段。

这些字段是系统需要知道消息的发送位置的字段。 对于电子邮件模板，它是电子邮件地址。 对于SMS，它是手机号码。

![](../assets/journey61.png)

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>您无法在个性化数据中传递集合。 如果交易电子邮件或短信需要集合，则它将不起作用。 另请注意，个性化数据具有预期的格式(例如：字符串、小数等)。 必须注意遵守这些预期格式。

这些是Adobe Campaign Standard消息应用的字段。 这些字段可用于个性化消息、应用条件格式或选择特定消息变体。

![](../assets/journey62.png)

## 推送{#section_im3_hvf_nhb}

在使用推送活动之前，您的移动应用程序需要配置Campaign Standard以发送推送通知。 使用此[文章](https://helpx.adobe.com/cn/campaign/kb/integrate-mobile-sdk.html)为移动设备执行必要的实施步骤。

首先，您需要从下拉列表和事务性消息中选择移动应用程序。 请参阅[此页](../building-journeys/about-action-activities.md)。

![](../assets/journey62bis.png)

提供两个类别:**[!UICONTROL Target]**&#x200B;和&#x200B;**[!UICONTROL Personalization Data]**。

**[!UICONTROL Target]**

>[!NOTE]
>
>此类别仅在您选择事件消息时才可见。 对于用户档案消息，系统使用Adobe Campaign Standard执行的协调自动检索&#x200B;**[!UICONTROL Target]**&#x200B;字段。

在本节中，您需要定义&#x200B;**[!UICONTROL Push platform]**。 下拉列表允许您选择&#x200B;**[!UICONTROL Apple Push Notification Server]**(iOS)或&#x200B;**[!UICONTROL Firebase Cloud Messaging]**(Android)。 您也可以从事件或数据源中选择特定字段，或定义高级表达式。

您还需要定义&#x200B;**[!UICONTROL Registration Token]**。 表达式取决于事件有效负荷或其他[!DNL Journey Orchestration]信息中如何定义令牌。 它可以是简单字段或更复杂的表达式，以防令牌在集合中定义，例如：

```
@{Event_push._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
```

**[!UICONTROL Personalization Data]**

>[!NOTE]
>
>您无法在个性化数据中传递集合。 如果交易推送需要集合，则它将不起作用。 另请注意，个性化数据具有预期的格式(例如：字符串、小数等)。 必须注意遵守这些预期格式。

这些是您的Adobe Campaign Standard消息中使用的事务模板所需的字段。 这些字段可用于个性化您的消息、应用条件格式或选择特定的消息变体。
