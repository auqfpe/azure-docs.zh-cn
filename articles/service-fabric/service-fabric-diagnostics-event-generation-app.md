---
title: Azure Service Fabric 应用程序级别监视 | Microsoft Docs
description: 了解用于监视和诊断 Azure Service Fabric 群集的应用程序和服务级别事件和日志。
services: service-fabric
documentationcenter: .net
author: dkkapur
manager: timlt
editor: ''
ms.assetid: ''
ms.service: service-fabric
ms.devlang: dotnet
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: NA
ms.date: 03/20/2018
ms.author: dekapur
ms.openlocfilehash: 258aac722aa1c94ecf2cbf0524a3e4b53b8a788c
ms.sourcegitcommit: d74657d1926467210454f58970c45b2fd3ca088d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="application-and-service-level-logging"></a>应用程序和服务级别日志记录

对于服务监视的其他大多数环节，检测代码是一个基本要求。 我们只能通过检测来判断是否出错以及诊断需要解决哪些问题。 尽管在技术上可将调试器连接到生产服务，但这种做法并不常见。 因此，提供详细的检测数据非常重要。

某些产品可自动检测代码。 尽管这些解决方案能够正常运行，但几乎始终都要执行手动检测。 最后，必须提供足够的信息来对应用程序进行取证式的调试。 本文将介绍检测代码的不同方法，以及如何在不同的方法之间做出选择。

## <a name="eventsource"></a>EventSource

在 Visual Studio 中通过模板创建 Service Fabric 解决方案时，将生成 **EventSource** 派生类（**ServiceEventSource** 或 **ActorEventSource**）。 会创建一个模板，可将应用程序或服务的事件添加到其中。 **EventSource** 名称**必须**唯一，应该将它重命名，不要使用默认的模板字符串 MyCompany-&lt;solution&gt;-&lt;project&gt;。 使用多个同名的 **EventSource** 定义会导致运行时出现问题。 每个定义的事件必须具有唯一标识符。 如果标识符不唯一，将发生运行时失败。 某些组织为标识符预先分配了值范围，避免不同的开发团队之间发生冲突。 有关详细信息，请参阅 [Vance 的博客](https://blogs.msdn.microsoft.com/vancem/2012/07/09/introduction-tutorial-logging-etw-events-in-c-system-diagnostics-tracing-eventsource/)或 [MSDN 文档](https://msdn.microsoft.com/library/dn774985(v=pandp.20).aspx)。

## <a name="aspnet-core-logging"></a>ASP.NET Core 日志记录

必须认真规划如何检测代码。 适当的检测计划有助于避免代码基变得不稳定，从而需要重新检测代码。 为了降低风险，可以选择一个检测库，例如，Microsoft ASP.NET Core 中包含的 [Microsoft.Extensions.Logging](https://www.nuget.org/packages/Microsoft.Extensions.Logging/)。 ASP.NET Core 提供一个可在所选提供程序中使用的 [ILogger](https://docs.microsoft.com/aspnet/core/api/microsoft.extensions.logging.ilogger) 接口，同时尽量减轻对现有代码的影响。 可以在 Windows 和 Linux 上的 ASP.NET Core 中以及整个 .NET Framework 中使用代码，从而将检测代码标准化。

## <a name="choosing-a-logging-provider"></a>选择日志记录提供程序

如果应用程序对性能的依赖程度很高，则最好使用 EventSource。 与 ASP.NET Core 日志记录或任何可用的第三方解决方案相比，**EventSource** 使用的资源*通常*更少，并且性能更佳。  对于许多服务来说这并不是一个问题，但如果服务以性能为中心，则 **EventSource** 可能是更好的选择。 但是，若要获得结构化日志记录的这些优势，EventSource 要求工程团队做出大笔投资。 如果可能，建议对一些日志记录选项执行快速原型，然后选择最符合需求的选项。

## <a name="next-steps"></a>后续步骤

选择了用于检测应用程序和服务的日志记录提供程序之后，需要将日志和事件聚合才能将其发送到任何的分析平台。 阅读有关 [EventFlow](service-fabric-diagnostics-event-aggregation-eventflow.md) 和 [WAD](service-fabric-diagnostics-event-aggregation-wad.md) 的信息，以便更好地了解一些推荐选项。
