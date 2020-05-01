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
- 证明： $ \Theta(\vec \alpha^* , \vec \beta^* ) = \inf \limits_{all\ \vec W}L(\vec W, \alpha^* , \beta^* ) \le L(\vec W^* , \alpha^* , \beta^* ) $, $ \inf \limits_{all\ \vec W} $ 遍历所有$ \vec W $求最小值，一定小于 $ \forall \vec W $,故$ \Theta(\vec \alpha^* , \vec \beta^* ) \le \vec W^* $求得的函数值 
  -  $ \Theta(\vec \alpha^* , \vec \beta^* ) \le L(\vec W^* , \alpha^* , \beta^* ) =  f(\vec W^* ) + \sum_{i=1}^K \alpha_i^* g_i(\vec W^* ) + \sum_{i=1}^M \beta_i^* h_i(\vec W^* )$
  - $ \vec W^* $是prime problem $\min \quad f(\vec W)$ 的解$ \rightarrow g_i(\vec W^* ) \le 0, i = 1, \dots, K  \\\ \quad h_i(\vec W^* ) = 0, i = 1, \dots, M $
  - $ (\vec \alpha^* , \vec \beta^* ) $是dual problem $ \max \Theta(\alpha, \beta) $的解$ \rightarrow \alpha_i^* \ge 0 $
  - $ \sum_{i=1}^K \alpha_i^* g_i(\vec W^* ) \le 0, \sum_{i=1}^M \beta_i^* h_i(\vec W^* ) = 0 $
  - $ \Theta(\vec \alpha^* , \vec \beta^* ) \le f(\vec W^* ) + $ 负数 $\rightarrow \Theta(\vec \alpha^* , \vec \beta^* ) \le f(\vec W^* ) $
3. Duality gap 对偶问题的间距$ G= f(\vec W^* ) - \Theta(\vec alpha^* , \vec beta^* ) \ge 0
 - 强对偶定理， 某些特定问题可以证明$ G = 0 $
  - 若$ f(\vec W) $是凸函数，且$ g(\vec w) = A\vec W + b, h(\vec W) = C\vec W + d $, 即$ g(\vec W), h(\vec W) $都是线性的
  - 则此优化问题的原问题与对偶问题间距为0, 即若$ \vec W^* $是prime problem $\min \quad f(\vec W)$ 的解，而$ (\vec \alpha^* , \vec \beta^* ) $是dual problem $ \max \Theta(\alpha, \beta) $的解，则$ f(\vec W^* ) = \Theta(\vec \alpha^* , \vec \beta^* ) $ 
  - Ref Convex optimization P1-p150
- KKT条件： $\forall i = 1, \dots, m, \alpha^* _i = 0\ or\ g^* _i(\vec W^*) = 0 $
  
### non linear SVM's dual problem
1. 强对偶定理的使用条件
- 目标条件为凸函数(bowl)$\  \min\quad \frac{1}{2}||\vec W||^2 + C\sum_{i=1}^m \xi_i \\\ 
s.t. y_i[\vec W^T\Phi(\vec X_i) + b] \ge 1 - \xi_i \\\\
\quad \ \xi_i \ge 0$
- 约束条件线性改写为$ \le 0$
  - $\xi_i \le 0 $ 加一个负数 
  - objective: $\min\quad \frac{1}{2}||\vec W||^2 - C\sum_{i=1}^m \xi_i $
2. non linear SVM's new prime problem
$\  \min\quad \frac{1}{2}||\vec W||^2 - C\sum_{i=1}^m \xi_i \\\ 
s.t.  1 + \xi_i - y_i[\vec W^T\Phi(\vec X_i) + b] \le 0\\\\
\quad \ \xi_i \le 0$

3. non linear SVM's dual problem
$ \max \Theta(\vec \mu, \vec \nu) \\\ s.t. \mu_i \ge 0, \nu_i \ge 0 $
$ \Theta(\vec \mu, \vec \nu) = \inf \limits_{all\ \vec W}L(\vec W, \vec \mu, \vec \nu) = \inf \limits_{all\ \vec W}(\frac{1}{2}||\vec W||^2 + \sum_{i=1}^m\mu_i (1 + \xi_i - y_i[\vec W^T\Phi(\vec X_i) + b]) + \sum_{i=1}^m\nu_i \xi_i) $
- $ \inf $求下确界，最小值可通过偏导数=0得到
  - $\partial\frac{L(\vec W, \vec \mu, \vec \nu)}{\vec W} = \partial\frac{frac{1}{2}\vec W^T\vec W}{\vec W} + \partial\sum_{i=1}^m \mu_i y_i \vec W^T\Phi(\vec X_i) = \vec W + \sum_{i=1}^m \ mu_i y_i\Phi(\vec X_i)
  - $\partial\frac{L(\vec W, \vec \mu, \vec \nu)}{\vec \mu} =  1 + \xi_i - y_i[\vec W^T\Phi(\vec X_i) + b] $
  - $\partial\frac{L(\vec W, \vec \mu, \vec \nu)}{\vec \nu} = \sum_{i=1}^m\xi_i $
