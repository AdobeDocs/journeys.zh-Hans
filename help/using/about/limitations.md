---
product: adobe campaign
title: Journey Orchestration限制
description: 進一步瞭解Journey Orchestration限制
feature: Journeys
role: User
level: Beginner
exl-id: fef039ae-c04d-4198-a082-4be27710255f
source-git-commit: 18c94897b5cea0d92a83f36845fdda64220b668f
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 51%

---

# 限制 {#limitations}

以下與使用Journey Orchestration相關的限制。

## 一般历程护栏 {#journeys-guardrails-journeys}

* 历程中的活动数量限制为 50 个。活动数显示在历程画布的左上角部分。
* 一个组织中的&#x200B;**实时历程**&#x200B;数量限制为每个沙盒 100 个。达到此限制后，您将无法再发布新历程。

## 一般動作限制

* 无发送限制。 
* 如果出现错误，系统将执行三次重试。无法根据收到的错误消息调整重试次数。 
* 內建 **反應** 事件可讓您對開箱即用的動作做出反應(請參閱此 [頁面](../building-journeys/reaction-events.md))。 如果您想要對透過自訂動作傳送的訊息做出反應，則需要設定專用事件。 

## 歷程版本限制 {#journey-versions-limitations}

* v1 中以事件活动开始的历程，在后续版本中无法以事件之外的其他内容开始。无法以&#x200B;**区段资格**&#x200B;事件开始历程。
* v1 中以&#x200B;**区段资格**&#x200B;活动开始的历程在后续版本中必须始终以&#x200B;**区段资格**&#x200B;开始。
* 在中選擇的區段和名稱空間 **區段資格** （第一個節點）無法在新版本中變更。
* 在所有历程版本中，重新进入规则必须相同。

## 区段鉴别 {#segment-qualification}

* 此 **區段資格** 由於輸送量限制，活動不能與Adobe Campaign Standard異動訊息結合使用。 另請參閱 [Adobe Campaign Standard產品說明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 

## 自訂動作限制

* 自定义操作 URL 不支持动态参数。 
* 仅支持 POST 和 PUT 调用方法. 
* 查询参数或标头的名称不得以“.”或“$”开始。 
* 不允许使用 IP 地址. 
* 不允许使用内部 Adobe 地址 (.adobe.)。 

## Adobe Campaign動作限制

* Adobe Campaign Standard交易式訊息傳遞的規模是給定執行個體的各管道每小時最多50,000則訊息。 另請參閱 [Adobe Campaign Standard產品說明](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 

## 事件限制

* 對於系統產生的事件，必須先在Journey Orchestration中設定用於啟動客戶歷程的串流資料，才能取得唯一的協調流程ID。 此協調流程ID必須附加至傳入Adobe Experience Platform的串流裝載。 此限制不适用于基于规则的事件。 

## 資料來源限制

* 可在客戶歷程中利用外部資料來源即時查詢外部資料。 這些來源必須可透過REST API使用、支援JSON並能夠處理大量請求。

## 在建立設定檔的同時開始的歷程 {#journeys-limitation-profile-creation}

在 Adobe Experience Platform 中，创建/更新基于 API 的配置文件存在延迟。延迟方面的服务水平目标 (SLT) 是在每秒请求量 (RPS) 为 20K 的情况下，从摄取到统一配置文件的第 95% 的请求的延迟小于 1 分钟。

如果在建立設定檔的同時觸發歷程，並立即從設定檔服務檢查/擷取資訊，則可能無法正常運作。

您可以从以下两种解决方案中选择一种：

* 在第一个事件后添加等待活动，以便给 Adobe Experience Platform 提供向用户档案服务执行摄取所需的时间。

* 设置不会立即利用用户档案的历程。例如，如果歷程的設計是要確認帳戶的建立，則體驗事件可能包含傳送第一個確認訊息（名字、姓氏、電子郵件地址等）所需的資訊。
