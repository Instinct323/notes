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

三点求导公式:

$$\begin{aligned}
f'(x_0) &\approx \frac{-3f(x_0) + 4f(x_1) - f(x_2)}{2h} \\
&\approx \frac{f(x_1) - f(x_{-1})}{2h} \\
&\approx \frac{f(x_{-2}) - 4f(x_{-1}) + 3f(x_0)}{2h}
\end{aligned}$$

导数与微分:

| 函数                             | 导数                                                                                                          |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| $f(x) = x^n$                   | $\frac{df}{dx} = nx^{n-1}$                                                                                  |
| $f(x) = a^x$                   | $\frac{df}{dx} = a^x \ln(a)$                                                                                |
| $f(x) = \log_a(x)$             | $\frac{df}{dx} = \frac{1}{x \ln(a)}$                                                                        |
| $f(x) = \sin(x)$               | $\frac{df}{dx} = \cos(x)$                                                                                   |
| $f(x) = \cos(x)$               | $\frac{df}{dx} = -\sin(x)$                                                                                  |
| $f(x) = \tan(x)$               | $\frac{df}{dx} = \sec^2(x)$                                                                                 |
| $f(x) = \cot(x)$               | $\frac{df}{dx} = -\csc^2(x)$                                                                                |
| $f(x) = \sec(x)$               | $\frac{df}{dx} = \sec(x) \tan(x)$                                                                           |
| $f(x) = \csc(x)$               | $\frac{df}{dx} = -\csc(x) \cot(x)$                                                                          |
| $f(x) = \sin^n(x)$             | $\frac{df}{dx} = n \sin^{n-1}(x) \cos(x)$                                                                   |
| $f(x) = \cos^n(x)$             | $\frac{df}{dx} = -n \cos^{n-1}(x) \sin(x)$                                                                  |
| $f(x) = x^n \ln(x)$            | $\frac{df}{dx} = nx^{n-1} \ln(x) + \frac{x^{n-1}}{x}$                                                       |
| $f(x) = \frac{u(x)}{v(x)}$     | $\frac{df}{dx} = \frac{u'(x)v(x) - u(x)v'(x)}{[v(x)]^2}$                                                    |
| $f(x) = u(x) \cdot v(x)$       | $\frac{df}{dx} = u'(x)v(x) + u(x)v'(x)$                                                                     |
| $f(x, y) = \text{atan2}(y, x)$ | $\frac{\partial f}{\partial x} = \frac{-y}{x^2 + y^2}, \frac{\partial f}{\partial y} = \frac{x}{x^2 + y^2}$ | 

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

Math Expectation:

$$\mathbb{D}[X] = \mathbb{E}[X^2] - \mathbb{E}^2[X]$$
$$\mathbb{D}[wX] = w^2 \mathbb{D}[X]$$
$$\text{cov}(X, Y) = \mathbb{E}[XY] - \mathbb{E}[X]\mathbb{E}[Y]$$
$$\mathbb{D}[X \pm Y] = \mathbb{D}[X] + \mathbb{D}[Y] \pm 2 \text{cov}(X, Y)$$

Bayes Law:

$$P(w_i \mid A) = \frac{P(w_i A)}{P(A)} = \frac{P(w_i)\ P(A \mid w_i)}{\sum_{i=1}^n P(w_i)\ P(A \mid w_i)}$$

Binomial Distribution:

$$X \sim B(n, p)$$
$$P(x) = B(x \mid n, p) = C_n^x p^x (1 - p)^{n - x}$$
$$\mathbb{E}[X] = np$$
$$\mathbb{D}[X] = np(1 - p)$$

Gaussian Distribution:

$$X \sim \mathcal{N}(\mu, \sigma^2)$$
$$P(x) = \mathcal{N}(x \mid \mu, \sigma^2) = \frac{1}{\sqrt{2\pi}\sigma} \exp \left( -\frac{(x - \mu)^2}{2\sigma^2} \right)$$
$$\int_{-\infty}^{\infty} \mathcal{N}(x \mid \mu, \sigma^2) \ dx = 1$$

Maximum Likelihood Estimation:

$$\mathcal{L}(\theta \mid x) = p(x \mid \theta) = \prod_{i=1}^n p(x_i \mid \theta)$$

Maximum A Posteriori Estimation (Prior $p(\theta)$):

$$p(\theta \mid x) = \frac{p(x \mid \theta)\ p(\theta) }{p(x)} \propto \mathcal{L}(\theta \mid x)\ p(\theta)$$

