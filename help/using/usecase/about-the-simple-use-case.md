---
product: adobe campaign
title: 关于简单用例
description: 進一步瞭解歷程簡單使用案例
feature: Journeys
role: User
level: Intermediate
exl-id: 11858c7a-fdb3-43a4-af28-0d5c23fa2468
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 11%

---

# 关于简单用例{#concept_grh_vby_w2b}

## 用途 {#purpose}

以一個名為Marlton的飯店品牌為例。 在酒店內，他們在所有策略區域附近都放置了信標裝置：大廳、地板、餐廳、健身房、游泳池等。

在此使用案例中，我們將瞭解如何即時傳送個人化訊息給站在spa附近信標旁邊的人。

我們只想在該人是女性時傳送訊息。 訊息必須在秒內收到。

![](../assets/journeyuc1_16.png)

## 先决条件 {#prerequisites}

針對我們的使用案例，我們在Adobe Campaign Standard中設計了一個電子郵件交易式訊息範本。 我們正在使用事件交易式訊息範本。 請參閱此 [頁面](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=zh-Hans).

Adobe Campaign Standard已設定為傳送電子郵件。

在信標附近偵測到事件時，會從客戶的行動電話傳送事件。 您需要設計行動應用程式，將事件從客戶的行動電話傳送至Mobile SDK。
