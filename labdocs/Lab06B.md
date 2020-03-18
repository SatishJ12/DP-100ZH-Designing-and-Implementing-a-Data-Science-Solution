﻿# 实验 6B：发布管道

创建管道之后，可以发布可用于启动该管道的 REST 终结点。这样就可以按需或按计划运行管道。

## 开始前

在开始本实验之前，请确保你已完成[实验 1A](Lab01A.md) 和[实验 1B](Lab01B.md)，其中包括创建 Azure 机器学习工作区和本实验中使用的其他资源的任务；并完成了 [Lab 6A](Lab06A.md)，在其中创建了你将在此试验中发布的管道。

## 任务 1：发布管道

在此任务中，你将创建一个管道来训练和注册模型。

1. 在 [Azure 机器学习工作室](https://ml.azure.com)中，查看工作区的 **“计算”** 页面，并在 **“计算实例”** 选项卡上启动计算实例。
2. 当计算实例运行时，在浏览器中刷新 Azure 机器学习工作室网页，确保身份验证会话没有过期。然后单击 **Jupyter** 链接以在新的浏览器选项卡中打开 Jupyter 主页。
3. 在 Jupyter 主页的 **Users/DP100** 文件夹中，打开 **06B - Publishing a Pipeline.ipynb** 笔记本。然后阅读笔记本中的笔记，依次运行每个代码单元。
4. 笔记本中的代码运行完毕后，在 **“文件”** 菜单上单击 **“关闭并停止”** 以关闭它及其 Python 内核。然后关闭所有 Jupyter 浏览器选项卡。
5. 在 Azure 机器学习工作室中的 **“计算”** 页面上，选择计算实例，然后单击 **“停止”** 以将其关闭。