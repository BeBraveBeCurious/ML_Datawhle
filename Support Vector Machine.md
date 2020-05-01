# SVM

## 没有免费午餐定理
如果我们不对特征空间进行先验假设，则所有算法的平均表现是一样的。
- 性能评估的必要性
- 先验知识的总结: 太阳每天会从东方升起
- 农夫养鸡
- 蜜蜂花蕊图

## 动画直观感受
[2-dimension SVM](https://github.com/BeBraveBeCurious/ML_Datawhle/blob/master/gif/8.SVM.gif)
[diverse dimensional SVM](https://github.com/BeBraveBeCurious/ML_Datawhle/blob/master/gif/9.SVM.gif)

## SVM linear模型

### 性能评估
最大化d (margin)
### support vector 支持向量
将最大化d (margin)的直线平行移动 与 样本交叉的向量 == Support Vector

### 样本+线性模型定义
#### 1. $m$ 个训练样本及标签: $(\vec X_1, y_1), (\vec X_2, y_2), (\vec X_3, y_3), \cdots, (\vec X_m, y_m)$
- $\vec X_i$ 在$R^2$空间中表现为$\begin{bmatrix}x_1 \\\x_2 \\\ \end{bmatrix}$
- $y_i = \pm 1$为二分类中向量$\vec X_i$的标签
#### 2. 线性模型待定参数$(\vec W, b)$
- Hyperplane: $\vec W^T\vec X + b = 0$, b是常数
- $\vec W$ 和 $\vec X_i$ 的特征维数相同，如
$ \vec X_1 = \begin{bmatrix}x_{11}\\\ x_{12}\\\ \cdots\\\ x_{1n} \end{bmatrix} $; 
$ \vec W = \begin{bmatrix}w_{1}\\\ w_{2}\\\ \cdots\\\ w_{n} \end{bmatrix} $; 
$ \vec W^T\vec X_{i} = \begin{bmatrix}w_{1} & w_{2} & \cdots & w_{n} \end{bmatrix}  \begin{bmatrix}x_{i1} \\\ x_{i2} \\\ \cdots \\\ x_{in} \end{bmatrix} = 常数 $
#### 3. 使用机器学习学习参数的步骤
- 限定一个模型：方程or复杂模型, i.e., 超平面$\vec W^T\vec X + b = 0$
- 模型里留出一些待定参数, i.e., $\vec W, b$
- 用训练样本和算法确定待定参数的具体取值, i.e., 确定$\vec W, b$的值，则完成机器学习过程。
#### 4. 训练集线性可分的定义
一条直线分开样本集的数学表示
$\exists (\vec W, b)$使训练样本$(\vec X_i, y_i), i = 1, \ldots, m$ 有
- 若$y_i = 1, \vec W^T\vec X + b \ge 0$
- 若$y_i = -1, \vec W^T\vec X +b \lt 0$
- 在$y_i = \pm 1$时，统一表达为$y_i[\vec W^T\vec X + b] \ge 0, \forall i = 1, \ldots, m. \tag{1} $

或者以下定义也可，求解的$\vec W, b$有一个负号差距。
- 若$y_i = 1, \vec W^T\vec X + b \lt 0$
- 若$y_i = -1, \vec W^T\vec X +b \ge 0$


## Linear SVM 优化模型
- 最大化margin变为最小化$\min   \quad   \frac{1}{2} ||\vec W||^2 = \frac {1}{2}(w_1^2 + w_2^2 + \ldots + w_n^2)$
- subject to $y_i[\vec W^T\vec X + b] \ge 1 $
- 1可以换为任意整数根据事实1
### 二次规划 Quadratic programming, 凸优化
- 目标函数为二次项
- 限制条件一次项，$y_i = \pm 1$
- 要么无解，要么只有一个极值

### 2个事实for目标转化
- 事实1: $\vec W^T\vec X + b = 0$ 与 $a\vec W^T\vec X + ab = 0, a \in R^+$ 是同一个平面
  - 若$(\vec W, b)$满足公式(1) 且 $a \in R^+$, 则$(a\vec W, ab)$也满足公式(1)
- 事实2: 点到平面的距离公式
  - 点$(x_0, y_0)$到平面$w_1x + w_2y + b = 0$的距离$d = \frac{\left|w_1x_0 + w_2y_0 + b\right|}{\sqrt{w_1^2 + w_2^2}}$
  - 向量$x_0$到超平面$\vec W^T\vec X + b = 0$的距离$d = \frac{|\vec W^T\vec X + b|}{||\vec W||}$, where $||\vec W|| = \sqrt{w_1^2 + w_2^2 + \ldots + w_n^2}$
  - 若$\vec X_0$为支持向量，使$d$最大则需使$||\vec w||$最小。
- 用$a$缩放$(\vec W, b)\rightarrow(a\vec W, ab), a \in R^+$使在所有的支持向量$\vec X_0$上有$|W^T\vec X_0 + b| = 1$
  - 此时，支持向量与平面的距离 $d = \frac{1}{||\vec W||}$

  
## SVM non-linear模型
### 非线性可分情况下，约束调节引入slack variable $\xi_i, \xi_i \ge 0$ 
- objective 相应变化为$\min\quad \frac{1}{2} ||\vec W||^2 + C \sum_{i=1}^m \xi_i$
- s.t. $ y_i[\vec W^T \vec X_i + b] \ge 1 - \xi_i, \xi_i \ge 0, i = 1, \ldots, m.$
- 若 $\xi_i$ 是一个非常大的数，那么$ 1 - \xi_i$会是一个比较小的负数，因此$ y_i[\vec W^T \vec X + b] \ge 1 - \xi_i $必然成立
- 优化目标中的regulation term正则项 $C \sum_{i=1}^n \xi_i$ 则使 $\xi_i$ 不能变得非常大
- regulation term正则项 $C \sum_{i=1}^n \xi_i$ 中的 $C$ 是事先设定的参数，平衡最大化margin和正则项的重要性
- libsvm 中 $C$ 的值是[-15:0.5:15],不断尝试； SVM中需要尝试的参数只有 $C$ 
- 已知量是 $ y_i, \vec X_i
- 待求量是 $\vec W, b, \xi_i$

### 低维到高维的映射 $\Phi(x)$
- [低维不可分的SVM图像1](https://github.com/BeBraveBeCurious/ML_Datawhle/blob/master/images/SVM-%E9%9D%9E%E7%BA%BF%E6%80%A7%E6%A0%B7%E6%9C%AC%E5%8F%AF%E5%88%86%E5%9B%BE.png)
- [低维不可分的SVM图像2](https://github.com/BeBraveBeCurious/ML_Datawhle/blob/master/images/SVM%E6%9B%B2%E9%9D%A2%E6%8A%95%E5%BD%B1.PNG)
- Vapnik仍然找直线，在高维空间找平面by高维映射的定义
1. XOR异或问题 in $R^2$
- 4个点坐标和类别
  - $$ x_1 = \begin{bmatrix}0 \\\0 \\\ \end{bmatrix} \in C_1; x_2 = \begin{bmatrix}1 \\\1 \\\ \end{bmatrix} \in C_1 $$
  - $$ x_3 = \begin{bmatrix}1 \\\0 \\\ \end{bmatrix} \in C_2; x_4 = \begin{bmatrix}0 \\\1 \\\ \end{bmatrix} \in C_2 $$
- 映射函数$X = \begin{bmatrix}a \\\b \\\ \end{bmatrix} \xrightarrow{\Phi} \Phi(x) = \begin{bmatrix}a^2 \\\b^2 \\\ a \\\b \\\ab \end{bmatrix}$
- 映射后的4点坐标
  - $$ \Phi(x_1) = \begin{bmatrix}0 \\\0 \\\0 \\\0 \\\0 \end{bmatrix}; \Phi(x_2) = \begin{bmatrix}1 \\\1 \\\1 \\\1 \\\1 \end{bmatrix} $$
  - $$ \Phi(x_3) = \begin{bmatrix}1 \\\0 \\\1 \\\0 \\\0 \end{bmatrix}; \Phi(x_4) = \begin{bmatrix}0 \\\1 \\\0 \\\1 \\\0 \end{bmatrix} $$ 
- 找 $\vec W, b$ 使 $\Phi(x_1),\Phi(x_2) \in C_1; \Phi(x_3),\Phi(x_4) \in C_2$
  - 两类区别主要在 $ab$ 最后一项
  - $\vec W = \begin{bmatrix} -1 \\\-1 \\\-1 \\\-1 \\\6 \end{bmatrix}$
  - $b = 1$
  


























