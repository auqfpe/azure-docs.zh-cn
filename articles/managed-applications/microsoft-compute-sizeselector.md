---
title: "Azure 托管应用程序 SizeSelector UI 元素 | Microsoft Docs"
description: "介绍了 Azure 托管应用程序的 Microsoft.Compute.SizeSelector UI 元素"
services: azure-resource-manager
documentationcenter: na
author: tfitzmac
manager: timlt
editor: tysonn
ms.service: azure-resource-manager
ms.devlang: na
ms.topic: reference
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/12/2017
ms.author: tomfitz
ms.openlocfilehash: 72278b1999f89e5bd5f203794ba3a403a695c933
ms.sourcegitcommit: 3ab5ea589751d068d3e52db828742ce8ebed4761
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
# <a name="microsoftcomputesizeselector-ui-element"></a>Microsoft.Compute.SizeSelector UI 元素
一个用于为一个或多个虚拟机实例选择大小的控件。 [创建 Azure 托管应用程序](publish-service-catalog-app.md)时使用此元素。

## <a name="ui-sample"></a>UI 示例
![Microsoft.Compute.SizeSelector](./media/managed-application-elements/microsoft.compute.sizeselector.png)

## <a name="schema"></a>架构
```json
{
  "name": "element1",
  "type": "Microsoft.Compute.SizeSelector",
  "label": "Size",
  "toolTip": "",
  "recommendedSizes": [
    "Standard_D1",
    "Standard_D2",
    "Standard_D3"
  ],
  "constraints": {
    "allowedSizes": [],
    "excludedSizes": []
  },
  "osPlatform": "Windows",
  "imageReference": {
    "publisher": "MicrosoftWindowsServer",
    "offer": "WindowsServer",
    "sku": "2012-R2-Datacenter"
  },
  "count": 2,
  "visible": true
}
```

## <a name="remarks"></a>备注
- `recommendedSizes` 必须至少包含一个大小。 第一个建议的大小将用作默认值。
- 如果某个建议的大小在所选位置中不可用，则会自动跳过该大小。 而且将使用下一个建议的大小。
- 将隐藏未在 `constraints.allowedSizes` 中指定的任何大小，会显示未在 `constraints.excludedSizes` 中指定的任何大小。
`constraints.allowedSizes` 和 `constraints.excludedSizes` 都是可选的，并且不能同时使用。 可以通过调用[为订阅列出可用虚拟机大小](/rest/api/compute/virtualmachines/virtualmachines-list-sizes-region)来确定可用大小的列表。
- 必须指定 `osPlatform`，它可以是 **Windows** 或 **Linux**。 它用来确定虚拟机的硬件成本。
- 对于第一方映像，将省略 `imageReference`，对于第三方映像，将提供此参数。 它用来确定虚拟机的软件成本。
- `count` 用来为元素设置合适的乘数。 它支持静态值（例如 **2**），也支持来自其他元素的动态值（例如 `[steps('step1').vmCount]`）。 默认值为 **1**。

## <a name="sample-output"></a>示例输出
```json
"Standard_D1"
```

## <a name="next-steps"></a>后续步骤
* 有关托管应用程序的简介，请参阅 [Azure 托管应用程序概述](overview.md)。
* 有关创建 UI 定义的简介，请参阅 [CreateUiDefinition 入门](create-uidefinition-overview.md)。
* 有关 UI 元素中的公用属性的说明，请参阅 [CreateUiDefinition 元素](create-uidefinition-elements.md)。
