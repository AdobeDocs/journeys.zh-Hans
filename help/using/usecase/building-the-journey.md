---
title: 构建旅程
description: '了解如何构建高级用例旅程 '
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
source-git-commit: 771b2b35e0aba412e4eb9e12a5d57de3d4c7068c
workflow-type: tm+mt
source-wordcount: '839'
ht-degree: 1%

---


# 构建旅程 {#concept_owm_kdy_w2b}

商 **业用户** 现在可以构建旅程。 我们的旅程将包括以下活动:

* 两个 **[!UICONTROL Event]** 活动: &quot;LobbyBeacon&quot;和&quot;RestaurantBeacon&quot;
* 两个 **[!UICONTROL Condition]** 活动
* 三名 **[!UICONTROL Push]** 活动和一名 **[!UICONTROL Email]** 活动(使用Adobe Campaign Standard)
* a **[!UICONTROL Wait]** activity
* 四个 **[!UICONTROL End]** 活动

>[!NOTE]
>
>只有在 **[!UICONTROL Push]** 您有 **[!UICONTROL Email]** Adobe Campaign Standard时，调色板中才提供这些和活动。

有关如何构建旅程的其他信息，请参阅 [](../building-journeys/journey.md)。

## 第一步{#section_ntb_ws1_ffb}

1. 在顶部菜单中，单击 **[!UICONTROL Home]** 选项卡 **[!UICONTROL Create]** 并创建新旅程。

   ![](../assets/journey31.png)

1. 在右侧显示的配置窗格中编辑旅程的属性。 添加一个名称，并将其设置为1个月，从12月1日至31日。

   ![](../assets/journeyuc2_12.png)

1. 开始通过将“LobbyBeacon”事件从调色板拖放到画布来设计您的旅程。 您还可以多次单击调色板中的事件，将其添加到画布。

   ![](../assets/journeyuc2_13.png)

1. 现在，我们添加一个条件，检查过去24小时内是否尚未联系到该人，并检查他是否是忠诚会员。 将条件活动拖放到您的旅程中。

   ![](../assets/journeyuc2_14.png)

1. 选择类 **[!UICONTROL Data Source Condition]** 型，然后在字段中 **[!UICONTROL Expression]** 单击。 您还可以定义将显示在画布中箭头上的条件标签。 在我们的示例中，我们将“条件1”替换为“忠诚会员”。

   ![](../assets/journeyuc2_15.png)

1. 单 **[!UICONTROL Advanced mode]** 击并根据来自Adobe Experience Platform数据源的“timestamp”和“directMarketing.sends.value”字段定义以下条件。 表达式的语法为：

   ```
   count(#{ExperiencePlatformDataSource.MarltonExperience.experienceevent.all(
       currentDataPackField.directMarketing.sends.value > 0 and
       currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
   and
       #{ExperiencePlatformDataSource.MarltonProfiles.Profile._customer.marlton.loyaltyMember}
   ```

   ![](../assets/journeyuc2_30.png)

1. 单击该 **[!UICONTROL Add a path]** 按钮，为过去24小时内尚未联系且不是忠诚度会员的客户创建第二个路径。 将路径命名为“不忠诚会员”。 表达式的语法为：

   ```
   count(#{ExperiencePlatformDataSource.MarltonExperience.experienceevent.all(
       currentDataPackField.directMarketing.sends.value > 0 and
       currentDataPackField.timestamp > nowWithDelta(-1, "days").timestamp}) == 0
   and not
       #{ExperiencePlatformDataSource.MarltonProfiles.Profile._customer.marlton.loyaltyMember}
   ```

   >[!NOTE]
   >
   >在表达式的第二部分，“用户档案”是可选的。

1. 我们需要选择命名空间。 根据命名空间属性预先选择模式。 您可以保持该选项处于预选状态。 有关命名空间的详细信息，请参阅 [](../event/selecting-the-namespace.md)。

在我们的使用情况下，我们只希望对这两种情况做出反应，因此我们不要选中该框 **[!UICONTROL Show path for other cases than the one(s) above]**。

在条件之后创建了两个路径：

* _过去24小时内未联系过且是忠诚会员的客户。_
* _过去24小时内未联系过且不是忠诚会员的客户。_

![](../assets/journeyuc2_16.png)

