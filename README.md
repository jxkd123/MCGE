# MCGE
蒙特卡洛梯度估计方法

https://www.sohu.com/a/339765442_500659

蒙特卡洛采样（MCS）

随机优化（SO）

变分推断（Variational Inference, VI）

在强化学习中的实际应用

强化学习中的一大类问题是无模型的策略搜索问题，即通过优化累计回报的均值学习到最优策略。所谓累计回报的均值形式如下：

![image](https://user-images.githubusercontent.com/33678772/169677738-9bb10eb3-73d1-4d74-8321-f54dc97aa1d8.png)

方法综述

可以将梯度估计方法大致分为两类：

求解分布测度的导数，包括本文介绍的 score function gradient estimator

求解代价函数的导数，包括本文介绍的 pathwise gradient estimator

根据公式（2）待估计的梯度是

![image](https://user-images.githubusercontent.com/33678772/169677549-a4458506-9d3e-4037-b1e9-685aef39410d.png)

SFGE的推导过程

![image](https://user-images.githubusercontent.com/33678772/169677682-d23a00ad-95c0-4311-be2e-f650ed9754c2.png)

利用 MC 采样可以估计出梯度，如下：

![image](https://user-images.githubusercontent.com/33678772/169677688-509fd184-3465-40d7-a17a-7cb000f9f886.png)


