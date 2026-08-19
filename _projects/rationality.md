---
layout: page
title: Brauer group invisibility, derived categories, and rationality
description: What can the derived category say about rationality?
img: 
importance: 3
category: work
---

Let's return to our pre-calculus equation from the introduction: $x^2 + y^2 = -1$. Homogenizing we are looking at a Zariski open subset of $X = Z(x^2+y^2+z^2) \subset \mathbb{P}^2_{\mathbb R}$. We still have $X(\mathbb{R}) = \emptyset$. If we instead allow complex solutions to the polynomial, then $X_{\mathbb{C}} \cong \mathbb{P}^1_{\mathbb{C}}$ which has many points.

The variety $X$ is an example of a Severi-Brauer variety - those that are isomorphic to projective space if we sufficiently enlarge the base coefficient field. The example of $X$ shows that a Severi-Brauer variety need not be isomorphism to projective space without passing to a field extension. A basic test for the utility of the derived category is the following question.

\begin{Question}
 Can one use to the derived category to detect when a Severi-Brauer variety is not split over $k$, ie not $\mathbb{P}^n_k$?
\end{Question}

The answer is yes. The difference is in the complexity of the building blocks. Fix a $k$-algebra $A$. An $A$-exceptional object $E$ in $D(X)$ is one that satisfies
\begin{itemize}
  \item $\op{End}(E) = A$ and
  \item $\op{Hom}(E,E[n]) = 0, \ \text{for all }n \neq 0$.
\end{itemize}
A foundational result of Beilinson says that $D(\mathbb{P}^n_k)$ possesses a full $k$-exceptional collection. A full exceptional collection is, precisely, an ordered list of objects $E_1,\ldots,E_n$ such that
\begin{itemize}
  \item each $E_i$ is $A_i$-exceptional for $A_i = \op{End}(E_i)$,
  \item $\op{Hom}(E_i,E_j[n]) = 0, \ \text{for all } n, i > j$, and
  \item the $E_i$ generate the category.
\end{itemize}
If all the $A_i$ are $k$, then we have a full $k$-exceptional collection. If all the $A_i$ are separable field extensions of $k$, we say we have a full \'etale-exceptional collection.

However, using noncommutative motives, \cite{Raed} showed that a non-split Severi-Brauer variety can never possess a full \'etale-exceptional collection. Thus, we can detect rationality of $X$, and hence the existence of rational points, from a property of the derived category. Possession of a full \'etale-exceptional collection can be summarized in the following satisfying manner: $X$ possesses a full \'etale-exceptional collection if $D(X)$ can be built from the derived categories of smooth zero-dimensional varieties over $k$, ie points. This leads one to wonder the following.

\begin{Question}
 If $X$ possesses a full \'etale-exceptional collection, is $X$ rational?
\end{Question}

The answer to this question is no \cite{BDLM2}.

\begin{theorem}
  There exists a smooth projective geometrically irreducible variety over $\mathbb{Q}$ which has no rational points but possess full \'etale-exceptional collections.
\end{theorem}

To motivate the construction of such examples, we return to the Severi-Brauer variety $X$ over $\mathbb{R}$ defined by $x^2+ y^2 + z^2 = 0$. The group $S^1$, ie the real algebraic variety $x^2+y^2=1$, naturally acts on $X$. If we take $z=1$, this open subset $U$ is a nontrivial $S^1$-torsor and $X$ is a smooth projective compactification where the action of $S^1$ extends.

We can build $X$ by twisting $\mathbb{P}^1_{\mathbb{R}}$ by the torsor $U$:
\begin{displaymath}
  X \cong (U \times \mathbb{P}^1_{\mathbb{R}})/S^1
\end{displaymath}
where
\begin{displaymath}
  \alpha \cdot (u, z) = (u \alpha^{-1}, \alpha z).
