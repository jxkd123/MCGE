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

Pathwise Gradient Estimator (PGE)

PGE 的思路是将待学习的参数从分布中变换到代价函数中，核心是做分布变换（即所谓的 reparameterization ，重参数化），

计算原来分布下的期望梯度时，由于变换后的分布不包含求导参数，可将求导和积分操作进行对换，从而基于 MC 对梯度进行估计。

PGE 的一个重要理论依据是 Law of the Unconscious Statistician (LOTUS) ，即：

![image](https://user-images.githubusercontent.com/33678772/169677916-bf51147c-7cd6-432a-a913-f03a2b2528d7.png)

![image](https://user-images.githubusercontent.com/33678772/169677918-0c66b46f-945f-4e99-993c-c5ea37a4a26c.png)

从定理中可以看到，计算一个函数的期望，可以不知道其分布，只需要知道一个简单分布，以及从简单分布到当前分布的映射关系即可。

PGE推导过程

基于 Law of the Unconscious Statistician (LOTUS) 对 PGE 进行推导，如下：

![image](https://user-images.githubusercontent.com/33678772/169677931-7bc4e28a-919f-4885-814f-ead24257cfad.png)

![image](https://user-images.githubusercontent.com/33678772/169677935-14aefa7c-a205-4f35-b280-8a9e6fc1cea1.png)

其中 。从推导中可以看出，分布中的参数被 push 到了代价函数中，从而可以将求导和积分操作进行对换。

分布变换是统计学中一个基本的操作，在计算机中实际产生各种常见分布的随机数时，都是基于均匀分布的变换来完成的。有一些常见的分布变换可参见下表：

![image](https://user-images.githubusercontent.com/33678772/169677996-5c466f4a-678d-405e-adab-4a83336d7c34.png)

