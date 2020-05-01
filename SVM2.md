### 优化理论：各种各样的资源要素的权衡取舍
1. 原问题 & 对偶问题

- prime problem: general的定义，可解 $\max$ 目标问题和约束 $ \ge 0 $
$$ \min \quad f(\vec W) \\\ s.t. g_i(\vec W) \le 0, i = 1, \dots, K  \\\ \quad h_i(\vec W) = 0, i = 1, \dots, M $$


- dual problem: 
$ \max \Theta(\alpha, \beta) = \inf \limits_{all\ \vec W}L(\vec W, \alpha, \beta), inf$ = 下确界，min
s.t. $ \alpha_i \ge 0\ or\ \vec \alpha \succeq 0$
  - where 针对一组 $(\alpha, \beta)$ 的值，需要遍历所有的 $\vec W$ 来求解目标 $\Theta(\alpha, \beta)$ 的max值

$$ L(\vec W, \alpha, \beta) = f(\vec W) + \sum_{i=1}^K \alpha_i g_i(\vec W) + \sum_{i=1}^M \beta_i h_i(\vec W) \xrightarrow{vector form} L(\vec W, \alpha, \beta) = f(\vec W) + \vec \alpha^T g(\vec W) + \vec \beta^T h(\vec W) $$
  - $dimension(\vec \alpha^T)$ = 不等式约束的个数， $dimension(\vec \beta^T)$ = 等式约束的个数。
  - $g(\vec W) = \begin{bmatrix} g_1(\vec W)\\\ g_2(\vec W)\\\ \dots\\\ g_K(\vec W)\end{bmatrix}, h(\vec W) = \begin{bmatrix} h_1(\vec W)\\\ h_2(\vec W)\\\ \dots\\\ h_M(\vec W)\end{bmatrix}$

2. relationship between prime problem and dual problem
- 定理： 若$ \vec W^* $是prime problem $\min \quad f(\vec W)$ 的解，而$ (\vec \alpha^* , \vec \beta^* ) $是dual problem $ \max \Theta(\alpha, \beta) $的解，则$ f(\vec W^* ) \ge \Theta(\vec \alpha^* , \vec \beta^* ) $
- 证明： $ \Theta(\vec \alpha^* , \vec \beta^* ) = \inf \limits_{all\ \vec W}L(\vec W, \alpha^*, \beta^*) \le \inf \limits_{all\ \vec W}L(\vec W^*, \alpha^*, \beta^*)
