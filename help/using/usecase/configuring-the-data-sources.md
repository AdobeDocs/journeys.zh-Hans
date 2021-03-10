---
product: adobe campaign
solution: Journey Orchestration
title: 配置数据源
description: 了解如何为旅程高级用例配置数据源
feature: 历程
role: 业务从业者
level: 中间
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 14%

---


# 配置数据源 {#concept_vml_hdy_w2b}

在我们的用例中，我们希望将个性化数据用于我们的消息。 我们还需要检查此人是否是忠诚会员，并且在过去24小时内没有联系到他。 此信息存储在实时客户用户档案数据库中。 **技术用户**&#x200B;需要配置Adobe Experience Platform数据源以检索这些字段。

有关数据源配置的其他信息，请参阅[此页](../datasource/about-data-sources.md)。

1. 在顶部菜单中，单击&#x200B;**[!UICONTROL Data Sources]**&#x200B;选项卡，然后选择内置Adobe Experience Platform数据源。

   ![](../assets/journey23.png)

1. 在预配置的组字段中，检查是否选择了以下字段：

   * _person > name > firstName_
   * _person > name > lastName_
   * _personalEmail >地址_

1. 单击&#x200B;**[!UICONTROL Add a New Field Group]**，选择&#x200B;**[!UICONTROL Profiles]**&#x200B;模式，并添加&#x200B;**Loyalty member**&#x200B;字段作为条件。 **Loyalty成员**&#x200B;字段是自定义字段，已添加到XDM中：&quot;_customer > marlton > loyaltyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. 单击&#x200B;**[!UICONTROL Add a New Field Group]**，选择&#x200B;**[!UICONTROL ExperienceEvent]**&#x200B;模式，然后根据给定时间段内发送的消息数选择我们的条件所需的字段：日期的&#x200B;_timestamp_&#x200B;和&#x200B;_directMarketing >发送> value_&#x200B;以表示发送的邮件数。

   ![](../assets/journeyuc2_7.png)

1. 单击 **[!UICONTROL Save]**.

我们还需要检查该人在酒店预订系统中是否有预订。 **技术用户**&#x200B;需要配置第二个数据源以检索此字段。

1. 在数据源列表中，单击&#x200B;**[!UICONTROL Add]**&#x200B;添加新的外部数据源以定义与酒店预订系统的连接。

   ![](../assets/journeyuc2_9.png)

1. 输入数据源的名称和外部服务的URL，例如：_https://marlton.com/reservation_

   >[!CAUTION]
   >
   >出于安全原因，我们强烈建议使用 HTTPS。

1. 根据外部服务配置以配置身份验证：**[!UICONTROL No authentication]**、**[!UICONTROL Basic]**、**[!UICONTROL Custom]** 或&#x200B;**[!UICONTROL API key]**。在我们的示例中，我们为类型选择“基本”，并为API调用指定用户名和密码。

   ![](../assets/journeyuc2_10.png)

1. 单击&#x200B;**[!UICONTROL Add a New Field Group]**&#x200B;定义要检索的信息和API参数。 对于我们的示例，只有一个参数(id)，因此我们需要创建一个包含以下信息的字段组：

   * **[!UICONTROL Method]**：选择 POST 或 GET 方法。在我们的示例中，我们选择 GET 方法。
   * **[!UICONTROL Cache duration]**:这会根据API调用的频率而改变。在我们的情况下，预订系统每10分钟更新一次。
   * **[!UICONTROL Response Payload]**:在字段内 **[!UICONTROL Payload]** 单击，然后粘贴有效负荷的示例。验证字段类型是否正确。每次调用 API 时，系统将检索有效负载示例中包含的所有字段。在我们的示例中，有效负荷仅包含保留状态：

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamic Values]**:在我们的示例中输入与用于标识每个客户的键对应的参数“id”。此参数的值将在旅程中定义。

   ![](../assets/journeyuc2_11.png)

1. 单击 **[!UICONTROL Save]**.

   现在，已配置数据源并准备好在您的旅程中使用。
