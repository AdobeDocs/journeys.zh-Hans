---
title: 访问管理
description: 了解有关访问管理的更多信息
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27

---


# 访问管理{#concept_rfj_wpt_52b}

## 关于访问管理 {#about-access-management}

产品配置文件将分配给您组织内共享相同权限的一组用户。

在“管理控制台”中，您可以向用户分配以下现成的产品配置之一：

* **[!UICONTROL Limited Access User]**:具有对旅程和报告的只读访问权限的用户。 此产品配置包含以下权限：
   * 阅读旅程
   * 阅读报告

* **[!UICONTROL Administrators]**:用户可访问管理菜单，并可以管理旅程、活动和报告。 此产品配置包含以下权限：
   * 管理和执行旅程
   * 管理事件、数据源和操作
   * 管理报告
   >[!NOTE]
   >
   >**[!UICONTROL Administrators]**是唯一允许在Adobe Campaign standard中创建、编辑和发布交易消息（或消息模板）的产品配置文件。 如果您使用Adobe Campaign Standard在旅程中发送消息，则需要此产品配置文件。

* **[!UICONTROL Standard User]**:具有基本访问权限的用户，如旅程管理。 此产品配置包含以下权限：
   * 管理和执行旅程
   * 管理报告

您可以在此 [找到](../assets/do-not-localize/acs_rights_journeys.pdf) ，权限与旅程编排的不同功能之间的兼容性。

## 分配产品配置 {#assigning-product-profile}

产品配置在管理控制台中进行管理。 有关详细信息，请参阅 [Admin Console文档](https://helpx.adobe.com/enterprise/managing/user-guide.html)。

为用户分配产品配置以访问旅程安排：

1. 在管理控制台中，选择 **[!UICONTROL Journey orchestration]**。

   ![](../assets/user_management.png)

1. 选择新用户将链接到的产品配置文件。

   ![](../assets/user_management_2.png)

1. 单击 **[!UICONTROL Add user]**.

   您还可以将新用户添加到用户组以微调共享的权限集。 For more on this, refer to this [page](https://helpx.adobe.com/enterprise/using/user-groups.html).

   ![](../assets/user_management_3.png)

1. 键入新用户的电子邮件地址，然后单击 **[!UICONTROL Save]**。

   ![](../assets/user_management_4.png)

然后，您的用户应会收到一封重定向到您的旅程安排实例的电子邮件。