---
product: adobe campaign
title: inSegment
description: 瞭解inSegment函式
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
source-git-commit: e56e6f5dcb8a4680851858355ac18a70bd832b73
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 6%

---

# inSegment {#inSegment}

檢查個人是否屬於指定的區段。

>[!NOTE]
>
>您最多可以擷取100個區段。

區段名稱必須是字串常數。 它不能是欄位參考或運算式。

區段定義於 [Adobe Experience Platform](https://platform.adobe.com/segment/overview). 運算式編輯器提供自動完成的區段清單。

區段可以有三種狀態：

* existing： entity會繼續存在於區段中。
* 已實現：實體正在進入區段。
* 退出：實體正在退出區段。

只有具備下列條件的個人 **已實現** 和 **現有** 區段參與狀態會視為區段的成員。 如需如何評估區段的詳細資訊，請參閱 [Segment Service檔案](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

`IF inSegment('segmentName') == true` 表示您擁有狀態為已輸入/現有狀態的segmentMembership。

`ELSE inSegment('segmentName') == false` 表示您擁有退出狀態的segmentMembership。

## 类别

Adobe Experience Platform

## 函式語法

`inSegment(<parameter>)`

## 参数

| 参数 | 描述 | 类型 |
|--- |--- |--- |
| 区段 | 區段名稱 | `<string>` |

## 簽章和傳回的型別

`inSegment(<string>)`

傳回布林值。

## 示例

`inSegment("men over 50")`

解释:

函式將傳回 **[!UICONTROL true]** 如果歷程例項中的個人屬於名為「50歲以上的男性」的Adobe Experience Platform區段， **[!UICONTROL false]** 否則。
