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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# 构建旅程 {#concept_owm_kdy_w2b}

商 **业用户** ，现在可以构建旅程。 我们的旅程将包括以下活动：

* 两项 **[!UICONTROL Event]**活动：“LobbyBeacon”和“RestaurantBeacon”
* 两个活 **[!UICONTROL Condition]**动
* 三个 **[!UICONTROL Push]**活动和一**[!UICONTROL Email]** 个活动（使用Adobe Campaign Standard）
* 活 **[!UICONTROL Wait]**动
* 四项活 **[!UICONTROL End]**动

>[!NOTE]
>
>只有在 **[!UICONTROL Push]**您拥有**[!UICONTROL Email]** Adobe Campaign Standard时，调板中才提供这些和活动。

有关如何构建旅程的其他信息，请参阅 [](../building-journeys/journey.md)。

## 第一步{#section_ntb_ws1_ffb}

1. 在顶部菜单中，单击选 **[!UICONTROL Home]**项卡并**[!UICONTROL Create]** 创建新旅程。

   ![](../assets/journey31.png)

1. 在右侧显示的配置窗格中编辑旅程的属性。 添加一个名称，并将其设置为1个月，从12月1日至31日。

   ![](../assets/journeyuc2_12.png)

1. 通过将“LobbyBeacon”事件从调色板拖放到画布，开始设计您的旅程。 您还可以双击调色板中的事件，将其添加到画布。

   ![](../assets/journeyuc2_13.png)

1. 现在，我们添加一个条件来检查此人在过去24小时内是否未联系过，并检查他是否是忠诚会员。 将条件活动拖放到您的旅程中。

   ![](../assets/journeyuc2_14.png)

1. 选择类 **[!UICONTROL Data Source Condition]**型，然后单击字**[!UICONTROL Expression]** 段。 您还可以定义将显示在画布中箭头上的条件标签。 在我们的示例中，我们将“条件1”替换为“忠诚会员”。

   ![](../assets/journeyuc2_15.png)

1. 单 **[!UICONTROL Advanced mode]**击并根据来自Experience Platform数据源的“timestamp”和“directMarketing.sends.value”字段定义以下条件。 表达式的语法为：

   ```
   count(#{ExperiencePlatformDataSource.MarltonExperience.experienceevent.all(
       currentDataPackField.directMarketing.sends.value > 0 and
       currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
   and
       #{ExperiencePlatformDataSource.MarltonProfiles.Profile._customer.marlton.loyaltyMember}
   ```

   ![](../assets/journeyuc2_30.png)

1. 单击该 **[!UICONTROL Add a path]**按钮，为过去24小时内尚未联系且不是忠诚度会员的客户创建第二个路径。 将路径命名为“非忠诚度会员”。 表达式的语法为：

   ```
   count(#{ExperiencePlatformDataSource.MarltonExperience.experienceevent.all(
       currentDataPackField.directMarketing.sends.value > 0 and
       currentDataPackField.timestamp > nowWithDelta(-1, "days").timestamp}) == 0
   and not
       #{ExperiencePlatformDataSource.MarltonProfiles.Profile._customer.marlton.loyaltyMember}
   ```

   >[!NOTE]
   >
   >在表达式的第二部分，“Profile”是可选的。

1. 我们需要选择一个命名空间。 将根据架构属性预先选择命名空间。 您可以保持预选。 有关命名空间的详细信息，请参 [](../event/selecting-the-namespace.md)阅。

在我们的使用情况下，我们只希望对这两种情况做出反应，因此我们不选中该框 **[!UICONTROL Show path for other cases than the one(s) above]**。

在条件之后将创建两个路径：

* _过去24小时内未联系过且是忠诚会员的客户。_
* _过去24小时内未联系过且不是忠诚会员的客户。_

![](../assets/journeyuc2_16.png)

## 第一条路径：客户是忠诚会员 {#section_otb_ws1_ffb}

1. 在第一条路径中，我们添加一个条件来检查他是否有预订。 将条件活动拖放到您的旅程中。

   ![](../assets/journeyuc2_17.png)

