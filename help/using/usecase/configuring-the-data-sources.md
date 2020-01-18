---
title: 配置数据源
description: 了解如何为旅程高级用例配置数据源
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


# 配置数据源 {#concept_vml_hdy_w2b}

在我们的使用案例中，我们希望将个性化数据用于我们的消息。 我们还需要检查此人是否是忠诚会员，并且在过去24小时内尚未联系到他。 此信息存储在实时客户档案数据库中。 技术 **用户需要配置** Experience Platform数据源以检索这些字段。

有关数据源配置的其他信息，请参阅 [](../datasource/about-data-sources.md)。

1. 在顶部菜单中，单击选 **[!UICONTROL Data Sources]**项卡，然后选择内置Experience Platform数据源。

   ![](../assets/journey23.png)

1. 在预配置的组字段中，检查是否选择了以下字段：

   * _person > name > firstName_
   * _person > name > lastName_
   * _personalEmail >地址_

1. 单击 **[!UICONTROL Add a New Field Group]**，选择一个**[!UICONTROL Profiles]** 架构，然后为我们的条件添 **加忠诚度成员** (Loyalty member)字段。 “忠 **诚度成员** ”字段是自定义字段，已添加到XDM中：&quot;_customer > marlton > loyaltyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. 单 **[!UICONTROL Add a New Field Group]**击，选择一个**[!UICONTROL ExperienceEvent]** 架构，然后根据给定时间段内发送的消息数选择我们的条件所需的字段：date和 _directMarketing_ > sends > value __ for the messages sented.

   ![](../assets/journeyuc2_7.png)

1. 单击 **[!UICONTROL Save]**.

我们还需要检查该人在酒店预订系统中是否有预订。 技 **术用户需要配置** 第二个数据源来检索此字段。

1. 在数据源列表中，单击以 **[!UICONTROL Add]**添加新的外部数据源以定义与酒店预订系统的连接。

   ![](../assets/journeyuc2_9.png)

1. 输入数据源的名称和外部服务的URL，例如： _https://marlton.com/reservation_

   >[!CAUTION]
   >
   >出于安全原因，我们强烈建议使用HTTPS。

1. 根据外部服务配置配置身份验证： **[!UICONTROL No authentication]**、**[!UICONTROL Basic]****[!UICONTROL Custom]**或**[!UICONTROL API key]**。 在我们的示例中，我们为类型选择“基本”，并为API调用指定用户名和密码。

   ![](../assets/journeyuc2_10.png)

1. 单 **[!UICONTROL Add a New Field Group]**击以定义要检索的信息和API参数。 对于我们的示例，只有一个参数(id)，因此我们需要创建一个包含以下信息的字段组：

   * **[!UICONTROL Method]**:选择POST或GET方法。 在我们的例子中，我们选择GET方法。
   * **[!UICONTROL Cache duration]**:这会因API调用的频率而异。 在我们的情况下，预订系统每10分钟更新一次。
   * **[!UICONTROL Response Payload]**:在字段内单**[!UICONTROL Payload]** 击并粘贴有效负荷的示例。 验证字段类型是否正确。 每次调用API时，系统都将检索有效负荷示例中包含的所有字段。 在我们的示例中，有效负荷仅包含保留状态：

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamic Values]**:输入与用于标识每个客户的键相对应的参数，在我们的示例中为“id”。 此参数的值将在旅程中定义。
   ![](../assets/journeyuc2_11.png)

1. 单击 **[!UICONTROL Save]**.

   数据源现已配置好，可在您的旅程中使用。
