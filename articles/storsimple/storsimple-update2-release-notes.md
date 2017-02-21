---
title: "StorSimple 8000 系列 Update 2 发行说明 | Microsoft Docs"
description: "介绍 StorSimple 8000 系列 Update 2 的新功能、问题和解决方法。"
services: storsimple
documentationcenter: NA
author: SharS
manager: carmonm
editor: 
ms.assetid: e2c8bffd-7fc5-4b77-b632-a4f59edacc3a
ms.service: storsimple
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: TBD
ms.date: 05/24/2016
ms.author: v-sharos
translationtype: Human Translation
ms.sourcegitcommit: 219dcbfdca145bedb570eb9ef747ee00cc0342eb
ms.openlocfilehash: ddd34019dbef06d324437dee1430488cb2c9a639


---
# <a name="storsimple-8000-series-update-2-release-notes"></a>StorSimple 8000 系列 Update 2 发行说明
## <a name="overview"></a>概述
以下发行说明描述 StorSimple 8000 系列 Update 2 的新功能，并标识重要的待解决问题。 其中还包含此版本随附的 StorSimple 软件、驱动程序和磁盘固件更新的列表。 

Update 2 可应用于任何运行 Release (GA)、Update 0.1 到 Update 1.2 的 StorSimple 设备。 与 Update 2 相关联的设备版本是 6.3.9600.17673。

在 StorSimple 解决方案中部署更新之前，请查看发行说明中所包含的信息。

> [!IMPORTANT]
> * 安装此更新需要大约 4-7 小时（包括 Windows 更新）。 
> * Update 2 具有软件、LSI 驱动程序和 SSD 固件更新。
> * 对于新版本，由于我们分阶段推出更新，你可能不能立即看到更新。 请等待几天，然后再次扫描更新，因为很快就会提供这些更新。
> 
> 

## <a name="whats-new-in-update-2"></a>Update 2 中的新增功能
Update 2 推出以下新功能。

* **本地固定卷** – 在以前发布的 StorSimple 8000 系列中，数据块基于使用情况分层到云中。 无法保证块会留在本地。 在 Update 2 中，当创建卷时，可以将卷指定为本地固定，来自该卷的主要数据不会分层到云。 本地固定卷的快照将仍被复制到云作备份，以便云可以用于数据移动性和灾难恢复目的。 此外，还可以更改卷类型（即，将分层卷转换为本地固定卷，以及将本地固定卷转换为分层卷）。 
* **StorSimple 虚拟设备改进** – 此前的 StorSimple 8000 系列将虚拟设备定位为灾难恢复或开发/测试解决方案。 只有一个虚拟设备模型（模型 1100）。 Update 2 引入了两个虚拟设备模型： 
  
  * 8010（以前称为 1100） – 无更改；具有 30 TB 的容量并使用 Azure 标准存储。
  * 8020 – 具有 64 TB 的容量并使用 Azure 高级存储，以提高性能。
    
    具有单个 VHD 用于两个虚拟设备模型 (8010/8020)。 首次启动虚拟设备时，它将检测平台参数并应用正确的模型版本。
* **网络改进** – Update 2 包含以下网络改进：
  
  * 可以针对云启用多个 NIC，以便在某个 NIC 出现故障时进行故障转移。
  * 路由改进，具有已启用云块的固定指标。
  * 在故障转移之前的出现故障的资源上重新尝试联机。
  * 服务故障的新警报。
* **更新改进** – 在 Update 1.2 和更早版本中，StorSimple 8000 系列通过两个渠道更新：针对群集、iSCSI 等的 Windows Update，以及针对二进制文件和固件的 Microsoft Update。
    Update 2 对针对所有更新包使用 Microsoft Update。 这应该会使安装补丁或执行故障转移所需的时间更少。 
* **固件更新**：包括以下固件更新：
  
  * LSI: lsi_sas2.sys 产品版本 2.00.72.10
  * 仅 SSD（没有 HDD 更新）：XMGG、XGEG、KZ50、F6C2 和 VR08
* **主动支持** – Update 2 使 Microsoft 可以从设备中提取其他诊断信息。 当运营团队标识有问题的设备时，我们可以更好地从设备中收集信息并诊断问题。 **通过接受 Update 2，我们就能够提供此主动支持**。    

