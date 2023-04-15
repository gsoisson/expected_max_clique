# The Expected Maximum Clique Problem

## Description Of The Problem

> An advertising company wants to select a group of people in which there exists a **large subset of group members** such that they all know each other. The company only knows the number of persons $n$ in the group and the probability $p$ that two persons in the group know each other.

## Mathematical Modelling

Let $G=(V,E)$ be an undirected graph, where $V=1, 2,..,n$ and $E⊂V×V$. Formally, a clique $C$ is a subset of vertices such that all vertices in $C$ share an edge, $C⊂V$ and $(i,j)∈E$ for any $i,j∈C$.

A clique is said to be :
*   maximal if it is not a subset of a larger clique in $G$ (i.e. a clique with a greater number of vertices)
*   maximum if there is no larger clique in $G$

Then, finding the largest subset of group members such that they all know each other can be formulated as finding the maximum clique in $G$.

Thus, the expected maximum clique problem is : <br />
Given a random graph $G=(V,E)$ of which we only know its number of vertices $n=|V|$ and the probability $p$ that there is an edge between any two vertices, $p=P((i,j)∈E)$ for any $i,j∈V$, what is its expected maximum clique?

## Estimating The Expected Maximum Clique

To achieve this, we propose a method that involves generating a large number of graphs $N$, calculating the maximum clique of each graph, and taking the average. By the law of large numbers, this should give a good approximation of the expected maximum clique when $N$ is sufficiently large, with $N=100$ used in our experiments. The main challenge then becomes calculating the maximum clique of a given graph.

## Maximum Independent Set Formulation Of The Maximum Clique Problem

As shown in class, the maximum clique problem is equivalent to the maximum independent set problem. An independent set $I$ is a subset of vertices in a graph such that there is no edge between any two vertices in the independent set, $I⊂V$ and $i,j∉E$ for any $i,j∈I$. 

So given a graph $G=(V,E)$ in which we want to find a maximum clique, we can construct a complementary graph $G′=(V',E')$ of $G$ where $E'$ is the set of all edges that are not in $E$. Now, if we find a maximum independent set in $G′$ it will be a maximum clique in $G$. Therefore, let us solve the maximum independent set problem in $G'$.

## Different Approaches To The Maximum Independent Set Problem

We propose two ways to solve the maximum independent set problem:
* Solving the 0-1 Linear Programming problem
* Using a simple yet fast algorithm
