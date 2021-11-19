# ![unnamed](https://tva1.sinaimg.cn/large/008i3skNgy1gwjntd1innj30e8021aac.jpg)

# Kuan's Logic Tutorial 02

2021.11.19

![Screen Shot 2021-11-16 at 5.14.13 AM](https://tva1.sinaimg.cn/large/008i3skNgy1gwjnte3e2pj31g20lqn2a.jpg)

[toc]

---

**Review of Tutorial 01:** Sets theory

---

# 2. Proofs

**Key points (with links):** 

- [Formal](https://people.cs.pitt.edu/~milos/courses/cs441/lectures/Class5.pdf) vs. [Informal proofs](https://people.cs.pitt.edu/~milos/courses/cs441/lectures/Class6.pdf)
- [Formal proof strategies](http://openaccess.uoc.edu/webapps/o2/bitstream/10609/57346/1/Formal%20Proof%3B%20Understanding%2C%20writing%20and%20evaluating%20proofs.pdf)
- **The structure and vocabulary are used in formal proofs.**

---

## 2.1. What?

- In short, proof is **evidence or argument establishing a fact or the truth of a statement.**

  A mathematical proof is an inferential argument for a mathematical statement, showing that the stated assumptions logically guarantee the conclusion.

- Proofs employ logic expressed in mathematical symbols, along with [**natural language**](https://en.wikipedia.org/wiki/Natural_language) which usually admits some ambiguity. 

  ---

  ### 2.1.1. Informal phroofs

- The steps of the proofs are not expressed in any **[formal language](https://en.wikipedia.org/wiki/Formal_language)** as (e.g. propositional logic). Steps are argued less formally using English, mathematical formulas and so on

---

**Example 01:**  Informal proof of $¬(φ ∨ ψ) → ¬φ ∧ ¬ψ$.

​					Assume $¬(φ ∨ ψ)$

​					Now also assume $φ$. This gives $φ ∨ ψ$, a contradiction. So, $¬φ$. 

​					Similarly, assuming $ψ$ gives a contradiction. So, $¬ψ$. 

​					From $¬φ$ and $¬ψ$, $¬φ ∧ ¬ψ.$

---

Natural language can deal with ambiguity.

**Exercise 01:** *Every men loves a woman.*

- Paraphrase:  

  				​				For every man, there is a woman, and it's possible that each man loves a different woman

  ​				$\forall x. MAN(x)\to (\exist WOMAN(y)\and LOVE(x,y))$ 

  ​				There is one particular woman who is loved by every man.

  ​				$\exist y.WOMAN(y)\and(\forall x.MAN(x)\to LOVE(x,y))$

  ---

  ### 2.1.2. Formal phroofs

- Starting from the definition of the problem and the set of accepted axioms, **a proof follows the logical inference rules until the statement is validated or refuted.**

- **Mathematical language** establishes the meaning of a statement in a precise and unambiguous way. **Logic** defines the catalogue of inference rules that can used to draw conclusions from previous statements. **Therefore**, a proof lets us claim the conclusions with complete confidence.

- The goal of formal proofs is **to provide certainty about the validity of a statement through rigorous deduction.**

- Formal proofs are usually divided into three blocks: *preliminaries*, *problem statement* and *proof development*.

---

**Example 02**: **The** N**-Queens Problem** (adapted from Jimenez &Viladrosa)

This mathematical puzzle is a generalisation of the 8-Queens problem, initially proposed in 1848. This problem has gathered interest from mathematicians and computer scientists, and it is often used a benchmark for measuring the efficiency of theorem provers and constraint solvers.

- **Preliminaries**
  
  ​	Definition 1 (Queen): A queen is a chess piece that threatens any piece of the board located on the same row, column or diagonal.

  ​	Definition 2 (*N*-Queens): Given an empty *N* × *N*-chess board, is it possible to place *N* queens in such a way that no pair of queens threaten each other?
  
- **Problem statement**
  
  ​	Theorem 1 (Feasibility of *N*-Queens): The *N*-Queens problem has a solution for any *N* ≥ 4.
  
- **Proof development**

  ​	Proof: 

  ​			Let us consider the following algorithm for generating a solution to the *N*- Queens problem for an arbitrary *N*: . . . 

  ​			This algorithm ensures that there is no pair of queens on the same row and column, but we still have to make sure that there are no queens on the same diagonal. 

  ​			We prove this... $\square$

![Screen Shot 2021-11-19 at 11.16.04 AM](https://tva1.sinaimg.cn/large/008i3skNgy1gwkmmtb9iwj30ey0fqjtu.jpg)

---

### 2.1.3. Formal vs. Informal

**Question**： What is the most important lexical category of nature languages? Why?

- What is your statement and how to proof?

---

## 2.2. Why?



Formal proofs use **known facts and the deduction rules of logic** to reach conclusions. As proofs are based on logics and mathematics, the conclusion of a proof is completely certain. Thus, proofs can be used to confirm **hypothesis and conjectures** with complete assurance.

---

## 2.3. How?

There are different kinds of proof strategies, which can be applied in different kinds of situations. Here we will look at the following four proof strategies:

- (i) refutation by counterexample 
- (ii) direct proof
- (iii) indirect proof 
- (iv) inductive proof

---

### 2.3.1. Refutation by counterexample

To prove the falsety of a claim that some general law is true.

---

**Example 03**: The following claim is false. For any sets *X* and *Y*, if *X* ∈ *Y*, then all the elements of *X* are also elements of *Y*.

*Proof.* 

​			**Let** $X=\{a,b\},Y=\{c,d,X\}=\{c,d,\{a,b\}\}$

​			**Then** we can see $X ∈ Y$ and $a ∈ X$

​			**But** $a \notin Y $ $\square$

---

**Exercise 03**: If $X ∪ Y \ne \emptyset$, then $X ∩ Y\ne ∅$.

*Proof.* 

​			**Let** $X = \{a\}$ and $Y=\{b\}$

​			**Then** we can see $\{a\} ∪ \{b\} = \{a,b\}\ne ∅$,

​			**But** {*a*} ∩ {*b*} = ∅  $\square $

---

### 2.3.2. Direct proof

To show $p \to q$ is proved by showing that if $p$ is true then $q$ follows

---

**Example 04:** Prove that “If $n$ is odd, then $n^2$ is odd.”

*Proof.*

- ​		**Assume** the hypothesis is true, i.e. suppose $n$ is odd.

  ​		**Then** let $n=2k+1$,where $k$ is an integer.
  $$
  \begin{aligned}
  n^2 &=(2k+1)^2\\
   &=4k^2 +4k+1 \\&= 2(2k^2 + 2k) + 1
   \end{aligned}
  $$
  ​		**Therefore**, $n^2$ is odd. $\square $

---

**Exercise 04:** If $X∩Y \ne∅$, then$|X∪Y|>0$

*Proof.* 

---

### 2.3.3. Indirect proof

To show $p \to q$ prove its contrapositive $¬q \to ¬p$

Why? $p \to q$  and $¬q \to ¬p$ are equivalent!

Assume $¬q$ is true, show that $ ¬p$  is true.

---

**Example 05:** Prove If $3n + 2$ is odd then $n$ is odd. 

- *Proof.* 

  ​		**Assume $n$ is even**, that is $n = 2k$, where $k$ is an integer.

  ​		Then: 

$$
\begin{aligned}
 3n+2&=3(2k)+2\\
&= 6k + 2\\
&= 2(3k+1)
 \end{aligned}
$$
​			Therefore $3n + 2$ is even.

​			We proved **$¬$ “$n$ is odd”** $\to$ **$¬$ “ $3n + 2$ is odd”.**

​			This is equivalent to **“$3n + 2$ is odd”** $\to $ **“$n$ is odd”.** $\square$

---

**Exercise 05**: If $X ⊆ Y $ and $Y ⊆ X$, then $X = Y$.

- *Proof.*

  ​			Let us assume that X ⊆ Y and Y ⊆ X and also that $X \ne Y$.

  ​			assume that $X=\{a,b\}$ and $Y=\{a,c\}$

  ​			then $b\in X$ and $b \notin Y$, $X\nsubseteq Y$ 

  ​			and $c\in Y$ and $c \notin X$, $Y\nsubseteq X$ 

  ​			This is a contradiction to our initial assumption. $\square$

---

### 2.3.4. Inductive proof

[**Mathematical induction**](https://groups.seas.harvard.edu/courses/cs152/2018sp/lectures/lec03-inductive-proof.pdf): Three steps

1. the inductive base
2. the inductive assumption 
3. the inductive step.



Inductive proofs are often useful in connection with **recursive definitions**. Let us consider a very simple example first. We use the following recursive definition of a set $\mathscr{F}$ of (flowery) strings:

- Anchor: the symbol $“*”$ is part of $\mathscr{F}$

- Step:if *f* ∈ $\mathscr{F}$, then so is $“(x)”$

- Exhaustion: nothing else is in $\mathscr{F}$



The *inductive reasoning principle* of mathematical induction can be stated as follows:

For any property $P$ , 

​	**If**

​	• $P(0)$ holds
 	• For all natural numbers $n$, if $P (n)$ holds then $P (n + 1)$ holds

​	**then**

​	for all natural numbers $k$, $P (k)$ holds.

---

**Example 06** : The cardinality of the power set of finite set *X* is $|\mathscr{P} (X) | = 2^{|X|}$.

- *Proof.*  The inductive proof is over the cardinality of set *X*.

  ​		1. *Inductive base.* If |*X*| = 0, we know that *X* = ∅, so that $\mathscr{P} (X)$ = {∅}. 

  ​								The cardinality of {∅} is indeed $2^{| *X* |} = 2^0 = 1$ 

  ​		2. *Inductive assumption.* Assume that the claim is true for any set with cardinality of at most *n* > 0

  ​		3. *Inductive step.* We need to show that the claim is true for any set *X* with| *X* | = *n*, given the inductive assumption. 

  ​							Let *X* be an arbitrary set with |*X*| = *n*. 

  ​							Let *x* ∈ *X* and *Y* = *X* \ {*x*}. 

  ​							By inductive assumption, $|\mathscr{P} (Y) |$ = $2^{|Y|}$. The power set of *X* contains all sets in the power set of *Y*. It additionally also contains a version of each element in $\mathscr{P} (Y)$ that also contains *x*.But that means that the cardinality of P(*X*) is $|\mathscr{P} (Y) |$ = $2^{|Y|}$ = $2×2^{n−1}$ = 2*n*. 􏶖

  ---

  **Exercise 06** :  Show that a set of $n$ elements has $2^n$ subsets. (adopted from [Hildebrand 2013](https://faculty.math.illinois.edu/~hildebr/213/inductionsampler.pdf))

  *Proof.* We will prove by induction that, for all $n ∈ \mathbb{Z}_+$, the following holds: 

  ​			$P (n)$ 			Any set of n elements has $2^n$ subsets.

     1.    *Inductive base.*  Since any 1-element set has 2 subsets, namely the empty set and the set itself, and $2^1 = 2$, the statement $P(n)$ is true for n = 1. 

     2.    *Induction step:*

           ​		Let $k ∈ \mathbb{Z}_+$ be given and suppose $P (k)$ is true, i.e., that any $k$-element set has $2^k$ subsets. We seek to show that $P (k + 1)$ is true as well, i.e., that any $(k + 1)$-element set has $2^{k+1}$ subsets.

           ​		Let $A$ be a set with $(k+1)$ elements.

           ​		Let $a \in A$, and let $A′ =A−\{a\}$ (so that A′ is a set with $k$ elements).

           ​		We classify the subsets of $A$ into two types: 

           ​		(I) subsets that do not contain a, and (II) subsets that do contain a.

           ​		The subsets of type (I) are exactly the subsets of the set A′. Since A′ has $k$ elements, the induction hypothesis can be applied to this set and we get that there are $2^k$ subsets of type (I).

           ​		The subsets of type (II) are exactly the sets of the form $B = B′ ∪ \{a\}$, where $B' \subset A'$. By the induction hypothesis there are $2^k$ such sets $B′$, and hence $2^k$ subsets of type (II).

           ​		Since there are $2^k$ subsets of each of the two types, the total number of subsets of $A$ is $2^k + 2^k = 2^{k+1}$.

           ​		Since A was an arbitrary $(k + 1)$-element set, we have proved that any $(k + 1)$-element set

           has $2^{k+1}$ subsets. Thus $P (k + 1)$ is true, completing the induction step. 

           3. *Conclusion:* By the principle of induction, $P(n)$ is true for all $n ∈ \mathbb{Z}_+$ $\square$

           ---

           **Exercise 07:** Let's defined a simple formal language $\mathscr{L}$ recursively as the smallest set such that:

           1. all words for natural numbers, i.e.,“one”,“two”,..., are in $\mathscr{L}$ 

           2. if $x,y ∈ \mathscr{L}$, then so are the strings:

  ​											“*x* plus *y*” 								“*x* minus *y*”

  ​	Prove the following statement with an inductive proof strategy: No element of L is a string that contains the word “bread.”

---

### 2.3.5. Summary

**Planning formal proofs**

1. Identifying the problem 
2. Reviewing the literature
3. Identifying the premises
4. Understanding the problem
5. Formalising the problem
6. **Selecting a proof strategy** 
7. Developing the proof 
8. Reevaluating the proof
9. Improving readability



