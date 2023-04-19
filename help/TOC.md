---
product: adobe campaign
user-guide-title: Journey Orchestration
title: Journey Orchestration 指南
user-guide-description: 提供实施和构建历程的操作说明。
index: true
feature: Journeys
source-git-commit: 137637a753ba44cc4f8e397b77c3fc076ec3de3f
workflow-type: ht
source-wordcount: '447'
ht-degree: 100%

---


# [!DNL Journey Orchestration] 指南 {#using}

+ [产品文档](journey-orchestration-home.md)
+ 新增功能 {#release-notes}
   + [发行说明](using/release-notes/release-notes.md)
   + [文档更新](using/release-notes/documentation-updates.md)
   + [升级到 Journey Optimizer](using/release-notes/upgrade-to-ajo.md)
+ [!DNL Journey Orchestration] 入门{#starting-with-journeys}
   + [关于 [!DNL Journey Orchestration]](using/about/about-journey-orchestration.md)
   + [限制](using/about/limitations.md)
   + [快速入门](using/about/get-started.md)
   + [用户界面](using/about/user-interface.md)
   + [访问管理](using/about/access-management.md)
   + [故障排除](using/about/troubleshooting.md)
   + [与外部系统集成](using/about/external-systems.md)
+ 配置事件 {#events-journeys}
   + 关于事件 {#about-events}
      + [一般原则](using/event/about-events.md)
      + [数据周期](using/event/about-data-cycle.md)
      + [创建事件](using/event/about-creating.md)
      + [利用 Adobe Analytics](using/event/about-analytics.md)
      + [关于 ExperienceEvent Schemas](using/event/experience-event-schema.md)
      + [用于发送事件的其他步骤](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
   + [定义有效负载字段](using/event/defining-the-payload-fields.md)
   + [选择命名空间](using/event/selecting-the-namespace.md)
   + [定义事件键](using/event/defining-the-event-key.md)
   + [预览有效负载](using/event/previewing-the-payload.md)
+ 配置数据源 {#data-source-journeys}
   + [关于数据源](using/datasource/about-data-sources.md)
   + [字段组](using/datasource/field-groups.md)
   + [Adobe Experience Platform 数据源](using/datasource/adobe-experience-platform-data-source.md)
   + [外部数据源](using/datasource/external-data-sources.md)
+ 配置操作 {#action-journeys}
   + [关于操作](using/action/action.md)
   + [使用 Adobe Campaign Standard](using/action/working-with-adobe-campaign.md)
   + [使用 Adobe Campaign v7/v8](using/action/acc-action.md)
   + 使用第三方系统 {#action-third-party}
      + [关于自定义操作配置](using/action/about-custom-action-configuration.md)
      + [URL 配置](using/action/url-configuration.md)
      + [定义操作参数](using/action/defining-the-message-parameters.md)
+ 使用区段 {#configuring-segment}
   + [关于区段](using/segment/about-segments.md)
   + [创建区段](using/segment/creating-a-segment.md)
   + [在条件中使用区段](using/segment/using-a-segment.md)
+ 构建历程 {#building-journeys}
   + 关于历程构建 {#about-journey-building}
      + [创建历程](using/building-journeys/journey.md)
      + [使用历程设计器](using/building-journeys/using-the-journey-designer.md)
      + [更改属性](using/building-journeys/changing-properties.md)
      + [历程版本](using/building-journeys/journey-versions.md)
      + [终止历程](using/building-journeys/terminating-a-journey.md)
      + [时区管理](using/building-journeys/timezone-management.md)
      + [测试用户档案](using/building-journeys/creating-test-profiles.md)
   + 活动 {#about-journey-building}
      + 事件活动 {#events-activities}
         + [关于事件活动](using/building-journeys/event-activities.md)
         + [一般事件](using/building-journeys/general-events.md)
         + [反应 事件](using/building-journeys/reaction-events.md)
         + [区段鉴别事件](using/building-journeys/segment-qualification-events.md)
      + 编排活动 {#orchestration-activities}
         + [关于编排活动](using/building-journeys/about-orchestration-activities.md)
         + [条件活动](using/building-journeys/condition-activity.md)
         + [结束活动](using/building-journeys/end-activity.md)
         + [等待活动](using/building-journeys/wait-activity.md)
      + 操作活动 {#action-activities}
         + [关于操作活动](using/building-journeys/about-action-activities.md)
         + [使用 Adobe Campaign Standard](using/building-journeys/using-adobe-campaign-actions.md)
         + [使用 Adobe Campaign v7/v8](using/building-journeys/using-adobe-campaign-classic.md)
         + [使用自定义操作](using/building-journeys/using-custom-actions.md)
         + [从一个历程转到另一个历程](using/building-journeys/jump.md)
         + [更新用户档案](using/building-journeys/update-profiles.md)
   + [测试历程](using/building-journeys/testing-the-journey.md)
   + [发布历程](using/building-journeys/publishing-the-journey.md)
   + 与 Adobe Experience Platform 共享历程步骤 {#sharing-journey-steps}
      + [历程步骤共享概述](using/building-journeys/sharing-overview.md)
      + [步骤事件字段列表](using/building-journeys/sharing-field-list.md)
      + 旧版步骤事件字段{#legacy-step-event-fields}
         + [关于旧版字段](using/building-journeys/sharing-legacy-fields.md)
         + [journeySteps 事件常用字段](using/building-journeys/sharing-common-fields.md)
         + [journeyStep 事件操作执行字段](using/building-journeys/sharing-execution-fields.md)
         + [journeyStep 事件数据提取字段](using/building-journeys/sharing-fetch-fields.md)
         + [journeyStep 事件身份字段](using/building-journeys/sharing-identity-fields.md)
         + [历程字段](using/building-journeys/sharing-journey-fields.md)
      + [查询示例](using/building-journeys/query-examples.md)
+ 构建表达式 {#building-advanced-conditions-journeys}
   + [概述](using/expression/expressionadvanced.md)
   + 语法 {#syntax}
      + [概述](using/expression/generalities.md)
      + [条件指令](using/expression/conditional-instruction.md)
      + [数据类型](using/expression/data-types.md)
      + [字段引用](using/expression/field-references.md)
      + [收藏集管理函数](using/expression/collection-management-functions.md)
      + [操作员](using/expression/operators.md)
      + [历程属性](using/expression/journey-properties.md)
      + [示例](using/expression/advanced-editor-use-cases.md)
   + 函数 {#main-functions-journey}
      + [主要函数](using/expression/functions.md)
      + Adobe Experience Platform {#adobe-experience-platform}
         + [inSegment](using/functions/functioninsegment.md)
      + 聚合 {#aggregation}
         + [avg](using/functions/functionavg.md)
         + [count](using/functions/functioncount.md)
         + [countOnlyNull](using/functions/functioncountonlynull.md)
         + [countWithNull](using/functions/functioncountwithnull.md)
         + [distinctCount](using/functions/functiondistinctcount.md)
         + [distinctCountWithNull](using/functions/functiondistinctcountwithnull.md)
         + [max](using/functions/functionmax.md)
         + [min](using/functions/functionmin.md)
         + [sum](using/functions/functionsum.md)
      + 转化 {#conversion}
         + [toBool](using/functions/functiontobool.md)
         + [toDateOnly](using/functions/functiontodateonly.md)
         + [toDateTime](using/functions/functiontodatetime.md)
         + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
         + [toDecimal](using/functions/functiontodecimal.md)
         + [toDuration](using/functions/functiontoduration.md)
         + [toInteger](using/functions/functiontointeger.md)
         + [toString](using/functions/functiontostring.md)
      + 日期 {#date}
         + [currentTimeInMillis](using/functions/functioncurrenttimeinmillis.md)
         + [inLastDays](using/functions/functioninlastdays.md)
         + [inLastHours](using/functions/functioninlasthours.md)
         + [inLastMonths](using/functions/functioninlastmonths.md)
         + [inLastYears](using/functions/functioninlastyears.md)
         + [inNextDays](using/functions/functioninnextdays.md)
         + [inNextHours](using/functions/functioninnexthours.md)
         + [inNextMonths](using/functions/functioninnextmonths.md)
         + [inNextYears](using/functions/functioninnextyears.md)
         + [now](using/functions/functionnow.md)
         + [nowWithDelta](using/functions/functionnowwithdelta.md)
         + [setHours](using/functions/functionsethours.md)
         + [setDays](using/functions/functionsetdays.md)
         + [updateTimeZone](using/functions/functionupdatetimezone.md)
      + 列表 {#list}
         + [distinct](using/functions/functiondistinct.md)
         + [distinctWithNull](using/functions/functiondistinctwithnull.md)
         + [filter](using/functions/functionfilter.md)
         + [getListItem](using/functions/functiongetlistitem.md)
         + [in](using/functions/functionin.md)
         + [intersect](using/functions/functionintersect.md)
         + [limit](using/functions/functionlimit.md)
         + [listSize](using/functions/functionlistsize.md)
         + [serializeList](using/functions/functionserializelist.md)
         + [sort](using/functions/functionsort.md)
      + 数学 {#math}
         + [random](using/functions/functionrandom.md)
         + [round](using/functions/functionround.md)
      + 字符串 {#string}
         + [concat](using/functions/functionconcat.md)
         + [contain](using/functions/functioncontain.md)
         + [containIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
         + [equalIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [isEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [长度](using/functions/functionlength.md)
         + [lower](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notequalIgnoreCase](using/functions/functionnotequalignorecase.md)
         + [replace](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [split](using/functions/functionsplit.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [substr](using/functions/functionsubstr.md)
         + [trim](using/functions/functiontrim.md)
         + [upper](using/functions/functionupper.md)
         + [uuid](using/functions/functionuuid.md)
+ 构建报告{#journey-reports}
   + [关于历程报告](using/reporting/about-journey-reports.md)
   + [创建历程报告](using/reporting/creating-your-journey-reports.md)
   + [量度和维度](using/reporting/metrics-and-dimensions.md)
+ 与智能服务集成{#use-case-advanced}
   + [关于 AI 集成](using/ai-services/ai-services-overview.md)
   + [利用客户人工智能](using/ai-services/leveraging-customer-ai.md)
+ 用例{#use-cases-journeys}
   + 发送个性化电子邮件{#use-case-simple}
      + [关于简单用例](using/usecase/about-the-simple-use-case.md)
      + [配置事件](using/usecase/configuring-the-event.md)
      + [配置数据源](using/usecase/configuring-the-data-source.md)
      + [构建历程](using/usecase/simple-uc-building-the-journey.md)
   + 构建跨渠道历程{#use-case-advanced}
      + [关于高级用例](using/usecase/about-the-advanced-use-case.md)
      + [配置事件](using/usecase/configuring-the-events.md)
      + [配置数据源](using/usecase/configuring-the-data-sources.md)
      + [构建历程](using/usecase/building-the-journey.md)
   + [使用 Campaign v7/v8 发送消息](using/usecase/campaign-classic-use-case.md)
   + [使用自定义操作动态传递收藏集](using/usecase/collections.md)
+ 使用 API{#working-with-apis}
   + [历程 API 入门](using/api/journeys-apis.md)
   + [API 上限](using/api/capping.md)
   + [API 限制](using/api/throttling.md)
