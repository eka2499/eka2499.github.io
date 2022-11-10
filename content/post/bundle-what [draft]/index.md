+++
author = "Elias Klakken Angelsen"
title = "Bundle what? Bundles of love, or any other fiber"
date = "2022-05-16"
description = "Aiming to understand Chern-Weil theory and the geometry behind characteristic classes. We start by giving a small recap about bundles"
tags = [
    "Algebraic Topology",
    "Differential Geometry",
    "Mathematical Physics",
    "Mathematics",
]
categories = [
    "Bundle theory",
    "Math",
]
series = ["Chern-Weil series"]
aliases = ["splasher"]
image = "splasher.jpg"
math = true
draft = true
+++

I've considered for a while to write a post about bundles, just to have established what they are and why they are fun on this blog. Many posts we will meet in the future will consider stuff happening in (co)tangent bundles, other fiber bundles or even in principal $G$-bundles for a Lie group $G$. 
Now, after some travelling, project work and procrastination of blog posting, I figured I'd introduce bundles once and for all as a part of a series on Chern-Weil theory and characteristic classes. 

As mentioned in the posts on [spectral sequences and multicomplexes](https://eka2499.github.io/tags/spectral-sequences/), I learned about spectral sequences when taking [a course](https://wiki.math.ntnu.no/ma3408/2021v/start) on algebraic topology at NTNU.
Bundles and characteristic classes were also a part of this course. I've worked a bit with bundles since the course, but characteristic classes has been a bit absent from my life at times. Nevertheless, I felt like I understood them more thoroughly than spectral sequences.
What I lacked was a geometric understanding of different classes. As I wanted to recap some things about Chern-Weil theory that I read a while ago, and (finally) learn the formal definition of a connection from differential geometry, we will now start a journey to understand (or recall) the theory of bundles, connections, curvature, Chern-Weil theory and characteristic classes. 

We start the bundle post by considering maybe the two most important bundles in geometry, namely the tangent and cotangent bundles assigned to a manifold.

## Tangent and cotangent bundles

If we are given a smooth manifold $M$, one can consider the tangent vectors at each point $p \in M$. These tangent vectors are often defined to be point derivations, as this can be shown to give the wanted theory. If this is not familiar to you, just think of them as tangent vectors in "the regular sense". The collection of all possible tangent vectors at a point $p$ is denoted $T_pM$, which is the tangent space to $M$ at $p$. Indeed, one can (and should) also consider the cotangent space $T_p^* M$ at $p$ to just be the dual space $(T_pM)^* $.

If we collect all of these tangent spaces, we get a space $TM = \coprod_{p \in M} T_pM$. An element of $TM$ can therefore be thought of as a pair $(p,v)$ where $p \in M$ and $v$ is a tangent vector to $M$ at $p$.
As you may see, the tangent bundle contains much information about the geometry of $M$, as it contains all the possible ways of finding tangent vectors, and therefore contains information such as which types of vector fields we can find at $M$. 

One should not that we have a canonical projection $\pi: TM \to M$ given by $\pi(p,v) = p$. This is quite an important feature of bundles!
To continue the thought we had about vector fields, we can actually define a vector field to be a split to the surjection $\pi$.
That is, a vector field $X$ is just a map $M \to TM$ such that $\pi X (p) = p$ for all $p \in M$. $X(p)$ is now on the form $X(p) = (p,v)$, as it lives in $TM$. As expected, it just assigns a tangent vector $v$ to each point $p$, which is exactly what vector fields do!
Such a split to the tangent bundle is called a section, and the sections of "a general bundle $\pi: E \to B$ is exactly such maps $s : B \to E$ such that $\pi s (b) = b$. 

Indeed, by gathering all of the cotangent spaces $T_p^* M$, we can form the cotangent bundle $T^* M$. 
The (smooth) sections of these are quite interesting, as they what we know as differential one-forms.

I'm quite sure we'll meet both of these bundles at a later stage, so we'll move on for now. Just to have it mentioned, we can use the topology of $M$ to induce the topology on these spaces, both at the (co)tangent space level and at the bundle level. One can even make both of them manifolds, giving them a lot of structure to exploit, if you want to!

## Fibre bundles

I often think of (co)tangent bundles as "gluing on a (co)tangent space at each point $p \in M$". This intuition of gluing on vector spaces actually gets us quite far. Natural questions to ask are if we can "glue on" other vector spaces, or maybe even if we can "glue on" other things than vector spaces at each point. The answers are yes and yes. The things we can glue on (to a point $p$), are called the fibers of the bundle (at the point $p$), and therefore much of this theory can be summarized by talking about fiber bundles.

### Vector bundles

If we consider the tangent bundle example we mentioned above, we had a manifold $M$, a new space $TM$, and a projection $\pi : TM \to M$ relating these spaces. The space $TM$ consisted of spaces $T_pM$ that we glued onto at a point $p$. This is the same as stating that $T_pM = \pi^{-1}(p)$ is the preimage (fiber) at the point $p$.
Note that since the manifolds are loca


### Sphere bundles

### Other weird things to glue on

## Principal $G$-bundles
### Examples!


## Relation between principal bundles and fibre bundles?


## Classification by Grassmannians?