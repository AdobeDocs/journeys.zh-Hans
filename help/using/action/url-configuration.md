---
product: adobe campaign
title: URL 配置
description: 了解URL配置
feature: Journeys
role: User
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: 2a93bce42ea9f1f21d70c68da3dbc36844dafd1b
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 4%

---

# URL 配置 {#concept_gbg_1f1_2gb}

配置自定义操作时，您需要定义以下内容 **[!UICONTROL URL Configuration]** 参数：

![](../assets/journeyurlconfiguration.png)

1. 在 **[!UICONTROL URL]** 字段，指定外部服务的URL：

   * 如果URL是静态的，请在此字段中输入URL。

   * 如果URL包含动态路径，则仅输入URL的静态部分，即方案、主机、端口，以及（可选）路径的静态部分。

     示例：`https://xxx.yyy.com/somethingstatic/`

     将自定义操作添加到历程时，您将指定URL的动态路径。 [了解详情](../building-journeys/using-custom-actions.md)。

   >[!NOTE]
   >
   >出于安全原因，我们强烈建议您对URL使用HTTPS方案。 我们不允许使用非公共Adobe地址和IP地址。
   >
   >定义自定义操作时只允许使用默认端口：80用于http，443用于https。

1. 选择呼叫 **[!UICONTROL Method]**：它可以是以下任一类型 **[!UICONTROL POST]** 或 **[!UICONTROL PUT]**.
1. 在 **[!UICONTROL Headers]** 部分，定义要发送到外部服务的请求消息的HTTP标头：
   1. 要添加标题字段，请单击 **[!UICONTROL Add a header field]**.
   1. 输入标题字段的键。
   1. 要为键值对设置动态值，请选择 **[!UICONTROL Variable]**. 否则，选择 **[!UICONTROL Constant]**.

      例如，对于时间戳，您可以设置动态值。

   1. 如果您已选择 **[!UICONTROL Constant]**，然后输入常量值。

      如果您已选择 **[!UICONTROL Variable]**，则您将在向历程添加自定义操作时指定此变量。 [了解详情](../building-journeys/using-custom-actions.md)。

      ![](../assets/journeyurlconfiguration2.png)

   1. 要删除标题字段，请指向标题字段并单击 **[!UICONTROL Delete]** 图标。

   此 **[!UICONTROL Content-Type]** 和 **[!UICONTROL Charset]** 默认设置标题字段。 您无法修改或删除这些字段。

   将自定义操作添加到历程后，如果历程处于草稿状态，您仍然可以向历程添加标题字段。 如果您不希望历程受配置更改的影响，请复制自定义操作并将标题字段添加到新的自定义操作。

   >[!NOTE]
   >
   >将根据字段解析规则验证标头。 [了解详情](https://tools.ietf.org/html/rfc7230#section-3.2.4)。