1. 选择类 **[!UICONTROL Data Source Condition]**型，并根据从保留系统检索到的保留状态信息来定义条件：

   ```
   #{MarltonReservation.MarltonFieldGroup.reservation} == true
   ```

   ![](../assets/journeyuc2_18.png)

1. 当您从外部数据源中选择字段时，屏幕的右侧部分将显示配置外部数据源时定义的参数列表(请参阅 [](../usecase/configuring-the-data-sources.md))。 单击参数名称并定义保留系统密钥的值，即Experience Cloud ID，在我们的示例中：

   ```
   @{LobbyBeacon.endUserIDs._experience.mcid.id}
   ```

   ![](../assets/journeyuc2_19.png)

1. 由于我们还想对没有预订的客户做出反应，因此我们需要选中此复选框 **[!UICONTROL Show path for other cases than the one(s) above]**。

   ![](../assets/journeyuc2_20.png)

   创建了两个路径：

   * _预订了房间的客户_
   * _未预定房间的客户。_
   ![](../assets/journeyuc2_21.png)

1. 在第一个路径（预订房间数）中，删除活 **[!UICONTROL Push]**动，选择您的移动应用程序和“欢迎”模板。

   ![](../assets/journeyuc2_22.png)

1. 定义系 **[!UICONTROL Target]**统发送推送所需的字段。

   * **[!UICONTROL Push platform]**:选择平台：(**[!UICONTROL Apple Push Notification Server]** Apple)或 **[!UICONTROL Firebase Cloud Messaging]**(Android)。
   * **[!UICONTROL Registration token]**:使用高级模式添加以下表达式（基于已配置的事件）:

      ```
      @{LobbyBeacon._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
      ``
      
1. 定义推送通知个性化字段。 在我们的示例中：名字和姓氏。

1. 添加“RestaurantBeacon”事件。

   ![](../assets/journeyuc2_23.png)

1. 添加新活 **[!UICONTROL Push]**动，选择“餐费折扣”模板并定义**[!UICONTROL Address]** 和字 **[!UICONTROL Personalization]**段。 添加活**[!UICONTROL End]** 动。

   ![](../assets/journeyuc2_24.png)

1. 我们希望仅当客人在欢迎推送后的6小时内进入餐厅时，才发送餐点折扣推送通知。 为此，我们需要使用等待活动。 将光标放在欢迎推送活动上并单击“+”符号。 在新路径中，添加等待活动并定义6小时的持续时间。 将选择第一个符合条件的活动。 如果在欢迎推送后不到6小时收到餐馆活动，则发送推送活动。 如果未来6小时内未收到餐馆活动，则选择等待。 在等待 **[!UICONTROL End]**活动之后放置活动。

   ![](../assets/journeyuc2_31.png)

1. 在遵循预订条件（未预订房间）的第二个路径中，添加一个活 **[!UICONTROL Push]**动并选择您的“房费”模板。 添加活**[!UICONTROL End]** 动。

   ![](../assets/journeyuc2_25.png)

## 第二条路径：客户不是忠诚会员{#section_ptb_ws1_ffb}

1. 在遵循第一个条件（客户不是忠诚度会员）的第二个路径中，添加活 **[!UICONTROL Email]**动并选择“忠诚度会员资格”模板。

   ![](../assets/journeyuc2_26.png)

1. 在字段 **[!UICONTROL Address]**中，从数据源中选择电子邮件地址。

   ![](../assets/journeyuc2_27.png)

1. 从数据源定义名和姓个性化字段。

   ![](../assets/journeyuc2_28.png)

1. 添加活 **[!UICONTROL End]**动。

单击切换 **[!UICONTROL Test]**按钮并测试您的旅程。 如果出现任何错误，请取消激活测试模式，修改您的旅程并再次测试它。 有关测试模式的详细信息，请参阅[](../building-journeys/testing-the-journey.md)。

![](../assets/journeyuc2_32bis.png)

当测试确定时，您可以从右上下拉菜单发布您的旅程。

![](../assets/journeyuc2_32.png)
