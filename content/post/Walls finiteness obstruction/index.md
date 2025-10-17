+++
author = "Elias Klakken Angelsen"
title = "Wall's finiteness obstruction"
date = "2024-10-24"
description = "Algebraic K-theory is a big thing. We try to motivate why it is a natural thing to study, and why a topologist should care."
tags = [
    "Algebraic Topology",
    "Algebraic K-theory",
    "Wall's finiteness obstruction",
    "Whitehead groups",
    "Mathematics",
]
categories = [
    "Algebraic K-theory",
    "Math",
]
series = ["Algebraic K-theory"]
aliases = ["Algebraic K-theory"]
image = "images/Wall-finiteness.png"
math = true
draft = true
+++

For a long time, I have been interested in $K$-theory. I am no expert, and I have not really been focusing on "learning all the hands-on K-theory there is". However, I think bundles are cool, and $K$-theory has been a recurring theme throughout my mathematical journey. 

For example, I read (and did not understand) some notes on topological $K$-theory in my second year, and when I wrote a bachelors thesis on $C^*$-algebras and non-commutative tori, it showed up as a topological tool, which is surprisingly useful in the world of operator algebras. During my master years, I was getting interested in stable and chromatic homotopy theory, and when I wrote my master thesis on differential- and Hodge-filtered cohomology theories, $K$-theory followed me to give cool examples of beautiful maths and ideas. 

Whether it was topological $K$-theory, operator $K$-theory, Karoubis Multiplicative $K$-theory, or even Morava $K$-theory, I felt $K$-theory was something I "knew something about". However, algebraic $K$-theory is a beast I never dared to learn more about. Why? Well, it is immensly difficult to compute, all the "basic theory" (of $K_0, K_1, K_2$, for example) can become quite technical and algebraic, as well as extremely messy (yes, I am looking at you, $K_2$). I mean, operator and topological $K$-theory can also be hard, but then you only need to deal with two things, $K_0$ and $K_1$, due to Bott periodicity, which is not possible for algebraic $K$-theory.

However, something has changed (probably starting a PhD, lol), and I just embarked on learning Algebraic $K$-theory.
I will try to skim through some constructions, as well as some motivation in this blogpost. 

# The Serre-Swan theorem and $K_0$-theory

One of the most beautiful theorems in math, at least in my opinion, is the Serre-Swan theorem.

**Theorem: (Serre-Swan)**
Let $X$ be a compact Hausdorff space, and $C(X)$ the ring of continuous $\mathbb{R}$-valued functions.
The globals sections functor $\Gamma: \operatorname{VBun}(X) \to \operatorname{fgproj}(C(X))$ from the category of vector bundles on $X$ to the category of finitely generated modules over $C(X)$ is an equivalence of categories.


I mean, this theorem is amazing. It gives a bridge between geometry and topology, allowing us to define topological versions of $K$-theory on one side, and algebraic versions of $K$-theory on the other. Note for example that the objects $C(X)$ are precisely the *commutative* $C^* $-algebras. For an arbitrary $C^*$-algebra $A$, one can think of the category $\operatorname{fgproj}(A)$ as "noncommutative vector bundles on $A$". This is precisely the idea that lets us define operator $K$-theory as well.

One reasonable question however, is "why finitely generated and projective"?
Intuitively, finitely generated comes from the fact that we work with finitely dimensional vector bundles, so the "bases" correspond to "generators". The projective part is maybe more interesting. 
Over nice spaces, one can show that if $F \to X$ is a sub-bundle of $E \to X$, then $F$ is a direct summand in $E$. By certain lemmas, we can realize that all bundles $F$ are summands in the trivial bundles. This is a fact on the topological side of the Serre-Swan theorem. On the algebraic side, this amounts to bundles giving modules which are summands in free modules. Those are precisely the projectives.

Anyways, let's get back to algebraic $K$-theory. Studying isomorphism classes of finitely projective modules only gives us a monoid under direct sum. If we want an abelian group, we have to group complete.

**Definition: $K_0(R)$**

Let $R$ be a ring and $\mathbf{P}(R)$ denote the monoid of isomorphism classes of finitely generated projective $R$-modules.
Then we define the $K$-theory of $R$ as the group completion $K_0(R) = \mathbf{P}(R)^{grp}$.
This is contravariantly functorial as a map $R \to S$ lets us define a $R$-module from an $S$-module, giving a map $K_0(S) \to K_0(R)$.

