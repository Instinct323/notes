# SO3

$\text{SO}(3) = \{R \in \mathbb{R}^{3 \times 3}\ |\ RR^T = I, \det(R) = 1\}$

- Rotation Angle: $\theta$
- Rotation Axis: $\{n = [n_x, n_y, n_z]^T \in \mathbb{R}^3\ |\ \|n\| = 1\}$
- Lie Algebra: $\phi = \theta n \in \mathbb{R}^3$
- Quaternion: $q = [q_w, q_x, q_y, q_z]^T$

## Lie Algebra

$$n^{\land} = \begin{bmatrix}
0 & -n_z & n_y \\
n_z & 0 & -n_x \\
-n_y & n_x & 0 \\
\end{bmatrix}$$

$$nn^T = I + n^{\land2}$$

$$\begin{aligned}
\exp({\phi}^{\land}) &= I& + \sin \theta &n^{\land}& + (1 - \cos \theta)&n^{\land2} \\
J_l(\phi^{\land}) &= I& + \frac{1 - \cos \theta}{\theta} &n^{\land}& + (1 - \frac{\sin \theta}{\theta})&n^{\land2} \\
J_r(\phi^{\land}) &= I& - \frac{1 - \cos \theta}{\theta} &n^{\land}& + (1 - \frac{\sin \theta}{\theta})&n^{\land2} \\
\end{aligned}$$

$$\begin{aligned}
\exp((\phi + \Delta \phi)^{\land}) & \approx \exp((J_l(\phi^{\land})\Delta \phi)^{\land}) \exp(\phi^{\land}) \\
& \approx \exp(\phi^{\land}) \exp((J_r(\phi^{\land})\Delta \phi)^{\land})
\end{aligned}$$

## Quaternion

Rotate:

$$p' = qpq^{-1}$$

Conjugate:

$$\begin{aligned}
q^* &\rightarrow R^T \\
q^* &= \| q \|^2 q^{-1} \\
\end{aligned}$$

Multiplication:

$$QQ^T = I$$
$$qr = Qr$$
$$rq = \overline{Q} r$$

$$Q = L(q) = \begin{bmatrix}
q_w & -q_x & -q_y & -q_z \\
q_x & q_w & -q_z & q_y \\
q_y & q_z & q_w & -q_x \\
q_z & -q_y & q_x & q_w \\
\end{bmatrix}$$

$$\overline{Q} = R(q)= \begin{bmatrix}
q_w & -q_x & -q_y & -q_z \\
q_x & q_w & q_z & -q_y \\
q_y & -q_z & q_w & q_x \\
q_z & q_y & -q_x & q_w \\
\end{bmatrix}$$

## Transformation

| from \ to | $R$                                                                                                | $\phi$                                                                                                                                                                                                                                | $q$                                                                                                                                                                                                                             |
|-----------|----------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| $R$       | $-$                                                                                                | $\begin{aligned} \theta &= \arccos \frac{\sqrt{\text{tr}(R) - 1}}{2} \\ n &= \frac{ \begin{bmatrix} R_{32} - R_{23} \\ R_{13} - R_{31} \\ R_{21} - R_{12} \\ \end{bmatrix} }{2\sin \frac{\theta}{2}(\text{tr}(R) + 1)} \end{aligned}$ | $\begin{aligned} q_w &= \frac{\sqrt{\text{tr}(R) + 1}}{2} \\ \begin{bmatrix} q_x \\ q_y \\ q_z \\ \end{bmatrix} &= \begin{bmatrix} R_{32} - R_{23} \\ R_{13} - R_{31} \\ R_{21} - R_{12} \\ \end{bmatrix} / 4q_w \end{aligned}$ |
| $\phi$    | $R = \exp({\phi}^{\land}) = \cos \theta I + (1 - \cos \theta) nn^T + \sin \theta n^{\land} $       | $-$                                                                                                                                                                                                                                   | $\begin{aligned} q_w &= \cos \frac{\theta}{2} \\ [q_x, q_y, q_z]^T &= n \sin \frac{\theta}{2} \end{aligned}$                                                                                                                    |
| $q$       | $\begin{aligned} p &= [q_x, q_y, q_z]^T \\ R &= 2(pp^T + q_w(q_wI + p^{\land})) - I \end{aligned}$ | $\begin{aligned} \theta &= 2\arccos q_w \\ n &= \frac{[q_x, q_y, q_z]^T}{\sin \frac{\theta}{2}} \end{aligned}$                                                                                                                        | $-$                                                                                                                                                                                                                             |

# SE3

$\text{SE}(3) = \{T = \begin{bmatrix} R & t \\ 0 & 1 \end{bmatrix} \in \mathbb{R}^{4 \times 4}\ |\ R \in \text{SO}(3), t \in \mathbb{R}^3\}$

$$T^{-1} = \begin{bmatrix}
R^T & -R^T t \\
0^T & 1 \\
\end{bmatrix}$$

- Lie Algebra: $\xi = [\rho, \phi]^T \in \mathbb{R}^6$
- Epipolar Constraint: $x_2^T E x_1 = p_2^T F p_1 = 0, \quad p = Kx$
- Essential Matrix: $E = t^{\land} R$
- Fundamental Matrix: $F = K^{-T} E K^{-1}$

## Lie Algebra

$$\xi^{\land} = \begin{bmatrix}
\phi^{\land} & \rho \\
0^T & 0 \\
\end{bmatrix}$$

$$T = \exp(\xi^{\land}) = \begin{bmatrix}
\exp(\phi^{\land}) & J\rho \\
0^T & 1 \\
\end{bmatrix}$$

$$J = \frac{\sin \theta}{\theta} I + (1 - \frac{\sin \theta}{\theta}) nn^T + \frac{1 - \cos \theta}{\theta}n^{\land}$$