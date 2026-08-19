---
layout: page
title: Kernels from flips
description: Given a flip, functorially construct a well-behaved kernel. 
img: 
importance: 2
category: work
---

One of the central questions in derived categories is the Bondal-Orlov conjecture.

**Bondal-Orlov Conjecture.**
 Assume that $X$ and $X^\prime$ are smooth projective varieties. If $$X$$ and $$X^\prime$$ are related by a flop, then there is an equivalence of their bounded derived categories of coherent sheaves
 
 $$
  D(X) \cong D(X^\prime).
$$

To get a sense of the situation, let us look at an example. Take $$\mathbb{C}^4$$ and consider the action of $$\mathbb{C}^\times$$ on $$\mathbb{C}^4$$ as follows.

$$
\begin{align*}
 \mathbb{C}^\times \times \mathbb{C}^4 & \to \mathbb{C}^4 \\
 (\alpha,x,y,z,w) & \mapsto (\alpha x , \alpha y, \alpha^{-1}z, \alpha^{-1}w).
\end{align*}
$$

Forming orbit spaces that have a natural structure of an algebraic variety is usually not possible. But, an insight of Mumford is that one can do so if one first deletes appropriate closed subsets. First, let us excise the linear subspace given by the vanishing of $x$ and $y$ simultaneously. Call this subset $V^+$. Then, the orbit space $$X^+:= (\mathbb{C}^4 \setminus V^+)/\mathbb{C}^\times$$ has the structure of an algebraic variety. It is the vector bundle $$\mathcal O_{\mathbb{P}^1}(-1)^{\oplus 2}$$. To be a bit more explicit, the functions $$z$$ and $$w$$ are local fiber coordinates on the vector bundle. If we look at where they both vanish, we see the projective space $$\mathbb{P}^1$$.

The observant reader will note that there is a blatant symmetry in the situation given by swapping $$(x,y) \leftrightarrow (z,w)$$ (and inverting $$\alpha$$). Let us denote the subspace given by the vanishing of $$z$$ and $$w$$ by $$V^-$$ and set $$X^- := (\mathbb{C}^4 \setminus V^-)/\mathbb{C}^\times$$. Notice that $$X^+$$ and $$X^-$$ are birational. Indeed, they share the open set obtained by removing both planes simultaneously $$ U := (\mathbb{C}^4 \setminus V^+ \cup V^-)/\mathbb{C}^\times$$. Plus both $$X^+$$ and $$X^-$$ are Calabi-Yau. One can verify that on $$X^+$$ the differential form $$du \wedge dv \wedge (xdy - ydx)$$ is non-vanishing and invariant under the $$\mathbb{C}^\times$$ action. This means it descends to a non-vanishing holomorphic volume form on $$X^+$$. Appealing to the blatant symmetry shows the same for $$X^-$$.

Since both $$X^+$$ and $$X^-$$ have trivial canonical bundle, one can see that the birational isomorphism $$X^+ \overset{\sim}{\dashrightarrow} X^-$$ preserves the canonical bundle. Since $$X^+$$ and $$X^-$$ are abstractly isomorphic, we might be tempted to conclude that the abstract isomorphism somehow induces the birational isomorphism. It is not so. To understand the geometry of $$X^+ \overset{\sim}{\dashrightarrow} X^-$$, let us introduce an intermediary.
Topologically we have a $$2$$-sphere, $$\mathbb{P}^1 \cong S^2$$, inside $$X^+$$ and $$X^-$$. Imagine shrinking that sphere down to a single point. Call this resulting space $$X^0$$. One can view $$X^0$$ as the space of $$\mathbb{C}^\times$$-orbits in $$\mathbb{C}^4$$ up to the equivalence relation generated nontrivial intersection of orbit closures.

We have a diagram
\begin{center}
\begin{tikzpicture}[scale=1,level/.style={->,>=stealth,thick},evel/.style={<->,>=stealth,thick}]
	\node (a) at (-1.5,1.5) {$X^+$};
	\node (b) at (1.5,1.5) {$X^-$};
	\node (c) at (0,0) {$X^0$};
	\draw[evel,dashed] (a) -- (b) ;
	\draw[level] (a) -- (c) ;
	\draw[level] (b) -- (c) ;
