﻿---
lab:
    title: '实验简介'
    module: '模块 0:欢迎'
---

# 实验简介

### Azure 机器学习服务：  信息汇总。

在本实验中，我们将介绍研讨会案例研究，其中包括使用 Azure 机器学习服务训练和部署预测性模型。本实验要求学生能够使用 Azure Notebooks 服务和 Azure 订阅。

# 研讨会案例研究

## 方案

你已分配新客户 Adventure Works LLC，这个客户向其客户销售自行车和自行车装备。

Adventure Works Cycles 是一家大型跨国制造公司。它制造自行车和自行车组件，并通过互联网渠道和经销商分销网络将产品销售到北美、欧洲和亚洲商业市场。它的总部设在华盛顿州柯克兰，拥有 290 名员工，在其整个市场群中设有多个区域销售团队。

在上一个财年取得成功后，Adventure Works 希望通过向现有客户销售额外产品来增加收入。虽然 Adventure Works 销售自行车配件和组件，但主要业务是销售自行车。  一项市场营销研究表明，许多购买过组件和配件的客户从未在 Adventure Works 购买过自行车。  他们希望面向这些客户开展自行车促销活动。  他们没有发送笼统的电子邮件或显示普通的在线广告，而是让数据科学团队创建了一个预测性机器学习模型，来确定客户最有可能购买哪种类型的自行车。  推断基于客户人口统计信息和销售数据，应该能够确定客户会购买的自行车类型：公路自行车、山地自行车或旅行自行车。  注意：  本项目的第二阶段将建立在此模型的基础上，用于预测客户将购买的特定自行车型号，但我们要慢慢来。

市场部相信你可以使用客户和销售历史记录来创建预测模型。  至关重要的是，该模型能够按需扩展，以便能够支持来自多种应用（即电子邮件、在线广告、直接邮寄广告等）的日益增长的使用量。需要提供一种使用模型对数据进行评分的标准方法，即一个易于使用的 API。市场部迫切希望尽快开发和部署模型，因此他们鼓励你找到加速开发的方法。

你的目标是执行以下操作：

- 执行探索性数据分析 (EDA)，以确定有助于预测客户购买的自行车的历史数据。 
- 根据 EDA 的结果，创建模型特征，即执行特征工程。
- 确定所需的机器学习模型的类型。  这将涉及尝试使用几种模型，评估其性能，并选择最佳模型。
- 在选择性能最佳模型的过程中，必须确定最优模型超参数。 
- 将经过训练的模型部署到方便调用模型的环境。
- 使用该模型进行测试。
- 监视模型的使用情况。

### 解决方案

你将使用 Azure 机器学习服务实现该解决方案。  Azure Notebooks 提供交互式开发环境 (IDE)，并且编程语言为 Python。Azure Notebooks 预先配置了所需的 Azure 机器学习软件开发工具包 (SDK) 以及大多数常用的 Python 数据科学相关包。 

- 你将使用数据工程师提供的数据提取内容，进行一些探索性数据分析并为模型创建几项额外的功能。

- 你将创建一个完全基于开放源代码的分类模型并评估其性能。

- 你将扩展创建的模型训练代码，以使用 Azure 机器学习服务。

- 你只是想要选择最佳的模型，但没有时间训练和比较大量的类型。  为了加快速度，你将使用 Azure 机器学习服务 AutoML 选择最佳模型并确定最优超参数值。 

- 你要将模型和容器映像注册到 Azure 机器学习服务工作区。

- 然后，你将部署模型并对其进行测试。 

- 你将通过 Python 监视模型。

每个实验中都给出了入门 Azure Notebooks，它提供了实验的结构。  有关上述步骤的更多详细信息，请参阅实验技术要求和 Azure 笔记本。
