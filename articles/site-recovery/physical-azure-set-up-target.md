---
title: "准备目标（物理到 Azure）| Microsoft Docs"
description: "本文介绍如何准备 Azure 环境以将运行 Windows 或 Linux 的物理服务器复制到 Azure。"
services: site-recovery
author: bsiva
manager: abhemraj
ms.service: site-recovery
ms.topic: article
ms.date: 03/05/2018
ms.author: bsiva
ms.openlocfilehash: a2465bb3397a175b6ad8b8be0de933dfae1dee5b
ms.sourcegitcommit: 168426c3545eae6287febecc8804b1035171c048
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2018
---
# <a name="prepare-target-vmware-to-azure"></a>准备目标（VMware 到 Azure）

本文介绍如何准备 Azure 环境以将运行 Windows 或 Linux 的物理服务器 (x64) 复制到 Azure。

## <a name="prerequisites"></a>先决条件

本文假设：
- 已创建恢复服务保管库，用于保护物理服务器。 已从 [Azure 门户](http://portal.azure.com "Azure 门户")创建恢复服务保管库。
- 已[设置本地环境](physical-azure-disaster-recovery.md)，用于将物理服务器复制到 Azure。

## <a name="prepare-target"></a>准备目标

完成“**步骤 1: 选择保护目标**”和“**步骤 2: 准备源**”后，会转到“**步骤 3: 目标**”

![准备目标](./media/physical-azure-set-up-target/prepare-target-physical-to-azure.png)

1. 订阅：从下拉菜单中，选择要将物理服务器复制到的“订阅”。
2. **部署模型：**选择部署模型（经典或 Resource Manager）

根据选择的部署模型运行验证，确保要将物理服务器复制并故障转移到的目标订阅中至少具有一个兼容的存储帐户和虚拟网络。

成功完成验证后，单击“确定”转到下一步。

如果你没有兼容的资源管理器存储帐户或虚拟网络，则可单击页面顶部的“+ 存储帐户”或“+ 网络”按钮来创建一个。

## <a name="next-steps"></a>后续步骤
[配置复制设置](vmware-azure-set-up-replication.md)。
