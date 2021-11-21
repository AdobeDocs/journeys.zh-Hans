---
product: adobe campaign
title: 文档更新
description: 了解文档更新
feature: Journeys
role: User
level: Beginner
exl-id: ac5d2cec-0b48-4863-afe3-19ac5f61c9fd
source-git-commit: ed09f77617ae193ef7a217222f831f17ffc6b07c
workflow-type: tm+mt
source-wordcount: '902'
ht-degree: 100%

---

# 文档更新

此页面列出了
[!DNL Journey Orchestration]的所有文档更新。您还可以参阅 [!DNL Journey Orchestration][发行说明。](../release-notes/release-notes.md)

## 2021 年 9 月

* 以下函数页面已更新：[sethours](../functions/functionsethours.md)、[getListItem](../functions/functiongetlistitem.md)、[inSegment](../functions/functioninsegment.md)

* 添加了以下函数：[filter](../functions/functionfilter.md)、[intersect](../functions/functionintersect.md)、[toDateOnly](../functions/functiontodateonly.md)

* 在表达式编辑器文档中添加了 dateOnly 日期类型。[了解更多信息](../expression/data-types.md)

* 添加了有关自定义操作缓存持续时间的详细信息。[了解更多信息](../datasource/external-data-sources.md#section_wjp_nl5_nhb)

* 添加了有关自定义操作默认端口的信息。[了解更多信息](../action/url-configuration.md)

* 添加了在数据湖中查询历程步骤事件的常用示例。[了解更多信息](../building-journeys/query-examples.md)

## 2021 年 8 月

* 更新了使用动态 URL 路径和动态标头进行自定义操作的配置过程。[了解更多信息](../action/url-configuration.md)
* 添加了有关辅助功能的章节。[了解更多信息](../about/user-interface.md#accessibility)
* 添加了有关区段评估方法的章节。[了解更多信息](../segment/about-segments.md#evaluation-method-in-journey-orchestration)

## 2021 年 3 月 {#march-2021}

* 我们详细介绍了在 Adobe Experience Platform 中创建测试用户档案的完整过程。[了解更多信息](../building-journeys/creating-test-profiles.md)。

## 2021 月 1 日 {#january-2021}

* 添加了在创建用户档案的同时触发历程的最佳实践。[了解更多信息](../about/limitations.md#journeys-limitation-profile-creation)。

## 2020 年 10 月 {#october-2020}

* 添加了有关如何为事件配置超时的信息。[了解更多信息](../building-journeys/event-activities.md#listening-to-events-during-a-specific-time)。

## 2020 年 9 月 {#september-2020}

* 更新了接口描述部分，以反映新的&#x200B;**全选器**&#x200B;菜单。[了解更多信息](../about/user-interface.md)
* 添加了基于区段的历程的不重复新版本的有关注释。

## 2020 年 8 月 {#august-2020}

* 添加了有关如何对要在区段列表中显示的列进行排序和选择的信息。[了解更多信息](../building-journeys/segment-qualification-events.md)
* 添加了有关在选择区段后如何复制区段名称和 ID 的信息。[了解更多信息](../building-journeys/segment-qualification-events.md)
* Experience Platform 事件已在不同页面上得到协调。

## 2020 年 7 月 {#july-2020}

* 添加了一个链接，指向有关向 Adobe Experience Platform 报告事件的步骤的新教程视频。[了解更多信息](../building-journeys/sharing-overview.md)
* 事件活动部分已重新组织为每种事件类型的专用子部分。[了解更多信息](../building-journeys/event-activities.md)
* 添加了避免区段鉴别过载的最佳实践。[了解更多信息](../building-journeys/segment-qualification-events.md#speed-segment-qualification)
* 添加了注释，以说明如何在操作或条件出现错误后继续历程。[了解更多信息](../about/troubleshooting.md#section_h3q_kqk_fhb)
* 新增了 Alpha 功能部分，这些功能在有限的一组客户中进行测试。
* 添加了有关与智能服务集成的新部分。[了解更多信息](../ai-services/ai-services-overview.md)
* 在创建测试用户档案时添加了新部分。[了解更多信息](../building-journeys/testing-the-journey.md)
* 添加了有关如何在历程条件或操作中使用 **[!UICONTROL SegmentQualification]** 节点的信息。[了解更多信息](../building-journeys/segment-qualification-events.md)
* 已在 Campaign 事务性消息和事件出版中添加注释。请参阅[使用 Adobe Campaign](../action/working-with-adobe-campaign.md) 和 [使用 Adobe Campaign 操作](../building-journeys/using-adobe-campaign-actions.md)。
* 已在测试 Campaign Standard 实例 URL 时执行的检查中添加了信息。[了解更多信息](../action/working-with-adobe-campaign.md)
* 已添加有关与 AWS 或 Azure 服务器上托管的 Campaign Standard 实例兼容的反应事件的信息。[了解更多信息](../building-journeys/reaction-events.md)
* 在处理 Campaign Standard 事务性消息传递时，需要设置上限规则这一点已添加注释。[了解更多信息](../action/working-with-adobe-campaign.md)
* 在使用测试模式触发事件时，在生成实际事件时添加了注释。[了解更多信息](../building-journeys/testing-the-journey.md#firing_events)

## 2020 年 6 月 {#june-2020}

* 添加了有关如何更改自定义身份验证数据源的令牌缓存时间的信息。[了解更多信息](../datasource/external-data-sources.md#section_wjp_nl5_nhb)
* 更新了屏幕截图和文本，以反映已更改为 **[!UICONTROL Closed (no entrance)]** 的 **[!UICONTROL Finished]** 历程状态的重命名。
* 添加了有关如何为界面定义语言的信息。[了解更多信息](../about/user-interface.md)
* 个人历程的状态列表已移至[测试模式日志](../building-journeys/testing-the-journey.md#viewing_logs)部分。

## 2020 年 4 月 {#april-2020}

* 添加了有关体验事件模式定义的新部分，以帮助用户配置其第一个事件。[了解更多信息](../event/experience-event-schema.md)
* 更新了 [!DNL Journey Orchestration] 文档主页，添加了其他有用链接。[了解更多信息](../../journey-orchestration-home.md)

## 2020 年 3 月 {#march-2020}

* 在测试日志部分，添加了 _actionExecutionErrors_ 和 _fetchErrors_ 参数描述。[了解更多信息](../building-journeys/testing-the-journey.md#viewing_logs)
* 历程中使用的自定义操作的限制已更新。您还可以修改 **[!UICONTROL URL]** 字段和 **[!UICONTROL Authentication]** 参数。[了解更多信息](../action/about-custom-action-configuration.md)
* 添加了新的情景式帮助条目。自定义身份验证有效负载窗格（在操作和数据源中）现包含一个链接到此[部分](../datasource/external-data-sources.md#section_wjp_nl5_nhb)的帮助图标。
* 现在可以停止已关闭的历程。[了解更多信息](../building-journeys/using-the-journey-designer.md)
* 界面描述部分已重新组织。[了解更多信息](../about/user-interface.md)
* 多个事件的触发已添加到测试模式部分[阅读更多](../building-journeys/testing-the-journey.md#firing_events)
* 与新的 **[!UICONTROL Wait time in test]** 参数有关的“测试模式”模式部分已更新。[了解更多信息](../building-journeys/testing-the-journey.md)
* 测试日志部分已更新为外部调用错误代码和响应。[了解更多信息](../building-journeys/testing-the-journey.md#viewing_logs)
* 时区管理现在集中在历程属性面板中。在[此处](../building-journeys/changing-properties.md#timezone)和[此处](../building-journeys/timezone-management.md)了解更多信息
* 历程设计器部分已更新以反映最近的增强功能。[了解更多信息](../building-journeys/using-the-journey-designer.md)
* 界面描述已更新，其中包含有关情景帮助的信息。[了解更多信息](../about/user-interface.md#section_ksq_zr1_ffb)
* 浏览 **XDM 字段**&#x200B;时，将显示友好名称。相关部分已更新。[了解更多信息](../about/user-interface.md#friendly-names-display)

## 2020 年 2 月 {#february-2020}

* 快捷键部分已更新。**C** 键盘快捷键，允许您在所有列表屏幕中创建新项目。[了解更多信息](../about/user-interface.md#section_ksq_zr1_ffb)
* [数据源](../datasource/about-data-sources.md)和[操作](../action/action.md)概述页面已得到改进。

## 2020 月 1 日 {#january-2020}

* 已为[体验事件](../datasource/adobe-experience-platform-data-source.md)和[区段](../functions/functioninsegment.md)添加“获取限制条件”。

<!--* The [getBestSendTime documentation](../functions/functiongetbestsendtime.md) has been updated.-->

## 2019 年 12 月 {#december-2019}

* 所有屏幕截图都已更新，以反映界面的更改。
* 测试模式部分已更新。[了解更多信息](../building-journeys/testing-the-journey.md)
<!--* A warning has been added in the [email send time optimization](../building-journeys/wait-activity.md) and [predictive fatigue scores](../ai-services/leveraging-fatigue-scores.md) sections. These capabilities are only available to customers who use the [Adobe Experience Platform Data Connector](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html).-->
* 现在可删除已停止的历程。相关文档页面已更新。
* 在历程中检测到问题时，会显示两种颜色。红色表示错误，橙色表示警告。[了解更多信息](../about/troubleshooting.md)
* 高级表达式编辑器部分已更新。[了解更多信息](../expression/expressionadvanced.md)。
* [条件说明](../expression/conditional-instruction.md)和[集合管理](../expression/collection-management-functions.md)部分已移动并更新。
* [函数](../expression/functions.md)部分已更新为新示例。
* [toDateTime 函数](../functions/functiontodatetime.md)文档已更新，以反映时区语法的更改。
