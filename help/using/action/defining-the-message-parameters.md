---
product: adobe campaign
title: 定义操作参数
description: 瞭解如何定義動作引數
feature: Journeys
role: User
level: Intermediate
exl-id: ea9cdb1d-dde6-4080-8f35-7f8cd3cf3644
source-git-commit: 7ce4ddec60f62662d67351b8ca70d7763e76b977
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 4%

---

# 定义操作参数 {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

在 **[!UICONTROL Action parameters]** 區段，貼上要傳送至外部服務的JSON裝載範例。

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>承載中的欄位名稱不能包含「。」 字符. 開頭不能為「$」字元。

您將能夠定義引數型別（例如：字串、整數等）。

您也可以選擇指定引數是常數還是變數：

* 常數表示引數的值是由技術角色在動作設定窗格中定義。 各個歷程中的值一律相同。 這不會改變，且行銷人員在歷程中使用自訂動作時不會看到。 例如，它可能是協力廠商系統期望的ID。 在這種情況下，切換常數/變數右側的欄位是傳遞的值。
* 變數表示引數的值會有所不同。 在歷程中使用此自訂動作的行銷人員，可自由傳遞所需值或指定從何處擷取此引數的值(例如從事件、Adobe Experience Platform等)。 在這種情況下，切換常數/變數右側的欄位是行銷人員在歷程中看到的標籤，以便命名此引數。

![](../assets/customactionpayloadmessage2.png)
