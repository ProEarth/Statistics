---
Title: STAT601 Statistics 1 - Basics of Probability Theory
Author: Shi Chen
Date: 2025-08-30
Labels:
  - Math
  - Probability
  - Statistics
  - Algebra
  - Probability Function
  - Probability Axioms
  - Probability Basic Theorems
  - Counting
  - Permutations
  - Combinations
---

# 1. Probability Theory
## 1.1. set theory
Random Experiment
>[!example]
> toss a coin $\{H,T\}$

>[!info] Definition: Sample Space
>The set of all possible outcomes is sample space $\mathcal{S}$

>[!example]
>Toss a coin until 1st fail
>$\mathcal{S}=\{T,HT,HHT,\cdots \}$ countable

>[!example]
>Life of lightbulb
>$\mathcal{S}=[0, \infty)$ uncountable

> [!info] Definition: Event
> An event is a subset of $\mathcal{S}$.


>[!example]
>$\{1st~fail~occurs~before~3rd~toss\}$
> $=\{T,HT\}  \in \mathcal{S}$

> [!info] Definition: Event operations
>> containment
>> empty set (null set)
>> 1. union ($A$ or $B$)
>> $$A\bigcup B=\{x\in \mathcal{S}:x\in A \quad or \quad  x \in B\}$$
>> 2. intersection ($A$ and $B$)
>> $$A\bigcap B=\{x\in \mathcal{S}:x\in A \quad and \quad  x \in B\}$$
>> 3. supplement (not $A$) complement
>> $$A^c=\{x\in \mathcal{S}:x\notin A\}$$
>> 4. difference $A\backslash B=A \bigcap B^c$


> [!info] Definition: partition
> 1. A and B are disjoint (mutually exclusive) if $A \bigcup B = \varnothing$
> 2. $A_1,A_2,\dots,A_n$ form a patition of S if they are pairwise disjoint and the union $\bigcup_{i=1}^n A_i=S$ is exactly the sample space.

> [!tip] Theorem: distribution laws
> $$
> A \bigcap \left(B \bigcup C\right)=\left(A \bigcap B\right) \bigcup \left(A \bigcap C\right)
> $$
$$A \equiv B \iff A \subset B \ \ and \ \  B \subset A$$

>[!info] Definition: De Margain's laws
> 1. $(\bigcup_{i=1}^{\infty} A)^c=\bigcap A_i^c$
> 2. $(\bigcap_{i=1}^{\infty} A)^c=\bigcup A_i^c$

## 1.2 basics of prob theory

> [!info] Definition: Algebra
> A set of events $\mathcal{A}$ is an algebra if 
>> 1. $A \in \mathcal{A} \Rightarrow A^c \in \mathcal{A}$
>> 2. $A_1,A_2 \in \mathcal{A} \Rightarrow A_1 \bigcup A_2 \in \mathcal{A}$

These generates that $A_1\bigcup A_2$, , $\varnothing$($A\bigcap A^c$), $S$($A\bigcup A^c$) must be in $\mathcal{A}$,

>[!info] Definition: sigma-Algebra
>a non empty set of events $\mathcal{B}$ is a $\sigma$-algebra if $\mathcal{B}$ is an algebra and 
>$\bigcup_{i=1}^{\infty} A_i \in \mathcal{B},\forall A_i\in \mathcal{B},i=1,2,\dots$

>[!warning] Remarks
>$\forall A_1,A_2,\dots, \in\mathcal{B}$
>$\Rightarrow A_1^c,A_2^c,\dots \in \mathcal{B}$
>$\Rightarrow \bigcap_{i=1}A_i=(\bigcup_{i=1}A_i^c)^c \in \mathcal{B}$

>[!example] Borel sigma-Algebra 
> $S=(-\infty,+\infty)$ is Borel sigma-Algebra 
> $\mathcal{B}$ consists of all open sets $(a,b)$ and all unions and intersections of them

> [!definition] probability function (Kolmogorov Axioms)
> Given a sample space $\mathcal{S}$ and $\sigma$-algebra $\mathcal{B}$, a probabiliy function $P$ on $(P,\mathcal{S},\mathcal{B})$ satisfies,
>> 1. $P(A)\geq 0,\quad \forall A \in \mathcal{B}$
>> 2. $P(\mathcal{S})=1$
>> 3. If $A_1,A_2,\dots, \in\mathcal{B}$ is pairwise disjoint, then $P\left(\bigcup_{i=1}^{\infty} A_i\right)=\sum_{i=1}^{\infty} P(A_i)$

>[!tip] Theorem: 
> $P$ is a probability function and $A\in \mathcal{B}$, then,
> > 1. $P(\varnothing)=0$
> > 2. For any pairwise disjoint $A_1,A_2,\dots,A_n \in\mathcal{B}$, $P\left(\bigcup_{i=1}^{n} A_i\right)=\sum_{i=1}^{n} P(A_i)$
> > 3. $P(A^c)=1-P(A)$
> > 4. $P(A)\leq 1$

>[!tip] Theorem: 
> $P$ is a probability function and $A，B\in \mathcal{B}$, then,
> > 1. $P(B\bigcap A^c)=P(B)-P(A\bigcap B)$
> > 2.  $P(A\bigcup B)=P(A)+P(B)-P(A\bigcup B)$
> > 3. If $A \subset B$, then $P(A)\leq P(B)$
> > 4. (Bonferroni inequality) $P(A\bigcap B) \geq P(A)+P(B)-1$

### counting
for finite sample space $S=\{s_1,s_2,\dots,s_n\}$, and each outcome has equal probability $P(i)=\frac{1}{|S|}=\frac{1}{n}$, then given $A$,
$$P(A)=\frac{|A|}{|S|}=\frac{\#~ elements~in~A}{\#~ elements~in~S}$$

>[!tip] Theorem: Fundamental Theorem of Counting
> If a job has $k$ sequential steps, and the $i$ th step can be done in $n_i$ ways, $i=1,2,\dots,k$, then the job can be done in $n_1\times n_2 \times \dots \times n_k$ ways.

>[!info] Definition: Permutations and Combinations
> \# permutations: $_nP_r=\frac{n!}{(n-r)!}$
> \# permutations: $_nC_r= \frac{_nP_r}{r!}=\frac{n!}{r!(n-r)!}=  \binom{n}{r}$

>[!example] Sample with replacement
> Sample $r$ from a finite sample space $S=\{s_1,s_2,\dots,s_n\}$.
> 1. In the ordered case, there are $n^r$ possibilities
> 2. In the unordered case, there are $\binom{n+r-1}{r}$ possibilities.
>> How many ways to put $r$ markers into $n+r-1$ positions?
>> Answer: $\binom{n+r-1}{r}$