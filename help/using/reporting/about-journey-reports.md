---
product: adobe campaign
title: 关于历程报告
description: 瞭解如何建立您的歷程報告
feature: Journeys
role: User
level: Intermediate
exl-id: 93768321-b171-4338-a440-6ea189a85a4a
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 1%

---

# 关于历程报告 {#concept_rfj_wpt_52b}

>[!NOTE]
>
>只有在您有Adobe Campaign Standard的情況下，才會填入傳遞資料和區段元件。

本節將說明如何存取及使用報表來測量歷程的成效。

## 报告界面 {#reporting-interface}

例如，頂端工具列可讓您修改、儲存或列印報表。

![](../assets/dynamic_report_toolbar.png)

使用 **[!UICONTROL Project]** 按Tab鍵以：

* **[!UICONTROL Open]**：開啟先前建立的報表或範本。
* **[!UICONTROL Save As]**：複製範本以便修改。
* **[!UICONTROL Refresh project]**：根據新資料和篩選器的變更來更新您的報表。
* **[!UICONTROL Download CSV]**：將報表匯出至CSV檔案。
* **[!UICONTROL Print]**：列印您的報表。

此 **[!UICONTROL Edit]** 索引標籤可讓您：

* **[!UICONTROL Undo]**：取消您在控制面板上的上一個動作。
* **[!UICONTROL Redo]**：取消您的最後一個 **[!UICONTROL Undo]** 動作。
* **[!UICONTROL Clear all]**：刪除控制面板上的每個面板。

此 **[!UICONTROL Insert]** 表格可讓您藉由將圖表和表格新增至控制面板來自訂報表：

* **[!UICONTROL New Blank Panel]**：新增空白面板至您的儀表板。
* **[!UICONTROL New Freeform]**：新增自由表格至您的儀表板。
* **[!UICONTROL New Line]**：新增折線圖至您的儀表板。
* **[!UICONTROL New Bar]**：新增橫條圖至您的儀表板。

左側標籤可讓您建立報告並視需要篩選資料。

![](../assets/dynamic_report_interface.png)

這些標籤可讓您存取下列專案：

* **[!UICONTROL Panels]**：新增空白面板或自由格式至您的報表，以開始篩選資料。 如需詳細資訊，請參閱 [新增面板](../reporting/creating-your-journey-reports.md#adding-panels) 區段
* **[!UICONTROL Visualizations]**：拖放選取的視覺效果專案，為您的報表提供圖形維度。 如需詳細資訊，請參閱 [新增視覺效果](../reporting/creating-your-journey-reports.md#adding-visualizations) 區段。
* **[!UICONTROL Components]**：使用不同的維度、量度、區段和時段來自訂報表。 如需詳細資訊，請參閱 [新增元件](../reporting/creating-your-journey-reports.md#adding-components) 區段。

## 歷程摘要範本 {#ootb-template}

報告分為兩個類別：現成可用的範本和自訂報告。
現成可用的範本， **[!UICONTROL Journey summary]**，可讓您清楚地檢視最重要的追蹤資料。

![](../assets/dynamic_report_journey_8.png)

每個表格都以摘要數字和圖表表示。 您可以變更詳細資訊在其各自視覺效果設定中的顯示方式。

報表頂端提供下列KPI：

* **[!UICONTROL Journey - Entered]**：到達歷程進入事件的個人總數。
* **[!UICONTROL Journey - Completion rate]**：已到達歷程結束的個人總數（或如果個人不符合任何條件），與進入歷程的個人總數比較。
* **[!UICONTROL Journey - Current]**：目前歷程中的個人總數。
* **[!UICONTROL Journey - Failed rate]**：與執行歷程數相比，未成功執行的歷程總數。
* **[!UICONTROL Delivery - Messages sent]**：已傳送的訊息總數。
* **[!UICONTROL Delivery rate]**：與已傳送的訊息相比，成功傳送的訊息總數。
* **[!UICONTROL Delivery - Bounce rate]**：與已傳送的訊息相比，跳出的訊息總數。
* **[!UICONTROL Delivery - Unsubscribed rate]**：收件者與已傳送訊息相比的取消訂閱總數。
* **[!UICONTROL Delivery - Open rate]**：已開啟的訊息總數，與已傳遞的訊息數比較。
* **[!UICONTROL Delivery - Click rate]**：與已傳送訊息數量相較的傳送中點按總數。

歷程流量視覺效果可讓您檢視目標設定檔在歷程中的逐步路徑。 這僅在鎖定一個歷程時可用。 這會自動產生，且無法修改。

![](../assets/dynamic_report_journey_10.png)

此 **[!UICONTROL Journey summary]** 表格包含可用於您歷程的資料，例如：

* **[!UICONTROL Entered]**：到達歷程進入事件的個人總數。
* **[!UICONTROL Completion rate]**：與進入歷程的個人總數相比，達到歷程的結束流量控制的個人總數。
* **[!UICONTROL Current]**：目前歷程中的個人總數。
* **[!UICONTROL Failed]**：未成功執行的歷程總數。
* **[!UICONTROL Failed rate]**：與執行歷程數相比，未成功執行的歷程總數。

此 **[!UICONTROL Top events]** 表格會顯示最成功的事件，以及 **[!UICONTROL Top action]**，此元件為歷程中最成功的動作。

![](../assets/dynamic_report_journey_11.png)

此 **[!UICONTROL Delivery - Sending summary]** 此表格包含可用於您歷程傳送的資料，例如：

* **[!UICONTROL Processed/sent]**：已傳送的訊息總數。
* **[!UICONTROL Delivered rate]**：與已傳送的訊息相比，成功傳送的訊息總數。
* **[!UICONTROL Delivered]**：成功傳送的訊息數，與已傳送訊息總數相關。
* **[!UICONTROL Bounce + error rate]**：與已傳送的訊息相比，跳出的訊息總數。
* **[!UICONTROL Bounces + errors]**：與已傳送訊息總數相關的傳送和自動傳回處理期間累計的錯誤總數。

此 **[!UICONTROL Delivery - Tracking summary]** 此表格包含可用於追蹤歷程傳送成功與否的資料，例如：

* **[!UICONTROL Open Rate]**：已開啟訊息的百分比。
* **[!UICONTROL Open]**：在傳遞中開啟訊息的次數。
* **[!UICONTROL Click trough rate]**：與已傳送訊息數量相較的傳送中點按總數。
* **[!UICONTROL Click]**：內容在傳遞中的點按次數。
* **[!UICONTROL Unsubscribe rate]**：收件者相對於已傳遞訊息的取消訂閱百分比。
* **[!UICONTROL Unsubscribed]**：收件者與已傳送訊息相比的取消訂閱總數。
