# Expectation_Maximization

## 白话一轮游 EM
### 两枚硬币经典例子
 ![image](https://github.com/BeBraveBeCurious/ML_Datawhle/blob/master/images/EM-Example-coin.jpg)
 ![image](https://github.com/BeBraveBeCurious/ML_Datawhle/blob/master/images/EM-Example-coin-explaination.jpg)
 - 需注意图二中顺序应该是E1-E2-M1
 - E步有两步，初始化参数 + 观察预期
 - M步是重新估计参数，得到新的theta_A和theta_B
[CSDN](https://blog.csdn.net/justry24/article/details/78043307)

## K-means 与 EM 的关系
- k-means是两个步骤交替进行，可以分别看成E步和M步；
- M步中将每类的中心更新为分给该类各点的均值，可以认为是在「各类分布均为单位方差的高斯分布」的假设下，最大化似然值；
- E步中将每个点分给中心距它最近的类（硬分配），可以看成是EM算法中E步（软分配）的近似

[知乎](https://www.zhihu.com/question/49972233/answer/119434460)

