---
layout: page
title: Frobenius and generation
description: Does the image of the structure sheaf under Frobenius generate the derived category
img: 
importance: 1
category: work
---

Say you are handed a triangulated category $$\mathcal T$$. Whether it is $$D^\pi(\operatorname{Fuk} X)$$ for some symplectic manifold, $$D^b(Y)$$ for an 
algebraic variety, or $$D(\operatorname{mod} A)$$ for a finite dimensional algebra $$A$$, perhaps the most fundamental question about the 
category is:

**Question**: Is there a generator for $$\mathcal T$$? If so, is there a good one?

Answering this question has been a fundamental component to essentially all of my work. Being able to locate a generator compresses the 
information about the category into a more manageable amount. 

Given a variety $$X$$ over a field of characteristic $$p$$, we have the Frobenius map $$\operatorname{Fr}_r : X^{(p^r)} \to X$$. The properties of the 
pushforward $$\operatorname{Fr}_{r\ast} \mathcal O$$ have proven exceptionally useful, especially in the presence of a group action. From the seminal result of 
Hochster and Hueneke on Cohen-Macaualayness of invariant rings to recent results tying these questions of noncommutative crepant 
resolutions}, exploiting the Frobenius morphism has yielded deep insights into questions in commutative algebra and algebraic 
geometry.

Observing this, the obvious question presents itself. 

**Question**: Does the object $$\operatorname{Fr}_{r\ast} \mathcal O$$ generate $$D^b(X)$$?

The answer in general is unknown. In 2006, Bondal claimed the following:

**Bondal's Conjecture**. Let $$X$$ be a smooth projective toric variety. Then $$\operatorname{Fr}_{r\ast} \mathcal O$$ generates $$D^b(X)$$ for $$r \gg 0$$.

Smooth toric varieties present an especially pleasant case. One can make sense of Frobenius over a 
general field. Since any toric variety of dimension $$n$$ admits a cover isomorphic to $$\mathbb{A}^n$$, 
we have a characteristic independent (relative) Frobenius coming from gluing the homomorphisms 

$$
\begin{align*}
  k[x_1,\ldots,x_n] & \to k[x_1,\ldots,x_n] \\
  x_i & \mapsto x_i^p
\end{align*}
$$

Thus Bondal's conjecture is of interest beyond finite characteristic. 

Partial results were obtained in low dimensions
but, in general, the question had been open for a decade and a half. 

With A. Duncan and P. McFaddin, we resolve it. 

**Theorem**. Bondal's Conjecture is true. 

In fact it is true for non-projective smooth toric varieties. Our proof is sufficiently 
algorithmic that it both amenable to formalization and computer implementation.

We are currently working to extending the result to spherical varieties and tropicalizing the argument. 
