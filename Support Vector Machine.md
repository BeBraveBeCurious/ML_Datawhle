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

### 样本定义
m 个训练样本及标签: $(\vec X_1, y_1), (\vec X_2, y_2), (\vec X_3, y_3), \cdots, (\vec X_m, y_m)$
- $\vec X_i$ 在$R^2$空间中表现为$\begin{bmatrix}x_1 \\x_2 \\ \end{bmatrix}$

$\begin{bmatrix}a & b\\c & d\end{bmatrix}$



$$
\begin{bmatrix}
x_1 \\
x_2 \\
\end{bmatrix}
$$
