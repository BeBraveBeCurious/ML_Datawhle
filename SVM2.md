### 优化理论：各种各样的资源要素的权衡取舍
1. 原问题 & 对偶问题

prime problem:
$$ \min \quad f(\vec W) \\\ s.t. g_i(\vec W) \le 0, i = 1, \dots, K  \\\ \quad h_i(\vec W) = 0, i = 1, \dots, M $$
general普适的定义，可解 $\max$ 目标问题和约束 $ \ge 0 $

dual problem: 
$$ L(\vec W, \alpha, \beta) = $$
$$ f(\vec W) + $$
$$ \sum{i=1}^K \alpha_ig_i(\vec W) + $$
$$ \sum{i=1}^M \betah_i(\vec W) $$
