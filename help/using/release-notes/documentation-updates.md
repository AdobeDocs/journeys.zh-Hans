---
title: 文档更新
description: 了解文档更新
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
source-git-commit: 71b5b1ecd20056d0103ae1a8b83a31478449e844
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 86%

---


# 文档更新

此页面列出了
[!DNL Journey Orchestration]的所有文档更新。您还可以参阅 [!DNL Journey Orchestration][发行说明。](../release-notes/release-notes.md)

## 2020 年 7 月 {#july-2020}

* 添加了指向新教程视频的链接，该视频在步骤事件报告到Adobe Experience Platform。 [阅读更多](../building-journeys/sharing-overview.md)
* 事件活动部分已重新组织为每种事件的专用子部分。 [阅读更多](../building-journeys/event-activities.md)
* 添加了最佳实践，以避免因细分质量而过载。 [阅读更多](../building-journeys/segment-qualification-events.md#speed-segment-qualification)
* 添加了注释，以说明如何在操作或条件出现错误后继续旅程。 [阅读更多](../about/troubleshooting.md#section_h3q_kqk_fhb)
* 新增了 Alpha 功能部分，这些功能在有限的一组客户中进行测试。[阅读更多](../alpha/alpha-overview.md)
* 添加了有关与智能服务集成的新部分。[阅读更多](../ai-services/ai-services-overview.md)
* 在创建测试用户档案时添加了新部分。[阅读更多](../building-journeys/testing-the-journey.md#create-test-profile)
* 添加了有关如何在旅程条件或操作中使用 **[!UICONTROL SegmentQualification]** 节点的信息。[阅读更多](../building-journeys/segment-qualification-events.md)
* 已在 Campaign 事务性消息和事件出版中添加注释。请参阅[使用 Adobe Campaign](../action/working-with-adobe-campaign.md) 和 [使用 Adobe Campaign 操作](../building-journeys/using-adobe-campaign-actions.md)。
* 已在测试 Campaign Standard 实例 URL 时执行的检查中添加了信息。[阅读更多](../action/working-with-adobe-campaign.md)
* 已添加有关与 AWS 或 Azure 服务器上托管的 Campaign Standard 实例兼容的反应事件的信息。[阅读更多](../building-journeys/reaction-events.md)
* 在处理 Campaign Standard 事务性消息传递时，需要设置上限规则这一点已添加注释。[阅读更多](../action/working-with-adobe-campaign.md)
* 在使用测试模式触发事件时，在生成实际事件时添加了注释。[阅读更多](../building-journeys/testing-the-journey.md#firing_events)

## 2020 年 6 月 {#june-2020}

* 添加了有关如何更改自定义身份验证数据源的令牌缓存时间的信息。[阅读更多](../datasource/external-data-sources.md#section_wjp_nl5_nhb)
* Updated screenshots and text to reflect the renaming of the **[!UICONTROL Finished]** journey state which has been changed to **[!UICONTROL Closed (no entrance)]**.
* 添加了有关如何为界面定义语言的信息。[阅读更多](../about/user-interface.md)
* 个人旅程的状态列表已移至[测试模式日志](../building-journeys/testing-the-journey.md#viewing_logs)部分。

## 2020 年 4 月 {#april-2020}

* 添加了有关体验事件模式定义的新部分，以帮助用户配置其第一个事件。[阅读更多](../event/experience-event-schema.md)
* [!DNL Journey Orchestration]文档主页已更新，添加了其他有用链接。[阅读更多](../../journey-orchestration-home.md)

## 2020 年 3 月 {#march-2020}

* 在测试日志部分，添加了 _actionExecutionErrors_ 和 _fetchErrors_ 参数描述。[阅读更多](../building-journeys/testing-the-journey.md#viewing_logs)
* 旅程中使用的自定义操作的限制已更新。You can also modify the **[!UICONTROL URL]** field and the **[!UICONTROL Authentication]** parameters. [阅读更多](../action/about-custom-action-configuration.md)
* 已添加新的情景帮助条目。自定义身份验证有效负载窗格（在操作和数据源中）现在包含一个链接到此[部分](../datasource/external-data-sources.md#section_wjp_nl5_nhb)的帮助图标。
* 现在可以停止已关闭的旅程。[阅读更多](../building-journeys/using-the-journey-designer.md)
* 界面描述部分已重新组织。[阅读更多](../about/user-interface.md)
* 多个事件的触发已添加到测试模式部分[阅读更多](../building-journeys/testing-the-journey.md#firing_events)
* “测试”模式部分已更新，以便与新参数相 **[!UICONTROL Wait time in test]** 关。 [阅读更多](../building-journeys/testing-the-journey.md)
* 测试日志部分已更新为外部调用错误代码和响应。[阅读更多](../building-journeys/testing-the-journey.md#viewing_logs)
* 时区管理现在集中在旅程属性面板中。在[此处](../building-journeys/changing-properties.md#timezone)和[此处](../building-journeys/timezone-management.md)了解更多信息
* 旅程设计器部分已更新以反映最近的增强功能。[阅读更多](../building-journeys/using-the-journey-designer.md)
* 界面描述已更新，其中包含有关情景帮助的信息。[阅读更多](../about/user-interface.md#section_ksq_zr1_ffb)
* 浏览 **XDM 字段**&#x200B;时，将显示友好名称。相关部分已更新。[阅读更多](../about/user-interface.md#friendly-names-display)

## 2020 年 2 月 {#february-2020}

* 快捷键部分已更新。**C** 键盘快捷键，允许您在所有列表屏幕中创建新项目。[阅读更多](../about/user-interface.md#section_ksq_zr1_ffb)
* [数据源](../datasource/about-data-sources.md)和[操作](../action/action.md)概述页面已得到改进。

## 2020 年 1 月 {#january-2020}

* 已为[体验事件](../datasource/adobe-experience-platform-data-source.md)和[区段](../functions/functioninsegment.md)添加“获取限制条件”。
* [getBestSendTime 文档](../functions/functiongetbestsendtime.md)已更新。

## 2019 年 12 月 {#december-2019}

* 所有屏幕截图都已更新，以反映界面的更改。
* 测试模式部分已更新。[阅读更多](../building-journeys/testing-the-journey.md)
* 在[电子邮件发送时间优化](../building-journeys/wait-activity.md)和[预测性疲劳得分](../ai-services/leveraging-fatigue-scores.md)部分添加了警告。这些功能只适用于使用 Adobe Campaign Standard 数据服务功能的客户。
* 现在可删除已停止的旅程。相关文档页面已更新。
* 在旅程中检测到问题时，会显示两种颜色。红色表示错误，橙色表示警告。[阅读更多](../about/troubleshooting.md)
* 高级表达式编辑器部分已更新。[阅读更多](../expression/expressionadvanced.md)。
* [条件说明](../expression/conditional-instruction.md)和[集合管理](../expression/collection-management-functions.md)部分已移动并更新。
* [函数](../expression/functions.md)部分已更新为新示例。
* [toDateTime 函数](../functions/functiontodatetime.md)文档已更新，以反映时区语法的更改。