## <a name="issues-fixed-in-update-2"></a>在 Update 2 中修复的问题
下表提供在 Updates 2 中已修复问题的摘要。    

| 否。 | 功能 | 问题 | 适用于物理设备 | 适用于虚拟设备 |
| --- | --- | --- | --- | --- |
| 1 |网络接口 |升级到 Update 1 之后，StorSimple Manager 服务报告在一个控制器上报告 Data2 和 Data3 端口出现故障。 现在已修复此问题。 |是 |否 |
| 2 |更新 |升级到 Update 1 之后，在多个设备上的 Azure 经典门户中出现有声警报通知。 现在已修复此问题。 |是 |否 |
| 3 |Openstack 身份验证 |使用 Openstack 作为云服务提供商时，可能会收到一条显示云身份验证字符串过长的错误。 此问题已解决。 |是 |否 |

## <a name="known-issues-in-update-2"></a>Update 2 中的已知问题
下表提供此版本中已知问题的摘要。

| 否。 | 功能 | 问题 | 注释/解决方法 | 适用于物理设备 | 适用于虚拟设备 |
| --- | --- | --- | --- | --- | --- |
| 1 |磁盘仲裁 |在极少数情况下，如果 8600 设备的 EBOD 机箱中的大部分磁盘断开连接，导致没有磁盘仲裁，则会使存储池脱机。 即使磁盘重新连接，存储池也将保持脱机状态。 |需要重新启动设备。 如果问题仍然存在，请联系 Microsoft 支持部门以了解后续步骤。 |是 |否 |
| 2 |错误的控制器 ID |当执行控制器更换时，控制器 0 可能显示为控制器 1。 控制器更换过程中，从对等节点加载图像时，控制器 ID 可能最初显示为对等控制器的 ID。 在极少数情况下，此行为也可能在系统重新启动后出现。 |不需要用户操作。 控制器更换过程完成后，这种情况将自动解决。 |是 |否 |
| 3 |存储帐户 |使用存储服务删除存储帐户是一个不受支持的方案。 这将导致无法在其中检索用户数据的情况。 | |是 |是 |
| 4 |设备故障转移 |不支持从同一源设备将某个卷容器多次故障转移到不同的目标设备。 从单个不活动的设备故障转移到多个设备，会使第一个故障转移设备上卷容器丢失数据所有权。 进行此类故障转移后，当你在 Azure 经典门户中查看这些卷容器时，会发现它们的显示或表现有所不同。 | |是 |否 |
| 5 |安装 |安装 StorSimple Adapter for SharePoint 期间，你需要提供设备 IP 才能成功完成安装。 | |是 |否 |
| 6 |Web 代理 |如果 Web 代理服务器配置将 HTTPS 作为指定的协议，则设备到服务通信将受到影响，并且设备将进入脱机状态。 在此过程中，会在进程中生成支持包，耗用设备上的大量资源。 |请确保 Web 代理 URL 将 HTTP 作为指定的协议。 有关详细信息，请转至[配置设备的 Web 代理](storsimple-configure-web-proxy.md)。 |是 |否 |
| 7 |Web 代理 |如果在注册的设备上配置并启用 Web 代理，将需要重新启动设备上的主动控制器。 | |是 |否 |
| 8 |云高延迟和高 I/O 工作负载 |当 StorSimple 设备同时遇到非常高的云延迟（大约秒数）和高 I/O 工作负载情况时，设备卷将进入降级状态，并且 I/O 可能会出现故障，发生“设备未就绪”错误。 |需要手动重新启动设备控制器或执行设备故障转移，才可以从这种情况中恢复。 |是 |否 |
| 9 |Azure PowerShell |当使用 StorSimple cmdlet **Get-AzureStorSimpleStorageAccountCredential &#124; Select-Object -First 1 -Wait** 选择第一个对象以便创建新的 **VolumeContainer** 对象时，该 cmdlet 将返回所有对象。 |将该 cmdlet 放在括号中，如下所示：**(Get Azure StorSimpleStorageAccountCredential) &#124;Select-Object -First 1 -Wait** |是 |是 |
| 10 |迁移 |当传递多个卷容器进行迁移时，只有第一个卷容器的最新备份的 ETA 准确。 此外，在迁移第一个卷容器中的前 4 个备份后，将开始并行迁移。 |建议你一次迁移一个卷容器。 |是 |否 |
| 11 |迁移 |还原后，不会将卷添加到备份策略或虚拟磁盘组。 |需要将这些卷添加到备份策略以创建备份。 |是 |是 |
| 12 |迁移 |迁移完成后，5000/7000 系列设备不得访问已迁移的数据容器。 |建议在迁移完成并提交之后删除迁移的数据容器。 |是 |否 |
| 13 |克隆和 DR |运行 Update 1 的 StorSimple 设备不能对运行 Update 1 前的软件的设备克隆或执行灾难恢复。 |需要将目标设备更新为 Update 1 以允许这些操作 |是 |是 |
| 14 |迁移 |当卷组没有关联的卷时，5000 7000 系列设备上用于迁移的配置备份可能会出现故障。 |删除所有不含关联卷的空卷组，然后重新配置备份。 |是 |否 |
| 15 |Azure PowerShell cmdlet 和本地固定卷 |无法通过 Azure PowerShell cmdlet 创建本地固定卷。 （通过 Azure PowerShell 创建的任何卷都会被分层。） |始终使用 StorSimple Manager 服务来配置本地固定卷。 |是 |否 |
| 16 |本地固定卷的可用空间 |如果删除本地固定卷，可能不会立即更新新卷的可用空间。 StorSimple Manager 服务大约会每隔一小时更新本地可用的空间。 |请等待一个小时，然后再尝试创建新卷。 |是 |否 |
| 17 |本地固定卷 |还原作业会在“备份目录”中显示临时快照备份，但仅会在还原作业期间显示。 此外，它还在“**备份策略**”页上显示一个前缀为 **tmpCollection** 的虚拟磁盘组，但仅会在还原作业期间显示。 |如果还原作业仅具有本地固定卷或混合了本地固定卷与分层卷，则可能发生此问题。 如果还原作业仅包含分层卷，将不会发生此问题。 无需用户干预。 |是 |否 |
| 18 |本地固定卷 |如果取消还原作业，并随即发生控制器故障转移，还原作业将显示“**失败**”而不是“**已取消**”。 如果还原作业失败，并随即发生控制器故障转移，还原作业将显示“**已取消**”而不是“**失败**’。 |如果还原作业仅具有本地固定卷或混合了本地固定卷与分层卷，则可能发生此问题。 如果还原作业仅包含分层卷，将不会发生此问题。 无需用户干预。 |是 |否 |
| 19 |本地固定卷 |如果取消还原作业，或者如果恢复失败，且发生控制器故障转移，“**作业**”页上将会显示其他还原作业。 |如果还原作业仅具有本地固定卷或混合了本地固定卷与分层卷，则可能发生此问题。 如果还原作业仅包含分层卷，将不会发生此问题。 无需用户干预。 |是 |否 |
| 20 |本地固定卷 |如果你尝试将分层卷（通过 Update 1.2 或更早版本创建和克隆）转换为本地固定卷，并且设备空间不足或云服务中断，则克隆会受损。 |此问题只会出现在使用 Update 2 之前软件创建和克隆的卷中。 这种情况应该很少见。 | | |
| 21 |卷转换 |卷转换正在进行时（分层到本地固定，反之亦然），请勿更新连接到此卷上的 ACR。 更新 ACR 可能导致数据损坏。 |如果需要，请在卷转换之前更新 ACR，不要在转换进行时执行任何进一步的 ACR 更新。 | | |

## <a name="controller-and-firmware-updates-in-update-2"></a>Update 2 中的控制器和固件更新
此版本将更新设备上的驱动程序和磁盘固件。

* 有关 LSI 固件更新的详细信息，请参阅 Microsoft 知识库文章 3121900。 
* 有关磁盘固件更新的详细信息，请参阅 Microsoft 知识库文章 3121899。

## <a name="virtual-device-updates-in-update-2"></a>Update 2 中的虚拟设备更新
此更新不能应用于虚拟设备。 将需要新建虚拟设备。 

## <a name="next-step"></a>后续步骤
了解如何在 StorSimple 设备上[安装 Update 2](storsimple-install-update-2.md)。




<!--HONumber=Nov16_HO3-->