\end{tikzpicture}
\end{center}
where all maps are isomorphisms over $$U$$. The birational map $$X^+ \overset{\sim}{\dashrightarrow} X^-$$ deflates (blows-down) the $$\mathbb{P}^1$$ in the directions of $$x$$ and $$y$$ and then inflates (blows-ups) a $$\mathbb{P}^1$$ in the transversal directions of $$z$$ and $$w$$. The birational map $$X^+ \overset{\sim}{\dashrightarrow} X^-$$ is the primordial example of a flop.

A decent body evidence in support of the conjecture exists. In particular, Bondal and Orlov showed that their conjecture was true for the primordial flop described above.  Another is that it is Bridgeland proved it in complex dimension $$3$$ \cite{Bri} which covers the setting of String Theory. Although it has been checked in some special situations using varying methods, the question remains wide-open in higher dimension, $$\geq 4$$.

To make progress on this question in full generality, one first needs to know where to look for the equivalence. A well-known result of Orlov \cite{OrlovKernels} says that if $$X$$ and $$X^\prime$$ are equivalent then there must exist an object, called a _kernel_, $$K \in D(X \times X^\prime)$$ so that pulling up to product, tensoring with $$K$$, and pushing down gives the equivalence. A by-product of Bridgeland's work is that for a flop of smooth projective three-folds
\begin{center}
\begin{tikzpicture}[scale=1,level/.style={->,>=stealth,thick},evel/.style={<->,>=stealth,thick}]
	\node (a) at (-1.5,1.5) {$X$};
	\node (b) at (1.5,1.5) {$X^\prime$};
	\node (c) at (0,0) {$Y$};
	\draw[evel,dashed] (a) -- (b) ;
	\draw[level] (a) -- (c) ;
	\draw[level] (b) -- (c) ;
\end{tikzpicture}
\end{center}
the kernel is the structure sheaf of the fiber product $\mathcal O_{X \times_Y X^\prime}$. While this construction gives an equivalence in many examples, it is known not to work in general \cite{NamStratMukai}.

In \cite{BFD}, C. Diemer, D. Favero, and I construct a kernel associated to a $D$-flip or normal varieties and conjecture that it will settle the Bondal-Orlov Conjecture in general when the $D$-flip is a flop. The construction uses a realization of Reid in the 1980s that all flips can be presented as variations of GIT quotients, like the example in the introduction, combined some Derived Algebraic Geometry (not to be confused with derived categories in Algebraic Geometry!) to first construct an idempotent kernel ``upstairs'' in the equivariant setting. The existence of this idempotent kernel, plus its relation to a construction of Drinfeld \cite{DriGm} is itself an interesting fact.

More so, in \cite{BFD}, we give a prescription of a more general construction which can be viewed as extending Drinfeld's construction from $\mathbb{G}_m \subset \mathbb{A}^1$ to $G \subset M$ where $M$ is a linear algebraic monoid and $G$ is its group of units. In \cite{GrassFlop}, we show how this produces a kernel giving an equivalence for the ``Grassmann flop'' studied in \cite{DSGrassFlop}.

Universally recognized as the most forbidding conceptual impediment to this approach is class of birational 
maps known as stratified Mukai flops \cite{NamStratMukai,Kaw-stratified-mukai}.

This class of examples previously broke community expectations on the Bondal-Orlov conjecture. 

With Chidambaram and Favero, we surmounted this challenge \cite{BCF21}.

\begin{theorem}
  The $Q$ construction provides a Fourier-Mukai kernel for stratified Mukai flops. 
\end{theorem}

Previous work of Cautis, Kamnitzer, and Licata had already shown the existence of Fourier-Mukai 
kernels but used a technique that only applied in special examples \cite{Cau12}. Furthermore, the kernel we obtain has 
homology in multiple degrees. This is the first such example coming 
from a flop. 

Our result points the way forward to a general resolution of the Bondal-Orlov conjecture.

