# 1. 介绍

　　在机器学习中，经常遇到需要优化一些函数的值的情况：给定函数 $f: \mathbb{R}^{n} \rightarrow \mathbb{R}$ ，求 $x\in\mathbb{R}^{n}$ 使得 $f(x)$ 最大或者最小。一些在机器学习中可以看做是优化问题的例子：最小方差、逻辑回归和支持向量机等。

　　对于一种特殊的优化问题——凸优化问题(Convex optimization problems)，在很多情况下可以找到全局最优解。

 

# 2. 凸集(Convex Sets)

　　**凸集(Convex Sets)**：对于任意的 $x,y \in C$ 且 $ \theta \in \mathbb{R} $ ，有 $\theta x + (1-\theta)y \in C $ ，集合 $C$ 是凸的，其中 $0 \leqslant \theta \leqslant 1$ 。

　　直观上理解就是，从集合 $C$ 中任取出两个点，然后在这两个点间画一条线段，则这条线段上的每个点仍然属于 $C$ 。点 $\theta x + (1-\theta)y  $ 叫做点 $x$ 和 $y$ 的**凸连接(convex combination)**。

![2019-05-27_082949.png](https://i.loli.net/2019/05/27/5ceb2fa50299837180.png)

<center>图1：凸集(左)和非凸集(右)的例子</center>

## 2.1 凸集例子

- 所有的 $\mathbb{R}^n $ ，即所有的实数向量。

- 非负象限 $\mathbb{R}^n_+ $ ，即元素非0的 $\mathbb{R}^n $ 向量。
- 范数(Norm balls)，给 $\mathbb{R}^n $ 加上范数，那么集合{ ${x: ||x|| \leqslant }$ 1} 是为凸集。
- 仿射子空间和多面体
  - 仿射子空间：给定矩阵 $A \in \mathbb{R}^{m \times n}$ 和向量 $b \in \mathbb{R^m}$ ，一个仿射子空间是集合 {$ x \in \mathbb{R}^n: Ax = b $} 
  - 多面体：即为集合 {$x \in \mathbb{R}^n: Ax \preceq b$ }，$\preceq$ 表示element-wise的小于等于
- 凸集的交∩依然为凸集。凸集的并∪不一定为凸集。
- 正半定矩阵。实际上，正定矩阵、负定矩阵和负半定矩阵也均为凸集。

 

# 3. 凸函数
