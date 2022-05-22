# MCGE
蒙特卡洛梯度估计方法

https://www.sohu.com/a/339765442_500659

蒙特卡洛采样（MCS）

随机优化（SO）

变分推断（Variational Inference, VI）

在强化学习中的实际应用

方法综述

公式（1）中的积分内是一个分布和代价函数的乘积，在对其梯度进行近似估计时，可以从两个方面进行求导。由此，可以将梯度估计方法大致分为两类：

求解分布测度的导数，包括本文介绍的 score function gradient estimator
求解代价函数的导数，包括本文介绍的 pathwise gradient estimator
根据公式（2）待估计的梯度是
![image](https://user-images.githubusercontent.com/33678772/169677549-a4458506-9d3e-4037-b1e9-685aef39410d.png)

Score Function Gradient Estimator (SFGE)
SFGE 是最经典的方法，也是适用性最好的方法，在强化学习中的策略梯度优化问题里，有一个算法叫做 REINFORCE，正是基于 SFGE 来做的。SFGE 也常常被用于解决目标函数不可导的优化问题以及一些黑盒优化问题。
