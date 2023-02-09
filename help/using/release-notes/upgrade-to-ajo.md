---
title: 升级到Adobe Journey Optimizer
description: 了解如何升级到Adobe Journey Optimizer
hide: true
hidefromtoc: true
exl-id: 887fd3bb-bcd3-4a6d-9817-43049c51ecba
source-git-commit: 3e9ff02cecfe85ea38cce4b0d241156f6209202f
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 2%

---

# 将Journey Orchestration环境升级到Adobe Journey Optimizer{#ugrade-ajo}

## 什么是Adobe Journey Optimizer?

Adobe Journey Optimizer是一款本地在Adobe Experience Platform上构建的灵活、可扩展的应用程序，用于编排和提供跨任何应用程序、设备、屏幕或渠道的个性化、连接且及时的客户旅程&#x200B;。

## Journey Orchestration 是什么？

Journey Orchestration是一项基于Adobe Experience Platform构建的服务，允许您根据每位客户的先前行为和偏好定制各个历程。 Journey Orchestration是向Journey Optimizer提交的前身申请。

## 我为什么要搬到Adobe Journey Optimizer?

**访问简化的界面** 通过Experience Platform功能，可快速访问历程、数据集、用户档案、警报等。 无需再在Adobe Experience Platform和Journey Orchestration之间来回执行访问模式或数据集的操作，所有内容都可直接从Adobe Journey Optimizer中获取。 有关更多信息，请参阅 [页面](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/user-interface.html).

<table>
<tr>
<th>之前</th>
<th>之后</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-1.png"><p>在Journey Orchestration中访问历程、区段和管理员部分（数据源、事件和操作）。 区段和数据集可在Adobe Experience Platform中访问。 </p></td>
<td><img src="../assets/migration-ajo-2.png"><p>访问历程、区段、管理员、区段和数据集， <strong>在Adobe Journey Optimizer</strong>. <strong>其他Adobe Experience Platform功能</strong> 也可在此处访问。</p></td>
</tr>
</table>

**新的报表界面** 以及访问新报表功能：

<table>
<tr>
<th>之前</th>
<th>之后</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-5.png"></td>
<td><img src="../assets/migration-ajo-6.png"><p><strong>全局视图</strong> 允许您测量选定时间段内历程和投放的影响。 对于更多实时量度，您可以访问 <strong>实时视图</strong>. 对于您的历程中使用的每个投放渠道（电子邮件、短信、推送）， <strong>专用部分</strong> 可在报表中查看量度。 仅当您使用现成的 <strong>Adobe Journey Optimizer报文传送功能</strong>. 有关更多信息，请联系您的客户团队。</p></td>
</tr>
</table>

任何旨在改进报表体验或在发布新功能后扩充报表体验的演变，仅在新报表界面中提供。 开始使用它以获得更完整的Adobe Journey Optimizer体验。

从其他电流中获益 **Adobe Journey Optimizer功能** 和新版本，如字段级别访问控制和对象级别访问控制。 请联系您的客户团队以获取更多信息。

## 如何升级我的Journey Orchestration环境？

1. 请联系您的客户团队，以使用Adobe更新您的协议。

1. 等待工程团队完成更改。

1. 使用Journey Optimizer的产品配置文件更新您的权限。 请参阅 [页面](https://experienceleague.adobe.com/docs/journey-optimizer/using/administration/ootb-product-profiles.html?lang=zh-Hans).

1. 您现在可以访问Adobe Journey Optimizer!

## 常见问题

### 我需要规划从Journey Orchestration到Adobe Journey Optimizer的任何内容吗？

不需要，没有迁移，没有工作需要，没有停机时间，也没有额外的投资。 您只需使用Adobe更新您的协议，然后我们会执行其余操作。 有关如何启动此过程的说明，请联系您的客户代表。

### 换衣服后我会失去什么吗？

否，您将保留所有现有Journey Orchestration和Adobe Experience Platform对象：架构、数据集、历程、事件、数据源、操作。 不会丢失任何内容，所有实时历程都将继续工作且不会中断。

<table>
<tr>
<th>之前</th>
<th>之后</th>
</tr>
<tr>
<td><img src="../assets/migration-ajo-7.png"></td>
<td><img src="../assets/migration-ajo-8.png"></td>
</tr>
</table>

### 我仍在应用程序切换器中看到Journey Orchestration，是否正常？

![](../assets/migration-ajo-9.png)

是的，这是正常的。 升级后，您仍可能会在几天内看到Journey Orchestration项目。 请用Journey Optimizer。

### 如果今天我将Journey Orchestration与Adobe Campaign Standard结合使用，会发生什么情况？

转到Adobe Journey Optimizer后，您仍然能够通过在Adobe Journey Optimizer中设计历程旅程并让Adobe Campaign Standard发送交付，来使用与Adobe Campaign Standard之间的集成。

但是，由于Adobe Journey Optimizer报表堆栈的工作方式，报表将不会将历程和Campaign Standard数据结合使用。 历程信息将在Adobe Campaign Standard的Adobe Journey Optimizer报告和投放信息中提供。 可以配置Experience Platform以将Adobe Campaign Standard数据重新引入Adobe Experience Platform，以供Customer Journey Analytics([了解更多](https://business.adobe.com/products/experience-platform/customer-journey-analytics.html))或其他第三方报表工具（如Tableau或PowerBI）。

Adobe Journey Optimizer报告在使用Adobe Journey Optimizer的即装即用消息传送功能(在Adobe Journey Optimizer的专用产品中提供)时最能正常运行。 有关如何在历程画布中创作消息的更多信息，请参阅此 [页面](https://experienceleague.adobe.com/docs/journey-optimizer/using/messages/messages-in-journeys.html).

有关更多信息，请联系您的客户团队。
