---
product: adobe campaign
solution: Journey Orchestration
title: URL 配置
description: 了解URL配置
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 9%

---


# URL 配置 {#concept_gbg_1f1_2gb}

配置自定义操作时，您需要定义以下&#x200B;**[!UICONTROL URL Configuration]**&#x200B;参数：

![](../assets/journeyurlconfiguration.png)

1. 添加外部服务的&#x200B;**[!UICONTROL URL]**。

   >[!NOTE]
   >
   >出于安全原因，我们强烈建议使用 HTTPS。我们不允许使用非公开的Adobe地址和IP地址。

1. 选择呼叫&#x200B;**[!UICONTROL Method]**:它可以是&#x200B;**[!UICONTROL POST]**&#x200B;或&#x200B;**[!UICONTROL PUT]**。
1. 在&#x200B;**[!UICONTROL Headers]**&#x200B;部分，单击&#x200B;**[!UICONTROL Add a header field]**&#x200B;定义新的键/值对。 它们与向外部服务发出的请求的HTTP头相对应。 要删除键/值对，请将光标放在&#x200B;**[!UICONTROL Headers]**&#x200B;字段上，然后单击&#x200B;**[!UICONTROL Delete]**&#x200B;图标。

   **[!UICONTROL Content-Type]** 和 **[!UICONTROL Charset]** 默认设置，无法删除或覆盖。

   >[!NOTE]
   >
   >根据以下[解析规则](https://tools.ietf.org/html/rfc7230#section-3.2.4)验证标头。
