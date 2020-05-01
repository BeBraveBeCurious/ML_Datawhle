### 优化理论：各种各样的资源要素的权衡取舍
1. 原问题 & 对偶问题

$\qquad$ prime problem:
$$ \min \quad f(\vec W) \\\ s.t. g_i(\vec W) \le 0, i = 1, \dots, K  \\\ \quad h_i(\vec W) = 0, i = 1, \dots, M $$
general普适的定义，可解 $\max$ 目标问题和约束 $ \ge 0 $

$\qquad$ dual problem: 
$$ \Theta(\alpha, \beta) = \inf \limits_{all \vec W}L(\vec W, \alpha, \beta), inf = 下确界，min$$
$$ L(\vec W, \alpha, \beta) = f(\vec W) + \sum_{i=1}^K \alpha_i g_i(\vec W) + \sum_{i=1}^M \beta_i h_i(\vec W) $$
$$ L(\vec W, \alpha, \beta) = f(\vec W) + \vec \alpha^T g(\vec W) + \vec \beta^T h(\vec W) $$
$dimension(\vec \alpha^T)$ = 不等式约束的个数， $dimension(\vec \beta^T)$ = 等式约束的个数。
$g(\vec W) = \begin{bmatrix} g_1(\vec W)\\\ g_2(\vec W)\\\ dots\\\ g_K(\vec W)\end{bmatrix}, h(\vec W) = \begin{bmatrix} h_1(\vec W)\\\ h_2(\vec W)\\\ dots\\\ h_M(\vec W)\end{bmatrix}$
