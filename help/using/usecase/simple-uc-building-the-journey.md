---
title: 构建旅程
description: 了解如何构建简单的使用案例旅程
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# 构建旅程{#concept_eyw_mcy_w2b}

商 **业用户** ，现在可以构建旅程。 我们的旅程将仅包含一条路径，其中包含以下活动：

* “SpaBeacon” **[!UICONTROL Event]**:当一个人在spa信标附近走路时，系统将收到一个活动，然后该人的旅程将开始。
* 检 **[!UICONTROL Condition]**查此人是否是女人的活动
* 活 **[!UICONTROL Email]**动（使用Adobe Campaign Standard）
* 活 **[!UICONTROL End]**动

>[!NOTE]
>
>只有在 **[!UICONTROL Push]**您拥有**[!UICONTROL Email]** Adobe Campaign Standard时，调板中才提供这些和活动。

有关如何构建旅程的其他信息，请参阅 [](../building-journeys/journey.md)。

1. 在顶部菜单中，单击选 **[!UICONTROL Home]**项卡并**[!UICONTROL Create]** 创建新旅程。

   ![](../assets/journey31.png)

1. 在右侧显示的配置窗格中编辑旅程的属性。 我们将它命名为“Spa旅程”，从12月1日到31日，将它设为一个月。

   ![](../assets/journeyuc1_8.png)

1. 从调色板中拖放“SpaBeacon”事件到画布，开始设计您的旅程。 您还可以双击调色板中的事件，将其添加到画布。

   ![](../assets/journeyuc1_9.png)

1. 现在，我们添加一个条件来检查这个人是否是女性。 将条件活动拖放到您的旅程中。

   ![](../assets/journeyuc1_10.png)

1. 选择类 **[!UICONTROL Data Source Condition]**型，然后单击字**[!UICONTROL Expression]** 段。 您还可以定义将显示在画布中箭头上的条件标签。

   ![](../assets/journeyuc1_11.png)

1. 使用简单的表达式编辑器，查找性别字段(_人>性别_)并将其放置到创建以下条件的权限中：&quot;性别等于&quot;女性&quot;。

   ![](../assets/journeyuc1_12.png)

1. 删除活 **[!UICONTROL Email]**动并选择“Spa折扣”交易消息模板。 此模板是使用Adobe Campaign设计的。 Refer to this[page](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

   ![](../assets/journeyuc1_13.png)

1. 在字段内单 **[!UICONTROL Email]**击，然后从数据源中选择电子邮件地址。

   ![](../assets/journeyuc1_14.png)

1. 同样，从数据源中定义名和姓个性化字段。

   ![](../assets/journeyuc1_15.png)

1. 删除活 **[!UICONTROL End]**动。

   ![](../assets/journeyuc1_17.png)

1. 单击此切 **[!UICONTROL Test]**换，并使用测试配置文件测试您的旅程。 如果出现任何错误，请取消激活测试模式，修改您的旅程并再次测试它。 有关测试模式的详细信息，请参阅[](../building-journeys/testing-the-journey.md)。

   ![](../assets/journeyuc1_18bis.png)

1. 当测试确定时，您可以从右上下拉菜单发布您的旅程。

   ![](../assets/journeyuc1_18.png)

下次，当一名女子走在Spa信标附近时，她会立即收到一封个性化的“Spa折扣”电子邮件。
