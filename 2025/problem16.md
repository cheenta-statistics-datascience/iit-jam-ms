# Solution: IIT JAM MS 2025 Problem 16 (MCQ2)
## Answer: (C)

Part (I) - True
* Let's assume that $A$ is singular. This means $A$ has an eigenvalue 0. Now comes the main part.
* Consider the [minimal polynomial](https://en.wikipedia.org/wiki/Minimal_polynomial_(linear_algebra)) $\mu_A$ of $A$.
* $mu_A(0) = 0$, since 0 is an eigenvalue of $A$. This implies $x$ is a factor of the polynomial $\mu_A(x)$.
* Since, $f(A) = 0$, it implies that $\mu_A$ divides $f(A)$ (why? - think in terms of remainder theorem)
* Hence, $\mu_A(x)$ is a factor of $f(x)$, which in turn implies $x$ is a factor of $f(x)$.
* Thus, by contrapositive argument, (I) is true.

Part (II) - True
* $f(0) = 0 \implies f(x) = xg(x)$ for some polynomial $g(x)$. Therefore, $f(A) = Ag(A)$.
* Given that $f(A) = 0 \implies Ag(A) = 0 \implies det(Ag(A)) = 0 \implies det(A) = 0$, since determinant function is multiplicative.
* Hence (II) is true, because zero determinant implies singular matrix.
