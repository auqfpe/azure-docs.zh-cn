---
title: Azure 流分析查询测试 | Microsoft Docs
description: 如何测试流分析作业中的查询。
keywords: 测试查询, 对查询进行故障排除
documentation center: ''
services: stream-analytics
author: jseb225
manager: ryanw
ms.assetid: ''
ms.service: stream-analytics
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: data-services
ms.date: 04/20/2017
ms.author: jeanb
ms.openlocfilehash: 50bfce426bf48ba986887f8a2e2873fe04ea2507
ms.sourcegitcommit: 34e0b4a7427f9d2a74164a18c3063c8be967b194
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2018
---
# <a name="test-azure-stream-analytics-queries-in-the-azure-portal"></a>在 Azure 门户中测试 Azure 流分析查询

使用 Azure 流分析，可以在无需启动或停止作业的情况下在 Azure 门户中测试查询。

## <a name="test-the-input"></a>测试输入

1. 要使用示例输入数据进行测试，请右键单击任意输入，并选择“从文件上传示例数据”。 当前只能上传 JSON 格式的数据。 如果数据采用其他格式（如 CSV），则应在上传前将其转换为 JSON 格式。 可以使用任何开源转换工具（如 [CSV 到 JSON 转换器](http://www.convertcsv.com/csv-to-json.htm)）将数据转换为 JSON 格式。

    ![流分析查询编辑器测试查询](media/stream-analytics-test-query/stream-analytics-test-query-editor-upload.png)

2. 完成上传后，单击“测试”，以针对已提供的示例数据来测试此查询。

    ![流分析查询编辑器测试示例数据](media/stream-analytics-test-query/stream-analytics-test-query-editor-test.png)

浏览器中显示查询输出和下载结果链接，便于保存测试输出以供稍后使用。 现在可以轻松反复地修改查询，并对其进行重复测试，以查看输出有何变化。

![流分析查询编辑器示例输出](media/stream-analytics-test-query/stream-analytics-test-query-editor-samples-output.png)

由于在查询中使用了多个输出，因此可以分别查看两个输出的结果，并轻松在它们之间切换。

对浏览器中显示的结果感到满意后，即可保存查询、启动作业并使其在不出现错误的情况下处理事件。

## <a name="get-help"></a>获取帮助

如需进一步的帮助，请试用我们的 [Azure 流分析论坛](https://social.msdn.microsoft.com/Forums/en-US/home?forum=AzureStreamAnalytics)。

## <a name="next-steps"></a>后续步骤

* [Azure 流分析简介](stream-analytics-introduction.md)
* [Azure 流分析入门](stream-analytics-real-time-fraud-detection.md)
* [缩放 Azure 流分析作业](stream-analytics-scale-jobs.md)
* [Azure 流分析查询语言参考](https://msdn.microsoft.com/library/azure/dn834998.aspx)
* [Azure 流分析管理 REST API 参考](https://msdn.microsoft.com/library/azure/dn835031.aspx)
