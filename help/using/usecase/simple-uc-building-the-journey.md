---
product: adobe campaign
solution: Journey Orchestration
title: 构建旅程
description: 了解如何构建简单的使用案例旅程
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 36%

---


# 构建旅程{#concept_eyw_mcy_w2b}

**业务用户**&#x200B;现在可以构建旅程。我们的旅程将仅包含一条包含以下活动的路径：

* “SpaBeacon” **[!UICONTROL Event]**:当一个人在spa信标附近走路时，系统将收到事件，而旅程将为该人开始。
* 一 **[!UICONTROL Condition]** 名活动，检查此人是否是女人
* 活动( **[!UICONTROL Email]** 使用Adobe Campaign Standard)
* an **[!UICONTROL End]** activity

>[!NOTE]
>
>仅当您具有 Adobe Campaign Standard 时，调色板中才提供 **[!UICONTROL Push]** 和 **[!UICONTROL Email]** 活动。

For additional information on how to build a journey, refer to [this page](../building-journeys/journey.md).

1. 在顶部菜单中，单击&#x200B;**[!UICONTROL Home]**&#x200B;选项卡和&#x200B;**[!UICONTROL Create]**&#x200B;以创建新旅程。

   ![](../assets/journey31.png)

1. 编辑右侧显示的配置窗格中的旅程属性。我们将它命名为“Spa旅程”，从12月1日到31日，将它设定为一个月。

   ![](../assets/journeyuc1_8.png)

1. 开始通过将“SpaBeacon”事件从调色板拖放到画布来设计您的旅程。 您还可以双击调色板中的事件来将其添加到画布。

   ![](../assets/journeyuc1_9.png)

1. 现在，我们添加一个条件来检查此人是否是女性。 将条件活动拖放到旅程中。

   ![](../assets/journeyuc1_10.png)

1. 选择 **[!UICONTROL Data Source Condition]** 类型，然后在 **[!UICONTROL Expression]** 字段中单击。您还可以定义将在画布中的箭头上显示的条件标签。

   ![](../assets/journeyuc1_11.png)

1. 使用简单的表达式编辑器，查找性别字段(_人>性别_)并将其放在创建以下条件的权限下：&quot;性别等于&quot;女性&quot;。

   ![](../assets/journeyuc1_12.png)

1. 删除活动 **[!UICONTROL Email]** 并选择“Spa折扣”交易消息模板。 此模板是使用Adobe Campaign设计的。 Refer to this [page](https://docs.adobe.com/content/help/zh-Hans/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

   ![](../assets/journeyuc1_13.png)

1. Click inside the **[!UICONTROL Email]** field and select the email address from the data source.

   ![](../assets/journeyuc1_14.png)

1. 同样，从数据源定义名和姓个性化字段。

   ![](../assets/journeyuc1_15.png)

1. 放下 **[!UICONTROL End]** 活动。

   ![](../assets/journeyuc1_17.png)

1. 单击切换 **[!UICONTROL Test]** 按钮，并使用测试用户档案测试您的旅程。 如果有任何错误，请取消激活测试模式，修改旅程并再次进行测试。For more information on the test mode, refer to [this page](../building-journeys/testing-the-journey.md).

   ![](../assets/journeyuc1_18bis.png)

1. 当测试得出结果时，您可以从右上方的下拉菜单发布旅程。

   ![](../assets/journeyuc1_18.png)

下次，当一位女士在Spa信标附近散步时，她会立即收到一封个性化的“Spa折扣”电子邮件。
