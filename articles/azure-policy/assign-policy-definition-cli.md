---
title: 使用 Azure CLI 创建策略分配以识别 Azure 环境中的不合规资源 | Microsoft Docs
description: 使用 PowerShell 创建 Azure 策略分配以识别不合规的资源。
services: azure-policy
keywords: ''
author: bandersmsft
ms.author: banders
ms.date: 03/13/2018
ms.topic: quickstart
ms.service: azure-policy
ms.custom: mvc
ms.openlocfilehash: 1ff1240073e25bf406e7da6b79135264376a5b3f
ms.sourcegitcommit: 48ab1b6526ce290316b9da4d18de00c77526a541
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="create-a-policy-assignment-to-identify-non-compliant-resources-in-your-azure-environment-with-the-azure-cli"></a>使用 Azure CLI 创建策略分配以识别 Azure 环境中的不合规资源

若要了解 Azure 中的符合性，第一步是确定资源的状态。 本快速入门逐步讲解如何创建策略分配，以识别未使用托管磁盘的虚拟机。

此过程结束时，你可以成功识别哪些虚拟机未使用托管磁盘。 这些虚拟机不符合策略分配要求。

Azure CLI 用于从命令行或脚本创建和管理 Azure 资源。 本指南使用 Azure CLI 创建策略分配，并识别 Azure 环境中的不合规资源。

如果你还没有 Azure 订阅，可以在开始前创建一个[免费](https://azure.microsoft.com/free/)帐户。

[!INCLUDE [cloud-shell-try-it.md](../../includes/cloud-shell-try-it.md)]

本快速入门需要运行 Azure CLI 2.0.4 版或更高版本，以便在本地安装并使用 CLI。 若要查找版本，请运行 `az --version`。 如果需要进行安装或升级，请参阅[安装 Azure CLI 2.0]( /cli/azure/install-azure-cli)。



## <a name="create-a-policy-assignment"></a>创建策略分配

本快速入门将创建一个策略分配，并分配“审核不带托管磁盘的虚拟机”定义。 此策略定义可识别不符合策略定义中设置的条件的资源。

运行以下命令创建策略分配：

```
az policy assignment create --name 'Audit Virtual Machines without Managed Disks Assignment' --scope '<scope>' --policy '<policy definition ID>' --sku 'standard'
```

上述命令使用以下信息：

- **名称** - 策略分配的显示名称。 本例使用了“审核不带托管磁盘分配的虚拟机”。
- **策略** - 策略定义 ID，用作创建分配的依据。 在本例中，此值为策略定义“审核不带托管磁盘的虚拟机”。 若要获取策略定义 ID，请运行以下命令：`az policy definition show --name 'Audit Virtual Machines without Managed Disks Assignment'`
- **范围** - 范围确定在其中实施策略分配的资源或资源组。 它可以从订阅延伸至资源组。 请务必将 &lt;scope&gt; 替换为资源组的名称。
- **SKU** – 此命令创建使用标准层的策略分配。 使用标准层可以实现大规模管理、符合性评估和补救。 有关定价层的其他详细信息，请参阅 [Azure 策略定价](https://azure.microsoft.com/pricing/details/azure-policy)。


## <a name="identify-non-compliant-resources"></a>识别不合规的资源

若要查看此新分配下不合规的资源，请运行以下命令获取策略分配 ID：

```
$policyAssignment = Get-AzureRmPolicyAssignment | where {$_.properties.displayName -eq "Audit Virtual Machines without Managed Disks"}
```

```
$policyAssignment.PolicyAssignmentId
```

有关策略分配 ID 的详细信息，请参阅 [Get-AzureRMPolicyAssignment](/powershell/module/azurerm.resources/get-azurermpolicyassignment)。

接下来，运行以下命令，获取输出到 JSON 文件中的不合规资源的资源 ID：

```
armclient post "/subscriptions/<subscriptionID>/resourceGroups/<rgName>/providers/Microsoft.PolicyInsights/policyStates/latest/queryResults?api-version=2017-12-12-preview&$filter=IsCompliant eq false and PolicyAssignmentId eq '<policyAssignmentID>'&$apply=groupby((ResourceId))" > <json file to direct the output with the resource IDs into>
```

结果应如以下示例所示：

```
{
"@odata.context":"https://management.azure.com/subscriptions/<subscriptionId>/providers/Microsoft.PolicyInsights/policyStates/$metadata#latest",
"@odata.count": 3,
"value": [
{
    "@odata.id": null,
    "@odata.context": "https://management.azure.com/subscriptions/<subscriptionId>/providers/Microsoft.PolicyInsights/policyStates/$metadata#latest/$entity",
      "ResourceId": "/subscriptions/<subscriptionId>/resourcegroups/<rgname>/providers/microsoft.compute/virtualmachines/<virtualmachineId>"
    },
    {
      "@odata.id": null,
      "@odata.context": "https://management.azure.com/subscriptions/<subscriptionId>/providers/Microsoft.PolicyInsights/policyStates/$metadata#latest/$entity",
      "ResourceId": "/subscriptions/<subscriptionId>/resourcegroups/<rgname>/providers/microsoft.compute/virtualmachines/<virtualmachine2Id>"
         },
{
      "@odata.id": null,
      "@odata.context": "https://management.azure.com/subscriptions/<subscriptionId>/providers/Microsoft.PolicyInsights/policyStates/$metadata#latest/$entity",
      "ResourceId": "/subscriptions/<subscriptionName>/resourcegroups/<rgname>/providers/microsoft.compute/virtualmachines/<virtualmachine3ID>"
         }

]
}

```

这些结果与 Azure 门户视图中“不合规资源”下通常所列的结果类似。

## <a name="clean-up-resources"></a>清理资源

本教程系列中的其他指南建立在本快速入门的基础之上。 如何打算继续学习后续教程，请不要清除本快速入门中创建的资源。 如果不打算继续学习，请运行以下命令删除创建的分配：

```azurecli
az policy assignment delete –name Audit Virtual Machines without Managed Disks Assignment --scope /subscriptions/ <subscriptionID> / <resourceGroupName>
```

## <a name="next-steps"></a>后续步骤

本快速入门已分配一个策略定义用于识别 Azure 环境中的不合规资源。

若要详细了解如何分配策略并确保**将来**创建的资源合规，请继续学习以下教程：

> [!div class="nextstepaction"]
> [创建和管理策略](./create-manage-policy.md)
