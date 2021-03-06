---
title: Azure Mobile Engagement - 主要特性
description: 介绍 Azure Mobile Engagement 的主要特性
services: mobile-engagement
documentationcenter: mobile
author: piyushjo
manager: erikre
editor: ''
ms.assetid: d98bafb6-4fd0-4cc3-8c2f-962af70c416c
ms.service: mobile-engagement
ms.workload: mobile
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 08/19/2016
ms.author: piyushjo
ms.openlocfilehash: ce160fbc78c7069b0114599455403e5e20771c6c
ms.sourcegitcommit: 34e0b4a7427f9d2a74164a18c3063c8be967b194
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2018
---
# <a name="azure-mobile-engagement---key-features"></a>Azure Mobile Engagement - 主要特性
> [!IMPORTANT]
> Azure Mobile Engagement 已在 2018 年 3 月 31 日停用。 此页将在不久之后删除。
> 

本文提供有关 Mobile Engagement 平台主要特性的高级概述。 

## <a name="general"></a>**常规**
* **查找适用于所有重要平台的 SDK** 适用于所有重要平台（ iOS、Android、Universal Windows、 Windows Phone Silverlight、Kindle、Cordova）的 SDK。 
  我们提供易于集成的 SDK 和有用的文档，帮助你在所选的任何平台上开始使用。 
* **独立的 SaaS 门户**允许轻松访问市场营销团队而无需浏览 Azure 管理门户。 
* **开放 REST API 的可用性** 为了与使用开放平台 API 的 CRM/CMS/IT 系统集成，并通过这些系统自动执行任务，我们提供开放 REST API 和 .NET SDK 来使用这些 API，使用这些 API 能够轻松与 Mobile Engagement 集成并通过其自动执行任务。 请参阅[此内容](mobile-engagement-api-authentication.md)来了解详细信息。 
* **可用的 Power BI 连接器** 还可以获取相应数据，在 Power BI 仪表板中提供关键分析图表。 请参阅此[指南](https://powerbi.microsoft.com/en-us/documentation/powerbi-content-pack-azure-mobile/)
* **安全和隐私保障**作为 Azure 系列的一部分，Azure Mobile Engagement 遵循有关云服务所需的安全性和隐私的所有标准最佳实践。

## <a name="actionable-analytics"></a>**可行性分析**
* **实时监视数据**可以使用“监视”模块跟踪实时数据分析，该模块可以实时显示详细信息，如会话、事件、错误和崩溃。 浏览此[文章](mobile-engagement-concepts.md)以了解基本概念。 
  
    ![][1]
  
    ![][2]        
* **查看聚合数据**通过使用“分析”模块，还可以获得更加丰富的聚合分析数据视图，从而让可以基于应用版本和时间段轻松筛选数据。
  
    ![][3]        
* **深入了解用户和保留模式**
  
    ![][4]        
* **深入了解用户来源以及在屏幕上的停留时间**
  
    ![][5]        
  
    ![][6]        
* **找出应用用户访问的屏幕，以及如何优化用户路径**这有助于用户发现希望他们看到的屏幕和功能。
  
    ![][7]        
  
    ![][8]        
* **深入了解应用中的最常见事件，并基于这些事件了解业务流程** 
  
    ![][9]    
* **跟踪常见错误和崩溃，深入了解开发团队**
  
    ![][10]        
  
    ![][11]    
* **了解用户是通过哪些设备和网络访问应用，从而优化应用** 
  
    ![][12]    

## <a name="targeted--personalized-push-notifications"></a>**定向和个性化推送通知**
* **基于收集的任何数据创建细分类别**为此可以使用任何事件/会话/活动/作业/崩溃/错误/标记数据。
  
    ![][13]
  
    ![][14]        
* **每天跟踪创建的细分类别的历史记录**
  
    ![][15]    
* **发送有针对性的通知**以常用细分类别（如新/老用户等）为目标，或者发送给自定义创建的细分类别
  
    ![][16]    
* **根据方案发送应用外/系统外推送通知以及基于 HTML 的丰富应用内推送通知**
  
    ![][17]    
  
    ![][18]    
* **以要显示于应用中特定屏幕/活动的应用内通知为目标**
  
    ![][19]    
* **当用户单击通知时指定“操作”**可以像单击通知即打开网页或导航到应用内的特定屏幕一样简单。 
  
    ![][20]
* **发送本地化的通知**以使其以让应用用户感觉最舒服的语言吸引应用用户。 
  
    ![][21]    
* **指定活动的开始和结束时间** 
  
    ![][22]    
* 通过注册测试设备并将测试通知仅发送到此设备来**轻松测试通知**。
  
    ![][23]    
* **轻松设置应用内通知以显示为快速轮询/调查**  
  
    ![][24]
* 为通知**获取推送活动统计信息**，了解你通知有多成功。
  
    ![][25]    
* **通过使用应用信息/标记和表情符号来轻松个性化通知** 
  
    ![][26]    
  
    ![][27]    
* **设置推送限制以防止骚扰用户**你不想向应用用户发送大量推送，使得看上去像是在骚扰他们。 这就是推送限制功能的作用，它允许根据细分类别的粒度配置推送限制。 
  
    ![][28]            

<!-- Images -->
[1]: ./media/mobile-engagement-key-features/monitor1.png
[2]: ./media/mobile-engagement-key-features/monitor2.png
[3]: ./media/mobile-engagement-key-features/analytics-filter.png
[4]: ./media/mobile-engagement-key-features/retention.png
[5]: ./media/mobile-engagement-key-features/analytics-geomap.png
[6]: ./media/mobile-engagement-key-features/analytics-session-length.png
[7]: ./media/mobile-engagement-key-features/analytics-activities.png
[8]: ./media/mobile-engagement-key-features/analytics-userpath.png
[9]: ./media/mobile-engagement-key-features/analytics-events.png
[10]: ./media/mobile-engagement-key-features/analyics-errors.png
[11]: ./media/mobile-engagement-key-features/analyics-errors-details.png
[12]: ./media/mobile-engagement-key-features/technicals.png
[13]: ./media/mobile-engagement-key-features/segment.png
[14]: ./media/mobile-engagement-key-features/segment-creation.png
[15]: ./media/mobile-engagement-key-features/segment-history.png
[16]: ./media/mobile-engagement-key-features/segment-push.png
[17]: ./media/mobile-engagement-key-features/out-of-app.png
[18]: ./media/mobile-engagement-key-features/in-app-push.png
[19]: ./media/mobile-engagement-key-features/push-in-activity.png
[20]: ./media/mobile-engagement-key-features/push-action.png
[21]: ./media/mobile-engagement-key-features/push-languages.png
[22]: ./media/mobile-engagement-key-features/push-timeframe.png
[23]: ./media/mobile-engagement-key-features/push-test.png
[24]: ./media/mobile-engagement-key-features/push-poll.png
[25]: ./media/mobile-engagement-key-features/push-stats.png
[26]: ./media/mobile-engagement-key-features/push_personalized.png
[27]: ./media/mobile-engagement-key-features/push_emoji.png
[28]: ./media/mobile-engagement-key-features/push_limits.png









