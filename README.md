# Ideas-memo
아이디어 메모장..

## 1. 실수와 카테고리 변수를 interop을 위한 distance-preserving(?) mapping

$x_k$이 실수값이면 $\displaystyle x_k \cdot \frac{\rho_k}{\sqrt\pi}\cos(kx)$
명목형 변수면 $\frac{1}{\sqrt {2\pi}}\sin(p_i \cdot jx)$ (i-th nominal, j-th class, $p_i$는 i번째 홀수 소수, $\rho_k$는 비례상수)

거리함수
$\displaystyle d^2 (x,y) = \int_{-\pi}^{\pi} \Vert \vec{x} - \vec{y} \Vert^2 dx$
= $\sum_{k} (x_k - y_k)$ (k is an index for a numeric) $+ \sum_{i} \rho_i^2\delta_{x_i y_i}$ (i is an index for a nominal)
