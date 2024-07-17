---
product: adobe campaign
title: 构建旅程 — 简单
description: 了解如何构建简单的用例历程
feature: Journeys
role: User
level: Intermediate
exl-id: 22bcd7f4-03ee-4e4c-b221-9f14aeadded6
source-git-commit: 9db330405130b14d1d8a8cbed59f612fd1f6767b
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 36%

---

# 构建历程{#concept_eyw_mcy_w2b}

**业务用户**&#x200B;现在可以构建历程。我们的历程将仅包含一个包含以下活动的路径：

* “SpaBeacon” **[!UICONTROL Event]**：当某人靠近spa信标时，系统将收到一个事件，并将为该人员开始历程。
* **[!UICONTROL Condition]**&#x200B;活动以检查此人是否为女性
* **[!UICONTROL Email]**&#x200B;活动(使用Adobe Campaign Standard)
* **[!UICONTROL End]**&#x200B;活动

>[!NOTE]
>
>仅当您具有 Adobe Campaign Standard 时，调色板中才提供 **[!UICONTROL Push]** 和 **[!UICONTROL Email]** 活动。

有关如何构建历程的其他信息，请参阅[此页面](../building-journeys/journey.md)。

1. 在顶部菜单中，单击&#x200B;**[!UICONTROL Home]**&#x200B;选项卡和&#x200B;**[!UICONTROL Create]**&#x200B;以创建新历程。

   ![](../assets/journey31.png)

1. 编辑右侧显示的配置窗格中的历程属性。我们将其命名为“Spa journey”，并将其设置为持续1个月（从12月1日至31日）。

   ![](../assets/journeyuc1_8.png)

1. 通过将“SpaBeacon”事件从调色板拖放到画布，开始设计历程。 您还可以双击调色板中的事件来将其添加到画布。

   ![](../assets/journeyuc1_9.png)

1. 现在，让我们添加一个条件来检查此人是否为女性。 将条件活动拖放到历程中。

   ![](../assets/journeyuc1_10.png)

1. 选择 **[!UICONTROL Data Source Condition]** 类型，然后在 **[!UICONTROL Expression]** 字段中单击。您还可以定义将在画布的箭头上显示的条件标签。

   ![](../assets/journeyuc1_11.png)

1. 使用简单表达式编辑器，查找性别字段(_person > gender_)，并将其拖放到右侧以创建以下条件：“gender is equal to &quot;Female&quot;。

   ![](../assets/journeyuc1_12.png)

1. 拖放&#x200B;**[!UICONTROL Email]**&#x200B;活动并选择“Spa折扣”事务型消息模板。 此模板是使用Adobe Campaign设计的。 请参阅此[页面](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=zh-Hans)。

   ![](../assets/journeyuc1_13.png)

1. 单击&#x200B;**[!UICONTROL Email]**&#x200B;字段并从数据源中选择电子邮件地址。

   ![](../assets/journeyuc1_14.png)

1. 同样，从数据源定义名字和姓氏个性化字段。

   ![](../assets/journeyuc1_15.png)

1. 删除&#x200B;**[!UICONTROL End]**&#x200B;活动。

   ![](../assets/journeyuc1_17.png)

1. 单击&#x200B;**[!UICONTROL Test]**&#x200B;切换并使用测试配置文件测试您的历程。 如果有任何错误，请取消激活测试模式，修改历程并再次进行测试。有关测试模式的更多信息，请参阅[此页面](../building-journeys/testing-the-journey.md)。

   ![](../assets/journeyuc1_18bis.png)

1. 当测试得出结果时，您可以从右上方的下拉菜单发布历程。

   ![](../assets/journeyuc1_18.png)

下次当一个女人走近水疗信标时，她马上会收到一封“水疗折扣”的个性化电子邮件。
