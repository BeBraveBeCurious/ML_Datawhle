# Mark 优秀blog
[通俗理解CRF](https://www.zhihu.com/question/35866596)
[B站白板CRF来龙去脉笔记](https://anxiang1836.github.io/2019/11/05/NLP_From_HMM_to_CRF/)


# Classical problem in ML

## Learn a classifier 
- 学习一个分类器，区分 >= 2 类 that can distinguish between two or more classes
- i.e., 准确预测新对象的类别，在给定训练样本已经分类的情况下 that can accurately predict a class for a new object given training examples of objects already classified

## Example of classifiers in NLP
- classifying an email as spam or not spam
- classifying a movie into genres
- classifying a news article into topics

# 一类有结构的预测问题
## another type of prediction problems which involve structure
### part-of-speech tagging
- each $x_i$ describes a word and each y_i the associated part-of-speech of the word x_i (e.g.: noun, verb, adjective, etc.).

$$\(ax^2 + bx + c = 0\)$$
