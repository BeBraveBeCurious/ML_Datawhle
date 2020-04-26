# 概念回顾

# 生成模型、判别模型分类
## 生成模型
- 对数据建模（例如根据某个变量的概率密度函数进行数据采样）
- 建立变量间的条件概率分布 based Bayesian theorem
- **常见算法** 高斯混合模型和其他混合模型、隐马尔可夫模型、随机上下文无关文法、朴素贝叶斯分类器、AODE分类器、潜在狄利克雷分配模型、受限玻尔兹曼机
- 上述条件算法基本只知道名字，日后填坑
- example： 要确定一个瓜是好瓜还是坏瓜，用判别模型的方法是从历史数据中学习到模型，然后通过提取这个瓜的特征来预测出这只瓜是好瓜的概率，是坏瓜的概率。

## 判别模型
- 在机器学习领域判别模型是一种对未知数据 y 与已知数据 x 之间关系进行建模的方法。
- 基于概率理论
- 已知输入变量 x ，判别模型通过构建条件概率分布 P(y|x) 预测 y 。
- **常见算法** 逻辑回归、线性回归、支持向量机、提升方法、条件随机场、人工神经网络、随机森林、感知器
- example： 利用生成模型是根据好瓜的特征首先学习出一个好瓜的模型，然后根据坏瓜的特征学习得到一个坏瓜的模型，然后从需要预测的瓜中提取特征，
-           放到生成好的好瓜的模型中看概率是多少，在放到生产的坏瓜模型中看概率是多少，哪个概率大就预测其为哪个。

## 联系与区别
- 生成模型是所有变量的全概率模型，而判别模型是在给定观测变量值前提下目标变量条件概率模型。
- 因此生成模型能够用于模拟（即生成）模型中任意变量的分布情况，而判别模型只能根据观测变量得到目标变量的采样。
- 判别模型不对观测变量的分布建模，因此它不能够表达观测变量与目标变量之间更复杂的关系。
- 因此，生成模型更适用于无监督的任务，如分类和聚类。

# prior probability & posterior probability
## 先验概率： 因
- 某一不确定量 p 的先验概率分布是在考虑"观测数据"前，能表达 p 不确定性的概率分布。
- 3Blue1Brown的解释：librarian和farmer的天生1：20的比例
## 后验概率： 知果求因
- 一个随机事件或者一个不确定事件的后验概率是在考虑和给出相关证据或数据后所得到的条件概率。
- 3Blue1Brown的解释: 给定一段任务描述后，推断他是librarian还是farmer的比例

## 最大似然法估计参数的4步：
- 1.写出似然函数；
- 2.对似然函数取对数，并整理；
- 3.求导数，令偏导数为0，得到似然方程组；
- 4.解似然方程组，得到所有参数即为所求。
- 贝叶斯分类器的训练过程就是参数估计。
## 学习资料给的非常全面，但感觉自己运用的更多的是阅读能力，不是学习能力，要改善！