It should be noted that we can define $K_0$ of not only rings, but other objects as well. 
For symmetric monoidal categories, this is essentally the same construction as above.
$K$-theory of abelian (and more generally exact) categories amount to defining $K_0(\mathcal{A})$ to be the free abelian group on objects of $\mathcal{A}$ subject to the relations that $[A] = [A']+[A'']$ if there exists a short exact sequences 
$$0 \to A' \to A \to A'' \to 0.$$

One can of course ask if we can take $K_0(Mod R)$ for some $R$, but there are size-issues regarding this. If we try, we will just obtain $K_0(Mod R) = 0$, by the Eilenberg Swindle. However, in nice situations (if R is noetherian, for example), we can consider the category of finitely generated modules, which under group completion yields what we call $G_0$-theory.
If the ring $R$ is also regular, then $K_0(R) = G_0(R)$.

# Wall's finiteness obstruction

We will not try to write a textbook on $K$-theory here, but rather explore some interesting facts. 
To do that, let us first ask the following question:
If $M$ is a nice space, say a compact manifold, does $M$ have the homotopy type of a finite CW-complex?

In special cases, we can answer this question immediately. For example, if $M$ is smooth, it can be triangulated, and thus it is even homeomorphic to a finite CW-complex. In the general case, it is hard. We know that $M$ has the homotopy type of a CW-complex (call it $X$), so it is sufficient to figure out if $X$ has the homotopy type of a *finite* CW-complex. 
We do not a priori know any finiteness conditions, but we may hope that some information about this homotopical question can be found in the homotopy groups of $X$. 

In general, for a group $G$, we can consider the group ring $\mathbb{Z}[G]$. By the augmentation map, defined by sending all of $G$ to $1$, we get a surjective map $\varepsilon: \mathbb{Z}[G] \to \mathbb{Z}$, which splits as $\mathbb{Z}$ is a projective abelian group. On $K$-theory, we can consider the quotient of $K_0(\mathbb{Z}[G])$ by $K_0(\mathbb{Z}) = \mathbb{Z}$. This defines the zeroth Whitehead group, $Wh_0(G)$.
If we apply this to $G = \pi_1(X)$ for some CW-complex $X$ as above, then we can, with some extra assumption, obtain an obstruction to $X$ being homotopy equivalent to a finite CW-complex!

**Definition: (Finitely dominated CW-complexes)**

A CW-complex $X$ is *dominated* by a CW-complex $K$ if $X$ is a retract of $K$.
That is, there are maps 
$$X \to K \to X$$ that compose to the identity on $X$ (up to homotopy).
We say $X$ is *finitely dominated* if there exist a finite CW-complex $K$ such that $X$ is dominated by $K$.

Since finitely dominated complexes are retracts of the finite CW-complexes, we can note that the finitely dominated complexes correspond precisely to the compact objects in the $\infty$-category of spaces.

**Theorem: (Wall's finiteness obstruction)**

Assume a CW-complex $X$ is finitely dominated. Then, there exists an element $w(X) \in Wh_0(\pi_1(G))$ such that 
$w(X) = 0$ if and only if $X$ is homotopy equivalent to a finite CW-complex. 

Just the existence of it can be used to give a new class of spaces that have the homotopy type of a finite CW-complex.

**Corollary:**
Let $X$ be a finitely dominated space which is simply connected. Then $X$ has the homotopy type of a finite CW-complex.

*Proof:*
This boils down to
$$w(X) \in Wh_0(\pi_1(X)) = Wh_0(pt) = K_0(\mathbb{Z}[pt])/K_0(\mathbb{Z}) = 0.$$


## Characterizing finitely dominated spaces

All the examples of fintely dominated spaces I can come up with on the spot, will certainly be finite CW-complexes, so I'm tempted to ask how "non-trivial" $w(-)$ really is. 
This requires a better understanding of what finitely dominated spaces really are.

Recall that a sheaf $\mathcal{L}$ of abelian groups is a local system of abelian groups if it is locally constant. That is, if each point has an open neighborhood $U$ such that $\mathcal{L}|_U$ is isomorphic to a sheafification of a constant presheaf. Sheaf cohomology yields a way to take cohomology with coefficients in a local system. 
The reason we care is the following theorem. 

**Theorem: (Representations of fundamental groups and local systems)**

For a connected $X$, the category of representations of $\pi_1(X,x_0)$ is equivalent to the category of local systems on $X$. 
This is independent of basepoint for connected $X$, and can be extended to non-connected $X$ by the above equivalence on extended components.

This gives us a way to characterize finitely dominated spaces.

**Theorem: (Characterization of finitely dominated spaces)**

A space $X$ is finitely dominated if and only if the following conditions hold:

1. $\pi_0(X)$ is a finite set.

2. $\pi_1(X,x)$ is a finitely presented group for each $x \in X$. 

3. For each $x \in X$, let $X_x^o$ denote the path component of $x$, let $V$ be a representation of $\pi_1(X,x)$ (which corresponds to a local system). The assignment $V \mapsto H^k(X^o; V)$ commutes with filtered directed colimits.

4. With the setup above, there exist an integer $n$ such that for any representation $V$ of $\pi_1(X,x)$, $H^k(X^o; V) = 0$ for $k > n$.
In this case, we say $X$ has homotopy dimension $\leq n$. 


## The image of $w(-)$ in $Wh_0(\pi_1(X))$

We return to the question of understanding $w(X)$.
That is, if we are given a group $G$ and a class $[P]$ in $Wh_0(G) = K_0(\mathbb{Z}[G])/K_0(\mathbb{Z})$, can we find a finitely dominated CW-complex $X$ such that $G = \pi_1(X)$ and $w(X) = [P]$? In particular, are there fintely dominated CW-complexes that are *not* finite CW-complexes?

If $G$ is a finitely presented group, we can always build a finite (2-dimensional) CW-complex $X_0$ such that $G = \pi_1(X_0)$ using the generators of $G$ to determine $1$-cells and relations of $G$ to determine the $2$-cells of $X_0$.

Let the class $[P]$ be represented by a finitely generated projective module $P$. Then $P$ is a retract of a free module, as it is projective. That is, $P$ is the image of an idempotent map $e: \mathbb{Z}[G]^r \to \mathbb{Z}[G]^r$.

To pass this to spaces, note that 
$$\mathbb{Z}[G]^r = \bigoplus_r H_2(S^2;\mathbb{Z}[G]) = H_2(\bigvee_r S^2;\mathbb{Z}[G]) = H_2(\bigvee_r S^2) \otimes \mathbb{Z}[G] \oplus (\text{some Tor that vanishes as } H_1(S^2)=0).$$
By the Hurewicz theorem, $H_2(S^2) = \pi_2(S^2) = [S^2, S^2]$.
That is, we can realize the map $e$ as a wedge sum of maps, where each wedge summand is of the form 
$[S^2, S^2] \to [S^2, S^2].$ By the Yoneda lemma, this is essentially $ [ -, S^2] (S^2) = [S^2, S^2]$, which means that each summand of $e$ comes from a map $S^2 \to S^2$.

Thus, we can see that the idempotent map $e$ must be induced from a map of spaces
$$\varepsilon: \bigvee_r S^2 \to \bigvee_r S^2,$$ 
which must idempotent in the homotopy category by functoriality of $H_2$, if it is supposed to induce an idempotent. 

Intuitively, the image of $\varepsilon$ will essentially yield the space that should have $P$ as homology. However, it is not a CW-complex always? But in htopycat, so ???


#### Todo Show (Lurie remark 23) that all for G finitely presented, all of Wh_0(ZG) arises as w(X) for some X.




## Making $w(X)$ more explicit

Given some cohomological bound on $X$, which is automatic for finitely dominated spaces, then we can explicitly define $w(X)$ in terms of computable pieces. 


#### Explain an idea for computing it

We obtain the following explicit way to view $w(X)$. 

**Theorem: (Explicit formula for $w(X)$)**

Let $X$ be a finitely dominated space, and make the following choices:
- Choose an integer $n \geq 2$ such that $X$ has homotopy dimension $\leq n$.
- Choose a CW-complex $Z$ of dimension $<n$.
- Choose a $(n-1)$-connected map $f: Z \to X$.

Then, $H_n(X,Z; \mathbb{Z}[G])$ is a finitely generated projective $\mathbb{Z}[G]$-module, and $w(X)$ is the class
$$w(X) = (-1)^n [H_n(X,Z; \mathbb{Z}[G])] \in Wh_0(\mathbb{Z}[G]).$$


#### TODO and what is this rep-cohom wrt. UCT?

#### TODO do an explicit computation with this formula



![The subtitle?](images/splasher.jpg)
*text*
 [this amazing video](https://www.youtube.com/watch?v=OnvQggy3Ezw) on freediving! 


