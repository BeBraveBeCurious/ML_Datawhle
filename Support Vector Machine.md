# SVM

## 没有免费午餐定理
如果我们不对特征空间进行先验假设，则所有算法的平均表现是一样的。
- 性能评估的必要性
- 先验知识的总结: 太阳每天会从东方升起
- 农夫养鸡

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
- Hyperplane: $\vec W^TX + b = 0$, b是常数
- $\vec W$ 和 $\vec X_i$ 的特征维数相同，如
$ \vec X_1 = \begin{bmatrix}x_{11}\\\ x_{12}\\\ \cdots\\\ x_{1n} \end{bmatrix} $; 
$ \vec W = \begin{bmatrix}w_{1}\\\ w_{2}\\\ \cdots\\\ w_{n} \end{bmatrix} $; 
$ \vec W^TX_{i} = \begin{bmatrix}w_{1} & w_{2} & \cdots & w_{n} \end{bmatrix}  \begin{bmatrix}x_{i1} \\\ x_{i2} \\\ \cdots \\\ x_{im} \end{bmatrix} = 常数 $
#### 3. 使用机器学习学习参数的步骤
- 限定一个模型：方程or复杂模型, i.e., 超平面$\vec W^TX + b = 0$
- 模型里留出一些待定参数, i.e., $\vec W, b$
- 用训练样本和算法确定待定参数的具体取值, i.e., 确定$\vec W, b$的值，则完成机器学习过程。
#### 4. 训练集线性可分的定义
一条直线分开样本集的数学表示
$\exists (\vec W, b)$使训练样本$(\vec X_i, y_i), i = 1, \ldots, m$ 有
- 若$y_i = 1, \vec W^TX + b \ge 0$
- 若$y_i = -1, \vec W^TX +b \lt 0$
- 在$y_i = \qm 1$时，统一表达为$y_i[\vec W^TX + b] \ge 0$
或者以下定义也可，求解的$\vec W, b$有一个负号差距。
- 若$y_i = 1, \vec W^TX + b \lt 0$
- 若$y_i = -1, \vec W^TX +b \ge 0$




















# 公式换行问题，待研究，码
$\begin{bmatrix}x_1 \\\x_2 \\\ \end{bmatrix}$

  $\begin{matrix} a & b \\\ c & d \end{matrix}$

$$
 \left[
 \begin{matrix}
   1 & 2 & 3 \\\
   4 & 5 & 6 \\\
   7 & 8 & 9
  \end{matrix}
  \right] \tag{3}
$$


$$
\begin{bmatrix}x_1 \\\x_2 \\\ \end{bmatrix}
$$
  $\begin{matrix} a & b \\\ c & d \end{matrix}$

$$
 \left[
 \begin{matrix}
   1 & 2 & 3 \\\
   4 & 5 & 6 \\\
   7 & 8 & 9
  \end{matrix}
  \right] \tag{3}
$$


$$
\begin{bmatrix}x_1 \\\x_2 \\\ \end{bmatrix}
$$