## 第一条路径： 客户是忠诚会员 {#section_otb_ws1_ffb}

1. 在第一条路径中，我们添加一个条件来检查他是否有预订。 将条件活动拖放到您的旅程中。

   ![](../assets/journeyuc2_17.png)

1. 选择类 **[!UICONTROL Data Source Condition]** 型，并根据从保留系统检索的保留状态信息定义条件：

   ```
   #{MarltonReservation.MarltonFieldGroup.reservation} == true
   ```

   ![](../assets/journeyuc2_18.png)

1. 从外部数据源中选择字段时，屏幕的右侧部分显示配置外部数据源时定义的参数列表(请参 [](../usecase/configuring-the-data-sources.md)阅)。 单击参数名称并定义保留系统键的值，即Experience CloudID，在我们的示例中：

   ```
   @{LobbyBeacon.endUserIDs._experience.mcid.id}
   ```

   ![](../assets/journeyuc2_19.png)

1. 由于我们还希望对没有预订的客户做出响应，因此我们需要选中该复选框 **[!UICONTROL Show path for other cases than the one(s) above]**。

   ![](../assets/journeyuc2_20.png)

   创建了两个路径：

   * _预订了房间的客户_
   * _没有预订房间的客户。_

   ![](../assets/journeyuc2_21.png)

1. 在第一条路径（预订的房间）中，删除 **[!UICONTROL Push]** 活动，选择移动应用程序和“欢迎”模板。

   ![](../assets/journeyuc2_22.png)

1. 定义 **[!UICONTROL Target]** 系统发送推送所需的字段。

   * **[!UICONTROL Push platform]**: 选择平台： **[!UICONTROL Apple Push Notification Server]** (Apple)或 **[!UICONTROL Firebase Cloud Messaging]** (Android)。
   * **[!UICONTROL Registration token]**: 使用高级模式添加以下表达式(基于配置的事件):

      ```
      @{LobbyBeacon._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
      ```

1. 定义推送通知个性化字段。 在我们的示例中： 名字和姓氏。

1. 添加“RestaurantBeacon”事件。

   ![](../assets/journeyuc2_23.png)

1. 添加新 **[!UICONTROL Push]** 活动，选择“餐费折扣”模板并定义 **[!UICONTROL Address]** 和字 **[!UICONTROL Personalization]** 段。 添加 **[!UICONTROL End]** 活动。

   ![](../assets/journeyuc2_24.png)

1. 我们希望仅当客人在欢迎推送后的6小时内进入餐厅时发送餐点折扣推送通知。 为此，我们需要使用等待活动。 将光标放在欢迎推送活动上并单击“+”符号。 在新路径中，添加等待活动并定义6小时的持续时间。 将选择第一个符合条件的活动。 如果在欢迎推送后不到6小时收到餐馆事件，则发送推送活动。 如果未来6小时内未收到餐馆事件，则选择等待。 在等待 **[!UICONTROL End]** 活动之后放置活动。

   ![](../assets/journeyuc2_31.png)

1. 在遵循预订条件（未预订房间）的第二个路径中，添加 **[!UICONTROL Push]** 活动并选择“房费”模板。 添加 **[!UICONTROL End]** 活动。

   ![](../assets/journeyuc2_25.png)

## 第二条路径： 客户不是忠诚会员{#section_ptb_ws1_ffb}

1. 在遵循第一个条件（客户不是忠诚度会员）的第二个路径中，添加 **[!UICONTROL Email]** 活动并选择“忠诚度会员资格”模板。

   ![](../assets/journeyuc2_26.png)

1. 在字段 **[!UICONTROL Address]** 中，从数据源中选择电子邮件地址。

   ![](../assets/journeyuc2_27.png)

1. 从数据源定义名和姓个性化字段。

   ![](../assets/journeyuc2_28.png)

1. 添加 **[!UICONTROL End]** 活动。

单击切换 **[!UICONTROL Test]** 并测试您的旅程。 如果出现任何错误，请取消激活测试模式，修改您的旅程并再次测试它。 有关测试模式的详细信息，请参阅 [](../building-journeys/testing-the-journey.md)。

![](../assets/journeyuc2_32bis.png)

当测试结果确定时，您可以从右上方的下拉菜单发布您的旅程。

![](../assets/journeyuc2_32.png)
