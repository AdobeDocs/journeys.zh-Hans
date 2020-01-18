---
title: URL配置
description: 了解URL配置
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# URL配置 {#concept_gbg_1f1_2gb}

配置自定义操作时，您需要定义以下参 **[!UICONTROL URL Configuration]**数：

![](../assets/journeyurlconfiguration.png)

1. 添加外 **[!UICONTROL URL]**部服务。

   >[!NOTE]
   >
   >出于安全原因，我们强烈建议使用HTTPS。 我们不允许使用非公开的Adobe地址和IP地址。

1. 选择呼叫 **[!UICONTROL Method]**:它可以是或**[!UICONTROL POST]** 或 **[!UICONTROL PUT]**。
1. 在部分 **[!UICONTROL Headers]**中，单击**[!UICONTROL Add a header field]** 以定义新键／值对。 它们与向外部服务发出的请求的HTTP头相对应。 要删除键／值对，请将光标放在字段 **[!UICONTROL Headers]**上并单击该图**[!UICONTROL Delete]** 标。

   **[!UICONTROL Content-Type]**和**[!UICONTROL Charset]** 默认设置，无法删除或覆盖。

   >[!NOTE]
   >
   >根据以下解析规则验证 [标题](https://tools.ietf.org/html/rfc7230#section-3.2.4)。
