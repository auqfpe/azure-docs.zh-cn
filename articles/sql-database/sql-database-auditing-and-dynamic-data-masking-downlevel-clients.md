---
title: "针对 SQL 数据库审核的下层客户端支持和 IP 终结点更改 | Microsoft 文档"
description: "了解有关针对 SQL 数据库审核的下层客户端支持和 IP 终结点更改的信息。"
services: sql-database
documentationcenter: 
author: ronitr
manager: jhubbard
editor: 
ms.assetid: 4ef19ed1-e798-43a2-ad99-0e563f93ab53
ms.service: sql-database
ms.custom: secure and protect
ms.workload: data-management
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 07/10/2016
ms.author: ronitr
translationtype: Human Translation
ms.sourcegitcommit: 2ea002938d69ad34aff421fa0eb753e449724a8f
ms.openlocfilehash: 06c1dfbcfa365f6c34708021f63a756e295e2ab4


---
# <a name="sql-database---downlevel-clients-support-and-ip-endpoint-changes-for-auditing"></a>SQL 数据库 - 针对审核的下层客户端支持和 IP 终结点更改
对于支持 TDS 重定向的 SQL 客户端，可以自动使用[审核](sql-database-auditing-get-started.md)。

## <a name="a-idsubheading-1adownlevel-clients-support"></a><a id="subheading-1"></a>下层客户端支持
任何实现了 TDS 7.4 的客户端同样应当支持重定向。 例外情况包括不完全支持重定向功能的 JDBC 4.0 以及未实现重定向的 Tedious（适用于 Node.JS）。

对于“下层客户端”，即支持 TDS 7.3 版和更低版本的客户端 — 应修改连接字符串中的服务器 FQDN：

连接字符串中的原始服务器 FQDN：<服务器名称>.database.windows.net

连接字符串中的修改后的服务器 FQDN：<服务器名称>.database.**secure**.windows.net

“下层客户端”的部分列表包括：

* .NET 4.0 和更低版本，
* ODBC 10.0 和更低版本。
* JDBC（JDBC 虽然支持 TDS 7.4，但不完全支持 TDS 重定向功能）
* Tedious（适用于 Node.JS）

**注释：**上面的服务器 FDQN 修改可能还可用于应用 SQL Server 级别的审核策略，而无需在每个数据库中进行配置（临时缓解）。

## <a name="a-idsubheading-2aip-endpoint-changes-when-enabling-auditing"></a><a id="subheading-2"></a>启用审核时的 IP 终结点的更改
请注意，启用审核时将更改数据库的 IP 终结点。 如果你有严格的防火墙设置，请相应地更新这些防火墙设置。

新的数据库 IP 终结点将取决于数据库区域：

| 数据库区域 | 可能的 IP 终结点 |
| --- | --- |
| 中国北部 |139.217.29.176、139.217.28.254 |
| 中国东部 |42.159.245.65、42.159.246.245 |
| 澳大利亚东部 |104.210.91.32、40.126.244.159、191.239.64.60、40.126.255.94 |
| 澳大利亚东南部 |191.239.184.223、40.127.85.81、191.239.161.83、40.127.81.130 |
| 巴西南部 |104.41.44.161、104.41.62.230、23.97.99.54、104.41.59.191 |
| 美国中部 |104.43.255.70、40.83.14.7、23.99.128.244、40.83.15.176 |
| 东亚 |23.99.125.133、13.75.40.42、23.97.71.138、13.94.43.245 |
| 美国东部 2 |104.209.141.31、104.208.238.177、191.237.131.51、104.208.235.50 |
| 美国东部 |23.96.107.223、104.41.150.122、23.96.38.170、104.41.146.44 |
| 印度中部 |104.211.98.219、104.211.103.71 |
| 印度南部 |104.211.227.102、104.211.225.157 |
| 印度西部 |104.211.161.152、104.211.162.21 |
| 日本东部 |104.41.179.1、40.115.253.81、23.102.64.207、40.115.250.196 |
| 日本西部 |104.214.140.140、104.214.146.31、191.233.32.34、104.214.146.198 |
| 美国中北部 |191.236.155.178、23.96.192.130、23.96.177.169、23.96.193.231 |
| 欧洲北部 |104.41.209.221、40.85.139.245、137.116.251.66、40.85.142.176 |
| 美国中南部 |191.238.184.128、40.84.190.84、23.102.160.153、40.84.186.66 |
| 亚洲东南部 |104.215.198.156、13.76.252.200、23.97.51.109、13.76.252.113 |
| 欧洲西部 |104.40.230.120、13.80.23.64、137.117.171.161、13.80.8.37、104.47.167.215、40.118.56.193、104.40.176.73、40.118.56.20 |
| 美国西部 |191.236.123.146、138.91.163.240、168.62.194.148、23.99.6.91 |
| 加拿大中部 |13.88.248.106 |
| 加拿大东部 |40.86.227.82 |




<!--HONumber=Nov16_HO3-->

