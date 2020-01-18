---
product: Journeys
audience: end-user
user-guide-title: Journey Orchestration Help
index: true
translation-type: tm+mt
source-git-commit: 22569d66acb1637efc346f77864302b9e2cb6070

---


# 旅程安排帮助 {#using}

+ [产品文档](journey-orchestration-home.md)
+ What&#39;s new {#release-notes}
   + [发行说明](using/release-notes/release-notes.md)
   + [文档更新](using/release-notes/documentation-updates.md)
+ 从旅程安排开始 {#starting-with-journeys}
   + [关于旅程安排](using/about/about-journey-orchestration.md)
   + [开始](using/about/get-started.md)
   + [用户界面](using/about/user-interface.md)
   + [访问管理](using/about/access-management.md)
   + [故障排除](using/about/troubleshooting.md)
+ 配置活动 {#events-journeys}
   + [关于活动](using/event/about-events.md)
   + [定义有效负荷字段](using/event/defining-the-payload-fields.md)
   + [选择命名空间](using/event/selecting-the-namespace.md)
   + [定义事件键](using/event/defining-the-event-key.md)
   + [添加条件](using/event/adding-a-condition.md)
   + [预览有效负荷](using/event/previewing-the-payload.md)
   + [发送活动的其他步骤](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
+ 配置数据源 {#data-source-journeys}
   + [关于数据源](using/datasource/about-data-sources.md)
   + [字段组](using/datasource/field-groups.md)
   + [Adobe Experience platform数据源](using/datasource/adobe-experience-platform-data-source.md)
   + [外部数据源](using/datasource/external-data-sources.md)
+ 配置操作 {#action-journeys}
   + [关于操作](using/action/action.md)
   + [使用Adobe Campaign](using/action/working-with-adobe-campaign.md)
   + 使用第三方系统 {#action-third-party}
      + [关于自定义操作配置](using/action/about-custom-action-configuration.md)
      + [自定义操作限制](using/action/custom-action-limitations.md)
      + [URL配置](using/action/url-configuration.md)
      + [定义消息参数](using/action/defining-the-message-parameters.md)
+ 构建旅程 {#building-journeys}
   + 关于旅程构建 {#about-journey-building}
      + [创建旅程](using/building-journeys/journey.md)
      + [使用旅程设计师](using/building-journeys/using-the-journey-designer.md)
      + [更改属性](using/building-journeys/changing-properties.md)
      + [旅程版本](using/building-journeys/journey-versions.md)
      + [终止旅程](using/building-journeys/terminating-a-journey.md)
      + [时区管理](using/building-journeys/timezone-management.md)
   + 活动 {#about-journey-building}
      + [活动活动](using/building-journeys/event-activities.md)
      + 安排活动 {#orchestration-activities}
         + [关于安排活动](using/building-journeys/about-orchestration-activities.md)
         + [条件活动](using/building-journeys/condition-activity.md)
         + [结束活动](using/building-journeys/end-activity.md)
         + [等待活动](using/building-journeys/wait-activity.md)
      + 行动活动 {#action-activities}
         + [关于操作活动](using/building-journeys/about-action-activities.md)
         + [使用Adobe Campaign操作](using/building-journeys/using-adobe-campaign-actions.md)
         + [使用自定义操作](using/building-journeys/using-custom-actions.md)
   + [测试旅程](using/building-journeys/testing-the-journey.md)
   + [发布旅程](using/building-journeys/publishing-the-journey.md)
+ 使用高级表达式编辑器 {#building-advanced-conditions-journeys}
   + [关于高级表达式编辑器](using/expression/expressionadvanced.md)
   + 语法 {#syntax}
      + [概括性](using/expression/generalities.md)
      + [条件说明](using/expression/conditional-instruction.md)
      + [数据类型](using/expression/data-types.md)
      + [字段引用](using/expression/field-references.md)
      + [集合管理功能](using/expression/collection-management-functions.md)
      + [运营商](using/expression/operators.md)
   + 函数 {#main-functions-journey}
      + [主要功能](using/expression/functions.md)
      + Adobe Experience Platform {#adobe-experience-platform}
         + [getBestSendTime](using/functions/functiongetbestsendtime.md)
         + [inSegment](using/functions/functioninsegment.md)
      + 聚合 {#aggregation}
         + [平均](using/functions/functionavg.md)
         + [计数](using/functions/functioncount.md)
         + [countOnlyNull](using/functions/functioncountonlynull.md)
         + [countWithNull](using/functions/functioncountwithnull.md)
         + [distinctCount](using/functions/functiondistinctcount.md)
         + [distinctCountWithNull](using/functions/functiondistinctcountwithnull.md)
         + [max](using/functions/functionmax.md)
         + [min](using/functions/functionmin.md)
         + [和](using/functions/functionsum.md)
      + 转化 {#conversion}
         + [toBool](using/functions/functiontobool.md)
         + [toDateTime](using/functions/functiontodatetime.md)
         + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
         + [toDecimal](using/functions/functiontodecimal.md)
         + [toDuration](using/functions/functiontoduration.md)
         + [toInteger](using/functions/functiontointeger.md)
         + [toString](using/functions/functiontostring.md)
      + 日期 {#date}
         + [currentTime &#x200B; inMillis](using/functions/functioncurrenttimeinmillis.md)
         + [inLastDays](using/functions/functioninlastdays.md)
         + [inLastHours](using/functions/functioninlasthours.md)
         + [inLastMonths](using/functions/functioninlastmonths.md)
         + [inLastYears](using/functions/functioninlastyears.md)
         + [inNextDays](using/functions/functioninnextdays.md)
         + [inNextHours](using/functions/functioninnexthours.md)
         + [inNextMonths](using/functions/functioninnextmonths.md)
         + [inNextYears](using/functions/functioninnextyears.md)
         + [现在](using/functions/functionnow.md)
         + [nowWithDelta](using/functions/functionnowwithdelta.md)
         + [setHours](using/functions/functionsethours.md)
         + [setDays](using/functions/functionsetdays.md)
      + 列表 {#list}
         + [不同](using/functions/functiondistinct.md)
         + [distinctWithNull](using/functions/functiondistinctwithnull.md)
         + [in](using/functions/functionin.md)
         + [listSize](using/functions/functionlistsize.md)
         + [serializeList](using/functions/functionserializelist.md)
         + [排序](using/functions/functionsort.md)
      + 数学 {#math}
         + [随机](using/functions/functionrandom.md)
         + [圆](using/functions/functionround.md)
      + 字符串 {#string}
         + [concat](using/functions/functionconcat.md)
         + [cont](using/functions/functioncontain.md)
         + [containWithIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
         + [equalWithIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [isEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [长度](using/functions/functionlength.md)
         + [lower](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notEqualWithIgnoreCase](using/functions/functionnotequalignorecase.md)
         + [替换](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [substr](using/functions/functionsubstr.md)
         + [修剪](using/functions/functiontrim.md)
         + [上](using/functions/functionupper.md)
         + [uid](using/functions/functionuuid.md)
+ 构建报告{#journey-reports}
   + [关于旅程报告](using/reporting/about-journey-reports.md)
   + [创建旅程报告](using/reporting/creating-your-journey-reports.md)
   + [指标和维度](using/reporting/metrics-and-dimensions.md)
+ 用例{#use-cases-journeys}
   + 简单用例{#use-case-simple}
      + [关于简单的用例](using/usecase/about-the-simple-use-case.md)
      + [配置活动](using/usecase/configuring-the-event.md)
      + [配置数据源](using/usecase/configuring-the-data-source.md)
      + [构建旅程](using/usecase/simple-uc-building-the-journey.md)
   + 高级用例{#use-case-advanced}
      + [关于高级用例](using/usecase/about-the-advanced-use-case.md)
      + [配置活动](using/usecase/configuring-the-events.md)
      + [配置数据源](using/usecase/configuring-the-data-sources.md)
      + [构建旅程](using/usecase/building-the-journey.md)
   + [利用疲劳分数](using/usecase/leveraging-fatigue-scores.md)

