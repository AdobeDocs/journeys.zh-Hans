---
product: adobe campaign
title: 使用自定义操作
description: 了解操作活动
feature: Journeys
role: User
level: Intermediate
exl-id: 9996d1eb-ddef-46dd-aaa9-c37fa9deb2f9
source-git-commit: 8980df5cc238a7195f01a1631e418a8de677fbea
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 11%

---

# 使用自定义操作 {#section_f2c_hbg_nhb}

活动配置窗格显示针对自定义操作配置的URL配置参数和身份验证参数。 [了解详情](../action/about-custom-action-configuration.md)。

## URL 配置

### 动态路径

如果URL包含动态路径，请在&#x200B;**[!UICONTROL Path]**&#x200B;字段中指定该路径。

>[!NOTE]
>
>您无法在历程中设置URL的静态部分，但可以在自定义操作的全局配置中设置。 [了解详情](../action/about-custom-action-configuration.md)。

要连接字段和纯文本字符串，请使用高级表达式编辑器中的字符串函数或加号(+)。 将纯文本字符串用单引号(&#39;)或双引号(&#39;&#39;)括起来。 [了解详情](../expression/expressionadvanced.md)。

下表显示了一个配置示例：

| 字段 | 值 |
| --- | --- |
| URL | `https://xxx.yyy.com:8080/somethingstatic/` |
| 路径 | `The id of marketingCampaign + '/messages'` |

连接的URL具有以下形式：

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;营销活动ID\>`/messages`

![](../assets/journey-custom-action-url.png)

### 标头

**[!UICONTROL URL Configuration]**&#x200B;部分显示动态标头字段，但不显示常量标头字段。 动态标头字段是将其值配置为变量的HTTP标头字段。 [了解详情](../action/about-custom-action-configuration.md)。

如果需要，请指定动态标头字段的值：

1. 选择历程中的自定义操作。
1. 在配置窗格中，单击&#x200B;**[!UICONTROL URL Configuration]**&#x200B;部分中标题字段旁边的铅笔图标。

   ![](../assets/journey-dynamicheaderfield.png)

1. 选择一个字段并单击&#x200B;**[!UICONTROL OK]**。

## 操作参数

在&#x200B;**[!UICONTROL Action parameters]**&#x200B;部分中，您将看到定义为&#x200B;_&quot;变量&quot;_&#x200B;的消息参数。 对于这些参数，您可以定义从何处获取此信息（例如：事件、数据源）、手动传递值或针对高级用例使用高级表达式编辑器。 高级用例可以是数据操作和其他功能使用。 [了解详情](../expression/expressionadvanced.md)。

**相关主题**

[配置操作](../action/about-custom-action-configuration.md)
