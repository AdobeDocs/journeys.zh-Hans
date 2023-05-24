---
product: adobe campaign
title: 创建事件
description: 瞭解如何建立事件
feature: Journeys
role: User
level: Intermediate
exl-id: 2ae8854a-c3e7-469d-9f89-25b54bc3e894
source-git-commit: bdc9ac3f54fae1dfd6f24a54a2687a0834f69c36
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 58%

---

# 创建新事件 {#section_tbk_5qt_pgb}

以下是配置新事件的主要步骤：

1. 在顶部菜单中，单击&#x200B;**[!UICONTROL Events]**&#x200B;选项卡。将显示事件列表。請參閱 [此頁面](../about/user-interface.md) 以取得介面的詳細資訊。

   ![](../assets/journey5.png)

1. 单击&#x200B;**[!UICONTROL Add]**&#x200B;以创建新事件。事件配置窗格将在屏幕右侧打开。输入事件的名称。您也可以新增說明。

   ![](../assets/journey6.png)

   >[!NOTE]
   >
   >请勿使用空格或特殊字符。请勿使用超过 30 个字符。

1. 在 **[!UICONTROL Event ID type]** 欄位中，選取您要使用的事件型別。

   ![](../assets/journey6bis.png)

   * **基于规则**&#x200B;的事件：此类型的事件不生成 eventID。在 **事件ID條件** 欄位，您只需定義系統用來識別將觸發歷程的相關事件的規則。 此规则可以基于事件有效负荷中可用的任何字段，例如用户档案的位置或添加到用户档案购物车的项目数。

   * **系統產生** 事件：此型別需要eventID。 建立事件時會自動產生此eventID欄位，並將其新增至裝載預覽。 推送事件的系统不应生成 ID，它应传递有效负荷预览中可用的 ID。请参阅[此小节](../event/previewing-the-payload.md)。
   >[!NOTE]
   >
   >深入瞭解中的事件型別 [本節](../event/about-events.md).
1. 使用此事件的旅程数显示在&#x200B;**[!UICONTROL Used in]**&#x200B;字段中。您可以单击 **[!UICONTROL View journeys]**&#x200B;图标，以显示使用此事件的旅程列表。
1. 定义架构和有效负载字段：在这里，您可以选择 [!DNL Journey Orchestration] 预期接收的事件信息（通常称为有效负载）。然后，您便能够在旅程中使用这些信息。请参阅[此页](../event/defining-the-payload-fields.md)。
   >[!NOTE]
   >
   >當您選取 **[!UICONTROL System Generated]** 型別，只有具有eventID型別mixin的結構描述才可使用。 當您選取 **[!UICONTROL Rule Based]** 型別，則所有體驗事件結構描述都可使用。

1. 對於規則型事件，請按一下 **[!UICONTROL Event ID condition]** 欄位。 使用簡單運算式編輯器，定義系統將用來識別將觸發您歷程之事件的條件。
   ![](../assets/alpha-event6.png)

   在我們的範例中，我們根據設定檔的城市來撰寫條件。 這表示每當系統收到符合此條件的事件時(**[!UICONTROL City]** 欄位和 **[!UICONTROL Paris]** 值)，則會將其傳遞給Journey Orchestration。

   >[!NOTE]
   >
   >定義時無法使用進階運算式編輯器 **[!UICONTROL Event ID condition]**. 在簡單運算式編輯器中，並非所有運運算元都可用，它們取決於資料型別。 例如，對於欄位的字串型別，您可以使用「包含」或「等於」。

1. 添加命名空间。此步骤是可选的，但还是建议您添加命名空间，以便您利用实时客户资料服务中存储的信息。它定义事件具有的键类型。请参阅[此页](../event/selecting-the-namespace.md)。
1. 定义键：从有效负载字段中选择一个字段或定义一个公式以标识与事件关联的个人。如果您选择命名空间，此键将自动设置（但仍可编辑）。事实上，[!DNL Journey Orchestration] 会选取应与命名空间对应的键（例如，如果您选择了电子邮件命名空间，则会自动选择电子邮件键）。请参阅[此页](../event/defining-the-event-key.md)。
1. 单击 **[!UICONTROL Save]**。

   ![](../assets/journey7.png)

   事件现已配置完毕，可随时投入旅程。还需要其他配置步骤以接收事件。请参阅[此页](../event/additional-steps-to-send-events-to-journey-orchestration.md)。