# 线性代数

Trace:

$$\text{tr}(A) = \text{tr}(A^T) = \sum_{i=1}^n \lambda_i$$
$$\text{tr}(aA + bB) = a \cdot \text{tr}(A) + b \cdot \text{tr}(B)$$
$$\text{tr}(A_1 A_2 \cdots A_k) = \text{tr}(A_2 \cdots A_k A_1)$$
$$\|A\|_2^2 = \text{tr}(A A^T)$$

Pseudo-inverse:

$$A \in \mathbb{R}^{m \times n}, \quad A^+ \in \mathbb{R}^{n \times m}$$
$$AA^+ A = A, \quad (AA^+)^T = AA^+$$

Non-linear Least Squares:

$$F(x) = \frac{1}{2}\|f(x)\|^2$$
$$J_f = \frac{df}{dx^T}, \quad J_F = \nabla F^T = \frac{dF}{dx^T} = f^T(x) J_f$$
$$H_F = \frac{d^2F}{dx^Tdx} = \frac{dJ_F}{dx}$$

- Gradient descent:$\Delta x = -\alpha J_F^T$
- Newton’s method:$\Delta x = -H_F^{-1} J_F$
- Gauss-Newton’s method:$\Delta x = -(J_f^T J_f)^{-1} J_f^T f(x)$
- Levenberg-Marquardt:$[J_f^T J_f + \lambda I] \Delta x = -J_f^T f(x)$

Linear Least Squares:

$$f(w) = \rho \cdot (Xw - y) = X_\rho w - y_\rho$$
$$J_f = X_\rho$$
$$\nabla F = J_f^T f(w) = X_\rho^T X_\rho w - X_\rho^T y_\rho$$

# 卡尔曼滤波

State Transition Equation:

$$x_k = f(x_{k-1}, u_k) + w_k, \quad w_k \sim \mathcal{N}(0, R_k)$$

Measurement Equation:

$$z_k = h(x_k) + v_k, \quad v_k \sim \mathcal{N}(0, Q_k)$$

Prior Estimate:

$$F = \frac{\partial f}{\partial x^T} \bigg| _{\hat{x}_{k-1}}$$
$$\overline{x}_k = f(\hat{x}_{k-1}, u_k)$$
$$\overline{P}_k = F \hat{P}_{k-1} F^T + R_k$$
$$p(x_k \mid x_0, u_{1:k}, z_{0:k-1}) \sim \mathcal{N}(\overline{x}_k, \overline{P}_k)$$

Posterior Estimate:

$$H = \frac{\partial h}{\partial x^T} \bigg| _{\hat{x}_k}$$
$$K_k = \overline{P}_k H^T (H \overline{P}_k H^T + Q_k)^{-1}$$
$$\hat{x}_k = \overline{x}_k + K_k (z_k - h(\overline{x}_k))$$
$$\hat{P}_k = (I - K_k H) \overline{P}_k$$
$$p(x_k \mid x_0, u_{1:k}, z_{0:k}) \sim \mathcal{N}(\hat{x}_k, \hat{P}_k)$$

# 模型评估

Information Entropy:

$$H(P, Q) = -\int p(x) \cdot \log q(x)\ dx$$

KL Divergence:

$$KL(P \| Q) = H(P, Q) - H(P)$$

- Forward Derivative:

$$\frac{\partial KL(P \| Q)}{\partial P} = 1 + \int \log \frac{p(x)}{q(x)}\ dx$$

- Backward Derivative:

$$\frac{\partial KL(P \| Q)}{\partial Q} = -\int \frac{p(x)}{q(x)}\ dx$$

Classification Metrics

| Metric          | Formula                                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
| Accuracy        | $\frac{TP + TN}{P + N}$                                                                                           |
| Specificity     | $\frac{TN}{N}$                                                                                                    |
| Precision       | $\frac{TP}{P'}$                                                                                                   |
| Recall          | $\frac{TP}{P}$                                                                                                    |
| $F_\beta$-Score | $\frac{(1 + \beta^2) \cdot \text{Precision} \cdot \text{Recall}}{\beta^2 \cdot \text{Precision} + \text{Recall}}$ |

Receiver Operating Characteristic (ROC)

- x-axis: False Positive Rate (FPR)

$$\text{FPR} = 1 - \text{Specificity}$$

- y-axis: True Positive Rate (TPR)

$$\text{TPR} = \text{Recall}$$

- Area Under the Curve (AUC): Measures the overall performance of the classifier.
