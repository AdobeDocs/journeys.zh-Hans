---
product: adobe campaign
title: 配置数据源
description: 了解如何为历程高级用例配置数据源
feature: 历程
role: User
level: Intermediate
exl-id: 2cfa4397-fe8f-44b3-b219-2fd5d3bdd156
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 14%

---

# 配置数据源 {#concept_vml_hdy_w2b}

在我们的用例中，我们希望将个性化数据用于我们的消息。 我们还需要检查该人员是否是忠诚会员，且过去24小时内未联系到该人员。 此信息存储在实时客户资料数据库中。 **技术用户**&#x200B;需要配置Adobe Experience Platform数据源以检索这些字段。

有关数据源配置的其他信息，请参阅[此页面](../datasource/about-data-sources.md)。

1. 在顶部菜单中，单击&#x200B;**[!UICONTROL Data Sources]**&#x200B;选项卡，然后选择内置的Adobe Experience Platform数据源。

   ![](../assets/journey23.png)

1. 在预配置的组字段中，检查是否选择了以下字段：

   * _person > name > firstName_
   * _person > name > lastName_
   * _personalEmail > address_

1. 单击&#x200B;**[!UICONTROL Add a New Field Group]**，选择&#x200B;**[!UICONTROL Profiles]**&#x200B;架构，并为我们的条件添加&#x200B;**忠诚会员**&#x200B;字段。 **忠诚会员**&#x200B;字段是自定义字段，已添加到XDM中：&quot;_customer > marlton > loyattyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. 单击&#x200B;**[!UICONTROL Add a New Field Group]**，选择&#x200B;**[!UICONTROL ExperienceEvent]**&#x200B;架构，然后根据给定时间段内发送的消息数选择条件所需的字段：日期为&#x200B;_timestamp_，而日期为&#x200B;_directMarketing >发送> value_，表示已发送的消息数。

   ![](../assets/journeyuc2_7.png)

1. 单击 **[!UICONTROL Save]**。

我们还需要检查该人在酒店预订系统中是否有预订。 **技术用户**&#x200B;需要配置第二个数据源以检索此字段。

1. 在数据源列表中，单击&#x200B;**[!UICONTROL Add]**&#x200B;以添加新的外部数据源，以定义与酒店预订系统的连接。

   ![](../assets/journeyuc2_9.png)

1. 输入数据源的名称和外部服务的URL，例如：_https://marlton.com/reservation_

   >[!CAUTION]
   >
   >出于安全原因，我们强烈建议使用 HTTPS。

1. 根据外部服务配置以配置身份验证：**[!UICONTROL No authentication]**、**[!UICONTROL Basic]**、**[!UICONTROL Custom]** 或&#x200B;**[!UICONTROL API key]**。在本例中，我们为类型选择“基本”，并为API调用指定用户名和密码。

   ![](../assets/journeyuc2_10.png)

1. 单击&#x200B;**[!UICONTROL Add a New Field Group]**&#x200B;以定义要检索的信息和API参数。 例如，只有一个参数(id)，因此我们需要创建一个字段组，其中包含以下信息：

   * **[!UICONTROL Method]**：选择 POST 或 GET 方法。在我们的示例中，我们选择 GET 方法。
   * **[!UICONTROL Cache duration]**:这因API调用的频率而异。在本例中，预订系统每10分钟更新一次。
   * **[!UICONTROL Response Payload]**:单击字段 **[!UICONTROL Payload]** 内部，并粘贴有效负载示例。验证字段类型是否正确。每次调用 API 时，系统将检索有效负载示例中包含的所有字段。在我们的示例中，有效负载仅包含保留状态：

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamic Values]**:输入与用于标识每个客户的键对应的参数，在本例中为“id”。此参数的值将在历程中定义。

   ![](../assets/journeyuc2_11.png)

1. 单击 **[!UICONTROL Save]**。

   数据源现已配置完毕，可随时用于您的历程。
