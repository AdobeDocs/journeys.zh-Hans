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
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 4%

---


# 构建旅程{#concept_eyw_mcy_w2b}

商 **业用户** 现在可以构建旅程。 我们的旅程将仅包含一条包含以下活动的路径：

* “SpaBeacon” **[!UICONTROL Event]**: 当一个人在spa信标附近走路时，系统将收到事件，而旅程将为该人开始。
* 一 **[!UICONTROL Condition]** 名活动，检查此人是否是女人
* 活动( **[!UICONTROL Email]** 使用Adobe Campaign Standard)
* an **[!UICONTROL End]** activity

>[!NOTE]
>
>只有在 **[!UICONTROL Push]** 您有 **[!UICONTROL Email]** Adobe Campaign Standard时，调色板中才提供这些和活动。

有关如何构建旅程的其他信息，请参阅 [](../building-journeys/journey.md)。

1. 在顶部菜单中，单击 **[!UICONTROL Home]** 选项卡 **[!UICONTROL Create]** 并创建新旅程。

   ![](../assets/journey31.png)

1. 在右侧显示的配置窗格中编辑旅程的属性。 我们将它命名为“Spa旅程”，从12月1日到31日，将它设定为一个月。

   ![](../assets/journeyuc1_8.png)

1. 开始通过将“SpaBeacon”事件从调色板拖放到画布来设计您的旅程。 您还可以多次单击调色板中的事件，将其添加到画布。

   ![](../assets/journeyuc1_9.png)

1. 现在，我们添加一个条件来检查此人是否是女性。 将条件活动拖放到您的旅程中。

   ![](../assets/journeyuc1_10.png)

1. 选择类 **[!UICONTROL Data Source Condition]** 型，然后在字段中 **[!UICONTROL Expression]** 单击。 您还可以定义将显示在画布中箭头上的条件标签。

   ![](../assets/journeyuc1_11.png)

1. 使用简单的表达式编辑器，查找性别字段(_人>性别_)并将其放在创建以下条件的权限下： &quot;性别等于&quot;女性&quot;。

   ![](../assets/journeyuc1_12.png)

1. 删除活动 **[!UICONTROL Email]** 并选择“Spa折扣”交易消息模板。 此模板是使用Adobe Campaign设计的。 Refer to this [page](https://docs.adobe.com/content/help/zh-Hans/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

   ![](../assets/journeyuc1_13.png)

1. 在字段内 **[!UICONTROL Email]** 单击，然后从数据源中选择电子邮件地址。

   ![](../assets/journeyuc1_14.png)

1. 同样，从数据源定义名和姓个性化字段。

   ![](../assets/journeyuc1_15.png)

1. 放下 **[!UICONTROL End]** 活动。

   ![](../assets/journeyuc1_17.png)

1. 单击切换 **[!UICONTROL Test]** 按钮，并使用测试用户档案测试您的旅程。 如果出现任何错误，请取消激活测试模式，修改您的旅程并再次测试它。 有关测试模式的详细信息，请参阅 [](../building-journeys/testing-the-journey.md)。

   ![](../assets/journeyuc1_18bis.png)

1. 当测试结果确定时，您可以从右上方的下拉菜单发布您的旅程。

   ![](../assets/journeyuc1_18.png)

下次，当一位女士在Spa信标附近散步时，她会立即收到一封个性化的“Spa折扣”电子邮件。
