# 高等数学

二元一次方程求根:

$$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$

三角函数:

$$\sin \alpha - \sin \beta = 2 \sin \frac{\alpha - \beta}{2} \cos \frac{\alpha + \beta}{2}$$

极限:

$$x \to 0 \begin{cases}
x \sim \sin x \sim \arcsin x \sim \arctan x \\
(1 + x)^{\frac{1}{x}} \sim e \\
\log_a (1 + x) \sim \frac{x}{\ln a} \\
a^x - 1 \sim x\ln a \\
x - \sin x \sim \frac{x^3}{6} \\
\tan x - x \sim \frac{x^3}{3} \\
\tan x - \sin x \sim \frac{x^3}{2} \\
\end{cases}$$

导数与微分:

| 函数                           | 导数                                                 |
|------------------------------|----------------------------------------------------|
| $ f(x) = x^n $               | $ f'(x) = nx^{n-1} $                               |
| $ f(x) = a^x $               | $ f'(x) = a^x \ln(a) $                             |
| $ f(x) = \log_a(x) $         | $ f'(x) = \frac{1}{x \ln(a)} $                     |
| $ f(x) = \sin(x) $           | $ f'(x) = \cos(x) $                                |
| $ f(x) = \cos(x) $           | $ f'(x) = -\sin(x) $                               |
| $ f(x) = \tan(x) $           | $ f'(x) = \sec^2(x) $                              |
| $ f(x) = \cot(x) $           | $ f'(x) = -\csc^2(x) $                             |
| $ f(x) = \sec(x) $           | $ f'(x) = \sec(x) \tan(x) $                        |
| $ f(x) = \csc(x) $           | $ f'(x) = -\csc(x) \cot(x) $                       |
| $ f(x) = \sin^n(x) $         | $ f'(x) = n \sin^{n-1}(x) \cos(x) $                |
| $ f(x) = \cos^n(x) $         | $ f'(x) = -n \cos^{n-1}(x) \sin(x) $               |
| $ f(x) = x^n \ln(x) $        | $ f'(x) = nx^{n-1} \ln(x) + \frac{x^{n-1}}{x} $    |
| $ f(x) = \frac{u(x)}{v(x)} $ | $ f'(x) = \frac{u'(x)v(x) - u(x)v'(x)}{[v(x)]^2} $ |
| $ f(x) = u(x) \cdot v(x) $   | $ f'(x) = u'(x)v(x) + u(x)v'(x) $                  |

不定积分:

$$\int \frac{1}{x} \ dx = \ln |x| + c$$

$$\int u\ dv = uv - \int v\ du$$

向量代数:

$$a \cdot b = |a| |b| \cos \theta$$

$$a \times b = -b \times a = |a| |b| \sin \theta$$

# 复变函数

欧拉公式:

$$e^{i\theta} = \cos \theta + i \sin \theta$$

# 概率论

$$P(A) \ P(B \mid A) = P(AB)$$

贝叶斯公式:

$$P(w_i \mid A) = \frac{P(w_i A)}{P(A)} = \frac{P(w_i)\ P(A \mid w_i)}{\sum_{i=1}^n P(w_i)\ P(A \mid w_i)}$$

数学期望:

$$\mathbb{D}[X] = \mathbb{E}[X^2] - \mathbb{E}^2[X]$$
$$\mathbb{D}[wX] = w^2 \mathbb{D}[X]$$
$$\mathbb{D}[X \pm Y] = \mathbb{D}[X] + \mathbb{D}[Y] \pm 2 \text{cov}(X, Y)$$

二项分布:

$$X \sim B(n, p)$$
$$P(x) = B(x \mid n, p) = C_n^x p^x (1 - p)^{n - x}$$
$$\mathbb{E}[X] = np$$
$$\mathbb{D}[X] = np(1 - p)$$

高斯分布:

$$X \sim \mathcal{N}(\mu, \sigma^2)$$
$$P(x) = \mathcal{N}(x \mid \mu, \sigma^2) = \frac{1}{\sqrt{2\pi}\sigma} \exp \left( -\frac{(x - \mu)^2}{2\sigma^2} \right)$$
$$\int_{-\infty}^{\infty} \mathcal{N}(x \mid \mu, \sigma^2) \ dx = 1$$

极大似然估计 (Maximum Likelihood Estimation):

$$\mathcal{L}(\theta \mid x) = p(x \mid \theta) = \prod_{i=1}^n p(x_i \mid \theta)$$

最大后验估计 (Maximum A Posteriori Estimation):

$$p(\theta \mid x) = \frac{p(x \mid \theta)\ p(\theta) }{p(x)} \propto p(x \mid \theta)\ p(\theta)$$

# 非线性优化

一阶导数: 梯度, 雅可比矩阵 (Jacobian)

二阶导数: 海塞矩阵 (Hessian) 

牛顿法 (泰勒展开):

$$ F(x) = F(x_0) + g^T \Delta x + o(\Delta x) $$
$$ \nabla f(x) = g + H(\Delta x) = 0 $$
$$ \Delta x = -H^{-1}g $$

高斯牛顿法 (最小二乘问题):

$$ F(x) = \|f(x)\|^2 $$
$$ \nabla F(x + \Delta x) = g \cdot f(x) + gg^T \Delta x = 0 $$
$$ \Delta x = -(gg^T)^{-1}g \cdot f(x) $$

列文伯格-马尔夸特 (高斯牛顿法 plus):
- 给定信赖区域半径, 根据近似程度 (后验下降 / 先验下降) 对信赖区域半径进行缩放, 作为 "学习率"

# 卡尔曼滤波

雅可比矩阵 (状态转移矩阵, 观测系统参数):

$$F = \frac{\partial f(x_{t-1}, u_t)}{\partial x_{t-1}}$$
$$H = \frac{\partial h}{\partial x_t}$$

先验估计及协方差:

$$\hat{x}_t^- = f(x_{t-1}, u_t) = F x_{t-1} + u_t$$
$$P_t^- = F P_{t-1} F^T + R$$

卡尔曼增益: 

$$K_t = \frac{P_t^- H^T}{H P_t^- H^T + Q}$$

后验估计及协方差:

$$x_t = \hat{x}_t^- + K_t(z_t - H \hat{x}_t^-)$$
$$P_t = (I - K_t H) P_t^-$$