\end{displaymath}
The action of $S^1$ stabilizes the full exceptional collection $\mathcal O, \mathcal O(1)$ up to isomorphism. Moreover, we can $\mathcal O$ and $\mathcal O(1)^{\oplus 2}$ carry $S^1$-equivariant structures. This yields a homomorphism
\begin{displaymath}
  H^1(\mathbb{R}, S^1) \to H^2(\mathbb{R}, \mathbb{G}_m) = Br(\mathbb{R}).
\end{displaymath}
by taking a torsor to the endomorphisms of the twist of $\mathcal O(1)^{\oplus 2}$ on twisted variety. This can be done in general.

In \cite{BDLM2}, we show explicitly how to transfer equivariant objects of the derived category along twists by torsors. Given a smooth projective compactification $X$ of a linear algebraic group $G$ with a full \'etale-exceptional collection, we get a homomorphism
\begin{displaymath}
  H^1(k, G) \to H^2(k, \mathcal D(K))
\end{displaymath}
where $D(K)$ is the Cartier-dual of the permutation module $K_0(X_{\bar{k}})$. The twisted exceptional collection remains \'etale exactly when the torsor lies in the kernel of this homomorphism.

This motivates us in \cite{BDLM1} to consider all probes by Brauer groups:
\[
\bigcap_E \bigcap_\alpha \op{ker}
\left( \alpha(k) : H^1(k,G) \to Br(E) \right)
\]
where the intersection runs over all \'etale algebras $E$
and $\alpha$ runs over every normalized cohomological invariant
in $\op{Inv}_k(G, Br(- \otimes_k E))_{norm}$ \cite{Skip}. As the homomorphism
\begin{displaymath}
  H^1(k, G) \to H^2(k, D(K))
\end{displaymath}
being one such normalized cohomological invariant, if we can check nontriviality of this kernel, we can find our desired torsor.

We identify this with a more concrete invariant of $G$. Given a reductive algebraic group $G$, we define
\[
\ICP(k,G) := \op{im}\left(H^1(k,C) \to H^1(k,G)\right)
\]
where $C \to G$ is a coflasque resolution of $G$ \cite{CT2008}. Then,

\begin{theorem}
  Let $G$ be a reductive algebraic group over $k$. Then
\[
\ICP(k,G) = \bigcap_E \bigcap_\alpha \op{ker}
\left( \alpha(k) : H^1(k,G) \to Br(- \otimes_k E)) \right).
\]
\end{theorem}

This identification allows to check that $\ICP(k,G)$ is a stable-birational invariant of $G$ and is trivial for retract rational $G$. Over a global field $k$, we identify $\ICP(k,G)$ with the Tate-Shafarevich group of $G$.

The simplest source of groups with nontrivial $\ICP$ are norm-one tori - in particular norm-one tori associated to biquadratic extensions. In \cite{BDLM2}, we use an exceptional constructed in \cite{CT} to produce a smooth projective compactification $Y$ of $R^{(1)}_{L/k} \mathbb{G}_m$ with a full \'etale exceptional collection of sheaves for any biquadratic extension $L/k$. Twisting this exceptional collection by the nontrivial element of $\ICP(k,  R^{(1)}_{L/k})$ produces another \'etale collection but kills all $k$-rational points. Taking products with copies of projective space boosts the dimension of our examples up from $3$ to any integer $\geq 3$.

We see that the counterexample is in particular a(n arithmetic) toric variety over $\mathbb{Q}$. However, if we restrict our attention to strict exceptional collections (i.e. Orlov's conjecture), then we can prove rationality for toric varieties.

\begin{theorem}
    Let $X$ be a smooth projective toric variety over a field $k$ with $X(k) \neq \emptyset$. If $D(X)$ has a full $k$-exceptional collection, then $X$ is rational.
\end{theorem}

Currently with Lamarche, we are studying a class of smooth Fano toric varieties where possession of a full \'etale-exceptional collection is equivalent to rationality.
