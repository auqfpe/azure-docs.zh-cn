NC 和 NV 大小也称为支持 GPU 的实例。 这些是针对不同方案和用例优化的专用虚拟机，其中包含 NVIDIA 的 GPU 卡。 NV 大小已针对远程可视化效果、流式处理、游戏、编码和 VDI 方案进行了优化和设计，使用 OpenGL 和 DirectX 之类的框架。 NC 大小更适用于计算密集型和网络密集型应用程序和算法，包括基于 CUDA 和 OpenCL 的应用程序和模拟。 


NV 实例采用 NVIDIA 的 Tesla M60 GPU 卡和 NVIDIA GRID，适用于桌面加速型应用程序和虚拟桌面，方便客户可视化其数据或模拟。 用户可以在 NV 实例上可视化其图形密集型工作流以获取高级图形功能，并可额外运行单精度工作负荷，例如编码和渲染。 Tesla M60 采用 4096 CUDA 核心，其双 GPU 设计最多可以运行 36 个 1080p H.264 流。 

NC 实例采用 NVIDIA 的 Tesla K80 卡。 通过将 CUDA 用于能源勘探应用、碰撞模拟、光纤跟踪渲染、深度学习等领域，用户现在分析数据的速度要快得多。 Tesla K80 采用 4992 CUDA 核心，其双 GPU 设计最多可以执行 2.91 兆次的双精度浮点运算，以及 8.93 兆次的单精度浮点运算。

## <a name="nv-instances"></a>NV 实例

| 大小 | CPU 核心数 | 内存：GiB | 本地 SSD：GiB | GPU |
| --- | --- | --- | --- | --- |
| Standard_NV6 |6 |56 |380 | 1 |
| Standard_NV12 |12 |112 |680 | 2 |
| Standard_NV24 |24 |224 |1440 | 4 |

1 GPU = 半块 M60 卡。

**受支持的操作系统**

* Windows Server 2016、Windows Server 2012 R2 - 请参阅[适用于 Windows 的 N 系列驱动程序安装](../articles/virtual-machines/virtual-machines-windows-n-series-driver-setup.md)

## <a name="nc-instances"></a>NC 实例

| 大小 | CPU 核心数 | 内存：GiB | 本地 SSD：GiB | GPU |
| --- | --- | --- | --- | --- |
| Standard_NC6 |6 |56 | 380 | 1 |
| Standard_NC12 |12 |112 | 680 | 2 |
| Standard_NC24 |24 |224 | 1440 | 4 |
| Standard_NC24r* |24 |224 | 1440 | 4 |

1 GPU = 半块 K80 卡。

*支持 RDMA

**受支持的操作系统**

* Windows Server 2016、Windows Server 2012 R2 - 请参阅[适用于 Windows 的 N 系列驱动程序安装](../articles/virtual-machines/virtual-machines-windows-n-series-driver-setup.md)
* Ubuntu 16.04 LTS - 请参阅[适用于 Linux 的 N 系列驱动程序安装](../articles/virtual-machines/virtual-machines-linux-n-series-driver-setup.md)

<br>
