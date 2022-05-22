# MCGE
蒙特卡洛梯度估计方法

https://www.sohu.com/a/339765442_500659

蒙特卡洛采样（MCS）

随机优化（SO）

变分推断（Variational Inference, VI）

在强化学习中的实际应用

方法综述

可以将梯度估计方法大致分为两类：

求解分布测度的导数，包括本文介绍的 score function gradient estimator

求解代价函数的导数，包括本文介绍的 pathwise gradient estimator

根据公式（2）待估计的梯度是

![image](https://user-images.githubusercontent.com/33678772/169677549-a4458506-9d3e-4037-b1e9-685aef39410d.png)


