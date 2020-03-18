﻿# 实验 1A：创建 Azure 机器学习工作区

在本实验中，你将创建本课程其余部分将使用的 Azure 机器学习工作区。

## 开始前

需要拥有 Azure 订阅才能完成本课程中的实验。如果还没有 Azure 订阅，可以访问 [https://azure.microsoft.com](https://azure.microsoft.com) 注册免费试用版。

如果使用向你提供用于本课程的 Azure Pass 订阅，那么你的帐户可能尚未分配到订阅 **“所有者”** 角色，而本课程中某些操作可能需要此角色。要将你的帐户添加到 **“所有者”** 角色，请执行以下操作：

1. 登录到 [Azure 门户](https://portal.azure.com)并查看 **“订阅”**。
2. 选择使用 Azure Pass 创建的订阅（其名称类似于 **Azure Pass - 赞助**）。
3. 在订阅的边栏选项卡中，打开 **“我的权限”** 页面，然后单击上面的链接以查看订阅的完整访问详细信息。
4. 在 **“添加角色分配”** 下，单击 **“添加”**。然后选择以下选项并单击 **“保存”**：
    - **角色**：所有者
    - **分配访问权限对象**：Azure AD 用户、组或服务主体
    - **选择**：用于登录 Azure 的 Microsoft 帐户。

## 任务 1：创建 Azure ML 工作区

顾名思义，工作区是用于管理机器学习项目中需要处理的所有 Azure ML 资产的集中位置。

1. 在 [Azure 门户](https://portal.azure.com)中，创建一个新的 **机器学习** 资源，指定唯一的工作区名称，并在离你位置最近的区域创建一个新的资源组。选择 **“企业”** 工作区版本。

   > **注意**：基本版工作区的成本较低，但不包括自动机器学习、可视化设计器和数据偏移监视等功能。有关更多详细信息，请参阅 [Azure 机器学习定价](https://azure.microsoft.com/zh-cn/pricing/details/machine-learning/)。

2. 创建工作区及其相关资源后，可在门户中查看该工作区。

## 任务 2：探索 Azure 机器学习工作室界面

可在 Azure 门户中管理工作区资产，但是对于数据科学家而言，此工具包含许多不相关的信息，还包含与管理常规 Azure 资源有关的链接。作为替代，可以使用特定于 Azure ML 的 Web 界面管理工作区。

> **注意**：Azure ML 的基于 Web 的界面名为 *“Azure 机器学习工作室”*，可能会产生混淆，因为还有一个免费的 *“Azure 机器学习工作室”* 产品，其用途是使用可视化设计器来创建机器学习模型。新的工作室界面中包含此可视化设计器的更具扩展性的版本。

1. 在 Azure 机器学习工作区的 Azure 门户边栏选项卡中，单击此链接以启动 **“Azure 机器学习工作室”** ；或者在新的浏览器选项卡中打开 [https://ml.azure.com](https://ml.azure.com)。如果出现提示，请使用上个任务中使用的 Microsoft 帐户登录，然后选择你的 Azure 订阅和工作区。
2. 查看工作区的 Azure 机器学习工作室界面 - 可以从此处管理工作区中的所有资产。

## 任务 3：创建计算资源

Azure 机器学习的好处之一是能够创建基于云的计算，可以在其上大规模运行试验和训练脚本。

1. 在工作区的 Azure 机器学习工作室 Web 界面中，查看 **“计算”** 页。你将在此处管理数据科学活动的所有计算目标。
2. 在 **“计算实例”** 选项卡上，添加一个新的计算实例，为其提供一个唯一的名称，并使用 **“STANDARD_DS3_V2”** VM 类型模板。在后续实验中，你将使用此 VM 作为开发环境。
3. 创建笔记本 VM 时，切换到 **“训练群集”** 选项卡，并添加具有以下设置的新训练群集：
    * **计算名称**：aml-cluster
    * **虚拟机大小**：Standard_DS12_v2
    * **虚拟机优先级**：专用
    * **最少节点数**：0
    * **最大节点数**：4
    * **缩减之前的空闲秒数**：3600
4. 请注意 **“推理群集”选项卡**。可在此处创建和管理计算目标，将经过训练的模型作为 Web 服务部署到计算目标上，供客户端应用程序使用。
5. 请注意 **“附加计算”选项卡**。可在此处附加位于工作区外部的虚拟机或 Databricks 群集。

    > **注意**：你将在本课程的后面部分详细了解计算目标。

## 任务 4：创建数据资源

拥有可用于处理数据的计算资源后，需要设法存储和引入待处理的数。

1. 在工 *作室* 界面，查看 **“数据存储”** 页。你的 Azure ML 工作区已包括两个数据存储，它们基于与工作区一起创建的 Azure 存储帐户。这些用于存储笔记本、配置文件和数据。

   > **注意**：在实际环境中，你可能会添加引用业务数据存储的自定义数据存储 - 例如 Azure Blob 容器、Azure Data Lake、Azure SQL 数据库等。稍后你将在课程中对此进行探讨。

2. 在工 *作室* 界面，查看 **“数据集”** 页。数据集表示你计划在 Azure ML 中使用的特定数据文件或表。
3. 使用以下设置，从 Web 文件创建新数据集：
    * **基本信息**：
        * **Web URL**：https://aka.ms/diabetes-data
        * **名称**：diabetes dataset（*注意匹配大小写和空格*）
        * **数据集类型**：表格
        * **描述**：糖尿病数据
    * **设置和预览**：
        * **文件格式**：带分隔符
        * **分隔符**：逗号
        * **编码**：UTF-8
        * **列标题**：使用第一个文件的标题
        * **跳过行**：无
    * **架构**：
        * 包括除 **“路径”** 之外的所有列
        * 查看自动检测的类型
    * **确认详细信息**：
        * 创建数据集后，请勿对其进行分析
4. 创建数据集后，将其打开并查看 **“探索”** 页以查看数据示例。此数据表示已接受糖尿病测试的患者的详细信息，你将在本课程的许多后续实验中使用它。

    > **注意**：你可以生成数据集的*配置*文件以查看更多详细信息。你将在本课程的后面部分详细了解数据集。