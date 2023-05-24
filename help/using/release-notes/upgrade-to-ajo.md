---
title: 升級至Adobe Journey Optimizer
description: 瞭解如何升級至Adobe Journey Optimizer
hide: true
hidefromtoc: true
exl-id: 887fd3bb-bcd3-4a6d-9817-43049c51ecba
source-git-commit: 3e9ff02cecfe85ea38cce4b0d241156f6209202f
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 2%

---

# 將您的Journey Orchestration環境升級至Adobe Journey Optimizer{#ugrade-ajo}

## 什麼是Adobe Journey Optimizer？

Adobe Journey Optimizer是內建在Adobe Experience Platform上的敏捷且可擴充的應用程式，可跨任何應用程式、裝置、畫面或頻道，協調及提供個人化、連線且及時的客戶歷程&#x200B;。

## Journey Orchestration 是什么？

Journey Orchestration是以Adobe Experience Platform為基礎建立的服務，可讓您根據每位客戶先前的行為和偏好設定量身打造個別歷程。 Journey Orchestration是Journey Optimizer的前身應用程式。

## 為何應改用Adobe Journey Optimizer？

**存取簡化的介面** 提供Experience Platform功能，可快速存取歷程、資料集、設定檔、警報等。 無需再在Adobe Experience Platform和Journey Orchestration之間來回工作即可存取結構描述或資料集，一切皆可直接從Adobe Journey Optimizer取得。 如需詳細資訊，請參閱此 [頁面](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/user-interface.html).

<table>
<tr>
<th>之前</th>
<th>之后</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-1.png"><p>存取Journey Orchestration中的「歷程」、「區段」和「管理員」區段（資料來源、事件和動作）。 區段和資料集可在Adobe Experience Platform中存取。 </p></td>
<td><img src="../assets/migration-ajo-2.png"><p>存取歷程、區段、管理員、區段和資料集 <strong>Adobe Journey Optimizer中的所有專案</strong>. <strong>其他Adobe Experience Platform功能</strong> 亦可在此處存取。</p></td>
</tr>
</table>

**新的報表介面** 以及存取新報告功能：

<table>
<tr>
<th>之前</th>
<th>之后</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-5.png"></td>
<td><img src="../assets/migration-ajo-6.png"><p><strong>全域檢視</strong> 可讓您測量選定時段內歷程與傳送的影響。 如需更多即時量度，您可以存取 <strong>即時檢視</strong>. 對於您的歷程中使用的每個傳送管道（電子郵件、簡訊、推播），請 <strong>專用區段</strong> 可用於報表中檢視量度。 這僅適用於使用現成可用的情況 <strong>Adobe Journey Optimizer傳訊功能</strong>. 如需詳細資訊，請洽詢您的帳戶團隊。</p></td>
</tr>
</table>

改善報告體驗或在新功能發行後使其豐富的任何演變，都只能在新的報告介面中使用。 開始使用它以取得更完整的Adobe Journey Optimizer體驗。

取得其他最新功能的好處 **Adobe Journey Optimizer功能** 以及推出新功能，例如「欄位層級存取控制」和「物件層級存取控制」。 如需詳細資訊，請洽詢您的帳戶團隊。

## 如何升級我的Journey Orchestration環境？

1. 請洽詢您的客戶團隊，以更新您與Adobe的合約。

1. 請等待我們的工程團隊完成變更。

1. 使用Journey Optimizer的產品設定檔更新您的許可權。 請參閱此 [頁面](https://experienceleague.adobe.com/docs/journey-optimizer/using/administration/ootb-product-profiles.html?lang=zh-Hans).

1. 您現在可以存取Adobe Journey Optimizer了！

## 常见问题

### 我需要規劃從Journey Orchestration移至Adobe Journey Optimizer的任何專案嗎？

不需要，無需移轉，您無需工作，無需停機，也不需額外投資。 您只需要使用Adobe更新您的合約，我們就會完成其餘工作。 如需如何啟動此程式的說明，請聯絡您的客戶代表。

### 變更後我會遺失一些東西嗎？

否，您將保留所有現有的Journey Orchestration和Adobe Experience Platform物件：結構描述、資料集、歷程、事件、資料來源、動作。 不會遺失任何內容，所有即時歷程將繼續運作而不會中斷。

<table>
<tr>
<th>之前</th>
<th>之后</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-7.png"></td>
<td><img src="../assets/migration-ajo-8.png"></td>
</tr>
</table>

### 我仍然在應用程式切換器中看到Journey Orchestration，它正常嗎？

![](../assets/migration-ajo-9.png)

是的，這是正常的。 升級後的幾天內，您仍可能會看到Journey Orchestration專案。 請使用Journey Optimizer one。

### 如果我今天將Journey Orchestration與Adobe Campaign Standard搭配使用，會發生什麼事？

移至Adobe Journey Optimizer後，您仍可在Adobe Journey Optimizer中設計客戶歷程並讓Adobe Campaign Standard傳送傳遞，藉此使用歷程與Adobe Campaign Standard之間的整合。

不過，由於Adobe Journey Optimizer報告棧疊的運作方式，報告不會結合歷程和Campaign Standard資料。 歷程資訊可在Adobe Journey Optimizer報告中取得，也可在Adobe Campaign Standard中取得傳送資訊。 可進行Experience Platform設定，將Adobe Campaign Standard資料帶回Adobe Experience Platform，使其可供Customer Journey Analytics ([瞭解更多](https://business.adobe.com/products/experience-platform/customer-journey-analytics.html))或其他協力廠商報告工具，例如Tableau或PowerBI。

使用Adobe Journey Optimizer現成的訊息傳送功能時，Adobe Journey Optimizer報表的運作最佳化(可在專屬的Adobe Journey Optimizer產品中取得)。 如需如何在歷程畫布中製作訊息的詳細資訊，請參閱此 [頁面](https://experienceleague.adobe.com/docs/journey-optimizer/using/messages/messages-in-journeys.html).

如需詳細資訊，請洽詢您的帳戶團隊。
