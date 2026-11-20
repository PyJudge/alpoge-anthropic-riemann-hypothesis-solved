[Read Levent Alpöge’s remark (PDF)](https://alpo.ge/remark.pdf)

# alpoge-anthropic-riemann-hypothesis-solved

Congratulations, Levent Alpöge!

This repository is an unofficial mirror and may be removed upon request by a rights holder.

## Formalized statements

This repository mirrors the Lean sources released by Levent Alpöge for the **Riemann Hypothesis (RH)** and the **Generalized Riemann Hypothesis (GRH) for Dirichlet $L$-functions**. The five theorem declarations in [`src/Main.lean`](src/Main.lean) are listed below.

### 1. The Riemann hypothesis

Every nontrivial zero of the Riemann zeta function lies on the critical line. For every $s\in\mathbb C$,

```math
\left(\zeta(s)=0 \;\land\; s\notin\{-2,-4,-6,\ldots\} \;\land\; s\ne 1\right)
\;\Longrightarrow\; \mathrm{Re}(s)=\tfrac12.
```

**Lean formalization.** `riemannHypothesis` has type [Mathlib’s `RiemannHypothesis`](https://leanprover-community.github.io/mathlib4_docs/Mathlib/NumberTheory/LSeries/RiemannZeta.html#RiemannHypothesis).

### 2. The Riemann hypothesis restated in terms of zeta zeros

If $\zeta(s)=0$ for a complex number $s$, with $s$ neither a negative even integer nor the pole $s=1$, then $\mathrm{Re}(s)=\tfrac12$. This is the same mathematical statement as item 1.

**Lean formalization.** `riemannZeta_eq_zero_re` has type `RiemannZetaZerosOnLine`, defined in [`src/Statements.lean`](src/Statements.lean).

### 3. Dirichlet $L$-function nonvanishing right of the critical line

For any positive integer $N$ and any complex-valued Dirichlet character $\chi$ modulo $N$, the function $L(s,\chi)$ has no zeros to the right of the critical line. Write $\chi_0$ for the principal character modulo $N$. For every $s\in\mathbb C$,

```math
\left(\mathrm{Re}(s)>\tfrac12 \;\land\; (\chi\ne\chi_0 \;\lor\; s\ne 1)\right)
\;\Longrightarrow\; L(s,\chi)\ne 0.
```

The excluded pair $(\chi_0,1)$ is the pole of the principal character’s $L$-function. See [NIST DLMF §25.15](https://dlmf.nist.gov/25.15#i).

**Lean formalization.** `LFunction_ne_zero_of_half_lt_re` has type `DirichletLNonvanishingRightOfHalf`, defined in [`src/Statements.lean`](src/Statements.lean).

### 4. The generalized Riemann hypothesis for Dirichlet $L$-functions

For every Dirichlet character $\chi$ of positive modulus, including imprimitive characters, all zeros of $L(s,\chi)$ in the open critical strip lie on the critical line. For every $s\in\mathbb C$,

```math
\left(0<\mathrm{Re}(s)<1 \;\land\; L(s,\chi)=0\right)
\;\Longrightarrow\; \mathrm{Re}(s)=\tfrac12.
```

**Lean formalization.** `LFunction_eq_zero_re` has type `DirichletLZerosOnLine`, defined in [`src/Statements.lean`](src/Statements.lean).

### 5. The generalized Riemann hypothesis for primitive Dirichlet characters

Let $\chi$ be a Dirichlet character modulo $N$, with $N>0$. If its conductor is $N$, then $\chi$ is primitive, and every zero of $L(s,\chi)$ with $0<\mathrm{Re}(s)<1$ satisfies $\mathrm{Re}(s)=\tfrac12$.

**Lean formalization.** `LFunction_eq_zero_re_of_isPrimitive` has type `PrimitiveDirichletLZerosOnLine`, defined in [`src/Statements.lean`](src/Statements.lean).

## Build and inspect the proofs

Install [Elan](https://github.com/leanprover/elan) and Git. Elan selects Lean 4.33.1 from `lean-toolchain`, and Lake uses the dependency revisions in `lake-manifest.json`. From the repository root, run:

```sh
lake exe cache get
lake build Main
```

After the build succeeds, save the following as `CheckProofs.lean` in the repository root:

```lean
import Main

#print axioms riemannHypothesis
#print axioms riemannZeta_eq_zero_re
#print axioms LFunction_ne_zero_of_half_lt_re
#print axioms LFunction_eq_zero_re
#print axioms LFunction_eq_zero_re_of_isPrimitive
```

Run the file with the project’s Lean environment to list the axioms each theorem depends on:

```sh
lake env lean CheckProofs.lean
```

## Download the 14 original parts

The links below point to the files on Levent Alpöge’s site. Download all 14 parts and join them in order before extracting the archive.

- [`lean.tar.gz.part01`](https://alpo.ge/lean.tar.gz.part01)
- [`lean.tar.gz.part02`](https://alpo.ge/lean.tar.gz.part02)
- [`lean.tar.gz.part03`](https://alpo.ge/lean.tar.gz.part03)
- [`lean.tar.gz.part04`](https://alpo.ge/lean.tar.gz.part04)
- [`lean.tar.gz.part05`](https://alpo.ge/lean.tar.gz.part05)
- [`lean.tar.gz.part06`](https://alpo.ge/lean.tar.gz.part06)
- [`lean.tar.gz.part07`](https://alpo.ge/lean.tar.gz.part07)
- [`lean.tar.gz.part08`](https://alpo.ge/lean.tar.gz.part08)
- [`lean.tar.gz.part09`](https://alpo.ge/lean.tar.gz.part09)
- [`lean.tar.gz.part10`](https://alpo.ge/lean.tar.gz.part10)
- [`lean.tar.gz.part11`](https://alpo.ge/lean.tar.gz.part11)
- [`lean.tar.gz.part12`](https://alpo.ge/lean.tar.gz.part12)
- [`lean.tar.gz.part13`](https://alpo.ge/lean.tar.gz.part13)
- [`lean.tar.gz.part14`](https://alpo.ge/lean.tar.gz.part14)
