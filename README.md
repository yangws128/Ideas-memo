# Ideas-memo
아이디어 메모장..

## 1. 실수와 카테고리 변수를 interop을 위한 distance-preserving(?) mapping

$x_k$이 실수값이면 $\displaystyle x_k \cdot \frac{1}{\sqrt\pi}\cos(kx)$
명목형 변수면 $\frac{\rho_k}{\sqrt {2\pi}}\sin(p_i \cdot jx)$ (i-th nominal, j-th class, $p_i$는 i번째 홀수 소수, $\rho_k$는 비례상수)

거리함수
$\displaystyle d^2 (x,y) = \int_{-\pi}^{\pi} \Vert \vec{x} - \vec{y} \Vert^2 dx$
= $\sum_{k} (x_k - y_k)^2 + \sum_{i} \rho_i^2\delta_{x_i y_i}$ (k index for numerics, i index for nominals)
 
## 2. 실수와 카테고리 변수를 포함하는 벡터의 압축

르장드르 다항식 $P_k (x), k \in \mathbb{N}$에 대하여 임의의 벡터의 실수부분 $\vec{x} _ {real} = (x_1 , x_2 , x_3 , \cdots , x_n )^t$이면, $\hat{x} _ {k}(t) = {x_k} \cdot P_k (t)$ 라고 하고,
명목형 부분 $\vec{x} _ {nominal} = (y_{1} , y_{2} , \cdots, y_{m} )^t$ 에 대해서, $\hat{y}_k (s) = \sin ( \pi p_k  y_k  s)$ 라고 하자.

$P(t) = \sum_{i=1}^{n} \hat{x} _k (t)$에 대해서 $j \in \mathbb{N} , (j < k)$ 개의 $\alpha_j \in (1 - \epsilon, 1 + \frac{\epsilon}{n}), N_j \in 1...\max(\deg(P))$을 뽑아 $P(t)$ 의 $N_j$차 항과 $P(t)$의 나머지 부분을 $P _{N_j}(t)$, $P_0 (t)$ 라고 하여 $|z| \le \alpha^j, z \in \mathbb{C}$를 기준으로 $|P _{N_j} (z) | > | P_0 (z) |$ 인 $j$들에 대해서, $\sum _{j} P _{N_j} (t)$ 를  $P(t)$의 압축 $\hat{P} (t)$이라고 한다. (Roucher 정리에서 착안)

다음, threshold 값으로 선정된 $\beta \in (0, +\infty)$에 대해서, $\displaystyle \vert \int _{-1} ^{1} P(t) \hat{y} _k (t) dt \vert > \beta$ 인 $y_k$의 인덱스의 집합을 $\Gamma$라 하자, $\sum _{\gamma \in \Gamma} y _\gamma (t) = Q (t)$ 라 하면, $Q(t)$ 는 명목형 부분의 압축이다.

마지막으로 두 압축값을 더하여 원본 벡터의 함수로의 사상 및 압축의 결과 $\hat{P}(t)+Q(t)$를 얻을 수 있다.
