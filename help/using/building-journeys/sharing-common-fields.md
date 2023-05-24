---
product: adobe campaign
title: journeysteps事件常見欄位
description: journeysteps事件常見欄位
feature: Journeys
role: User
level: Intermediate
exl-id: 5cf8e6b5-2162-4aa3-b071-96ede31948e6
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 9%

---

# journeysteps事件常見欄位 {#sharing-common-fields}

此mixin將由journeyStepEvent和journeyStepProfileEvent共用。

這些是常見的XDM欄位， [!DNL Journey Orchestration] 傳送至Adobe Experience Platform。 歷程中處理的每個步驟都會傳送通用欄位。 自訂動作和增強功能會使用更具體的欄位。

其中一些欄位僅適用於特定處理模式（動作執行、資料擷取等） 以限制事件大小。

## 入口

指出使用者是否已進入歷程。 如果不存在，我們會假設值為false。

类型：布尔值

值： true/false

## 重新進入

指出使用者是否已重新進入具有相同執行個體的歷程。 如果不存在，我們會假設值為false。

类型：布尔值

值： true/false

## instanceEnded

指示執行個體是否已結束（成功或失敗）。

类型：布尔值

## eventID

處理中的事件ID，用於步驟處理。 如果事件是外部事件，則值為其eventId。 如果事件是內部事件，則值為內部eventId （例如scheduledNotificationReceived、executedAction等）。

类型：字符串

## nodeID

使用者端節點id （來自畫布）。

类型：字符串

## stepID

目前正在處理的步驟的唯一ID。

类型：字符串

## stepName

目前正在處理的步驟名稱。

类型：字符串

## stepType

步驟型別。

类型：字符串

可能的值：

* 条件
* 操作
* 调度程序
* 計時器

## 步驟狀態

步驟的狀態，代表步驟的狀態，表示其處理已完成（且已引發步驟事件）的時間。

类型：字符串

状态可以是：

* 已結束：步驟沒有轉變，其處理已成功結束。
* 錯誤：步驟處理發生錯誤。
* 轉變：步驟正在等待事件轉變到另一個步驟。
* 上限：步驟因上限錯誤而失敗，在動作或擴充期間引發。
* 逾時：步驟因逾時錯誤而失敗，在動作或擴充期間發生。
* instanceTimedout：步驟已停止處理，因為執行個體已達到其逾時。

## journeyID

歷程的ID。

类型：字符串

## journeyVersionID

歷程版本的ID。 在journeyStepEvent的情況下，此id代表歷程的身分參考。

类型：字符串

## journeyVersionName

歷程版本的名稱。

类型：字符串

## journeyVersion

歷程版本的版本。

类型：字符串

## 執行個體識別碼

歷程執行個體的內部ID。

类型：字符串

## externalKey

從事件擷取以處理的外部金鑰。

类型：字符串

## parentstepid

執行個體中目前已處理步驟的父級步驟ID。

类型：字符串

## parentStepName

目前步驟之父項的步驟名稱。

类型：字符串

## parentTransitionID

將執行個體帶到已處理步驟的轉變ID。

类型：字符串

## parentTransitionName

將執行個體帶到已處理步驟的轉變名稱。

类型：字符串

## inTest

指出此歷程是否處於測試模式。

类型：布尔值

## processingTime

從執行個體步驟進入到處理結束的總時間量（毫秒）。

型別： long

## instanceType

指示執行個體型別（如果是批次或單一）。

类型：字符串

值：批次/單一

## recurrenceIndex

如果歷程是批次和週期性（第一次執行有recurrenceIndex = 1）的週期索引。

型別： long

## isBatchToUnitary

指出此單一執行個體是否已從批次執行個體觸發。

类型：布尔值

## batchExternalKey

批次事件的外部金鑰。

类型：字符串

## batchInstanceID

這是批次例項ID。

类型：字符串

## batchUnitaryBranchID

如果執行個體是從批次執行個體觸發，則為單一分支ID。

类型：字符串
