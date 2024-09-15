# Uniqueness and Completeness of Classical Spin Hamiltonians

*Ivo A. Maceira, Mario Geiger*

We wish to prove that there is a one-to-one correspondence between the couplings and the spectra of classical spin Hamiltonians.

We take a set of $N$ classical spin variables
```math
s_n = \pm 1,
```
which we will conveniently write as
```math
s_n \equiv (-1)^{\beta_n},\quad \beta_n = 0,1.
```

For brevity of notation, we call the ordered set of $\beta$’s as
```math
\beta \equiv (\beta_1,\beta_2,\dots,\beta_N).
```

Since $s_n^2 = 1$, the most general Hamiltonian written in terms of the $N$ spins has $2^N$ terms and can be written succinctly as
```math
\mathcal{H}_J(\beta) = \sum_{\{\alpha_n\}} J(\alpha) (-1)^{\sum_{n=1}^{N} \alpha_n \beta_n},
```
with $\alpha_n = 0,1$ and the sum taken over all $\{\alpha_n\}$ configurations. We define
```math
\alpha \equiv (\alpha_1,\alpha_2,\dots,\alpha_n),
```
and $J$ as the ordered set of $J(\alpha)$ couplings, totaling $2^N$ in number. Note that each “configuration” of $\alpha$ corresponds to a unique term of the Hamiltonian while each configuration of $\beta$ gives a unique spin configuration. However, the two sets of configurations are identical, and each Hamiltonian term involves the dot product between two configurations of 0’s and 1’s, one from each set.

We wish to prove that two Hamiltonians with different couplings have different spectra, or equivalently, that the correspondence between the set of energies of each configuration and the set of couplings is one-to-one.

Let us consider that two Hamiltonians $H_J$ and $H_K$ have equal spectra but possibly different sets of couplings $J$ and $K$,
```math
\forall \{\beta_n\}: \quad \mathcal{H}_J(\beta) = \mathcal{H}_K(\beta)
```
which is equivalent to
```math
\forall \{\beta_n\}: \quad \sum_{\{\alpha_n\}} [J(\alpha) - K(\alpha)] (-1)^{\sum_{n=1}^{N} \alpha_n \beta_n} = 0.
```

The system of equations above can be written in matrix form as

```math
\{\beta_n\}\,
\underset{\{\alpha_n\}}{
\begin{pmatrix}
  &  & \\
  & (-1)^{\sum_{n=1}^{N} \alpha_n \beta_n} & \\
  &  &
\end{pmatrix}
}
\,
\begin{pmatrix}
J - K
\end{pmatrix}
=
\begin{pmatrix}
0\\[1mm]
0\\[1mm]
\vdots
\end{pmatrix}.
```

Each column of the matrix corresponds to a Hamiltonian term labeled by $\{\alpha_n\}$ while each row corresponds to a spin configuration $\{\beta_n\}$. Our claim is that the only solution to this system of equations is $J = K$. To prove this, it suffices to show that the determinant of the matrix is nonzero. We name this matrix as $M$, a $2^N \times 2^N$ matrix where each element depends on the dot product of two $0,1$ configurations:

```math
M_N(\{\alpha_n\},\{\beta_n\}) \equiv (-1)^{\sum_{n=1}^{N} \alpha_n \beta_n} = \pm 1.
```

For a given configuration ordering, the smallest $M$ matrix (for $N=1$) is

```math
M_1 =
\begin{pmatrix}
1 & 1 \\
1 & -1
\end{pmatrix},
```
with $\det(M_1) = -2$.

Bigger matrices can be constructed recursively, noting that
```math
M_N(\{\alpha_n\},\{\beta_n\}) = (-1)^{\sum_{n=1}^{N-1} \alpha_n \beta_n} (-1)^{\alpha_N \beta_N} = (-1)^{\alpha_N \beta_N} M_{N-1}(\{\alpha_n\}\setminus \alpha_N,\{\beta_n\}\setminus \beta_N).
```

This leads to the matrix recursion
```math
M_N(\{\alpha_n\},\{\beta_n\}) =
\begin{pmatrix}
M_{N-1} & M_{N-1} \\
M_{N-1} & -M_{N-1}
\end{pmatrix}.
```

The determinant can then be obtained recursively using Schur's determinant identity:
```math
\det(M_N) = (-2)^{2^{N-1}} \det(M_{N-1})^2,
```
which is nonzero. This proves that the only solution to the system is $J = K$, establishing the one-to-one correspondence.


