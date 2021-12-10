# ![unnamed](https://tva1.sinaimg.cn/large/008i3skNgy1gx8bkv875wj30e8021aac.jpg)

# Kuan's Logic Tutorial 05

2021.12.10

![Screen Shot 2021-11-16 at 5.14.13 AM](https://tva1.sinaimg.cn/large/008i3skNgy1gx8bkx6vzpj31g20lqn2a.jpg)

[toc]

---

**Review exercises of Tutorial  04:** 

---

# 5. Propositional Logic II

**Key points:** 

- Translations & logical validity

---

## 5.1. Logical structure of meaning

- What is meaning?
  - *Semantic meaning*: The literal meaning is the context-independent logical core meaning. 
  - *Pragmatic meaning*: Pragmatic enrichments arise in context by taking into account general world knowledge or the reasons why a speaker used language in the way that they did.


### 5.1.1. *Conjunction*

- Logical conjunction is order-insensitive: $φ ∧ ψ$ and $ψ ∧ φ$ are logically equivalent
  - *They got married and had children.*
  - *They had children and got married.*

### 5.1.2. *Disjunction*

- Logical disjunction is *inclusive*: $φ ∨ ψ$ is true when $φ$ and $ψ$ are both true.
  - *She owns a Porsche or a Ferrari.*
  - *She owns a Porsche or a Ferrari and possibly both.*
  - *She owns* either *a Porsche or a Ferrari and possibly both.*

### 5.1.3. *Conditional perfection*

- Many natural language conditionals receive a so-called *conditional perfection reading*
  - i.e., “if and only if (iff)” statement which would correspond to logical operator $↔$, even though their logical meaning might just be that of a simple implication $→$
  - *If Bubu comes, Kiki comes.*
  - *If Bubu comes, Kiki comes, and maybe Kiki comes no matter what.*
  - *Kiki comes only if Bubu comes, and maybe Kiki comes not matter what.*

### 5.1.4. *Excavating the logical structure*

- The logical relation between propositions contained in a natural language sentence may sometimes be opaque.
  - *If drawing a red card means that I lost, I lost.*
    - $p$: I drew a red card. 				
    - $q$: I lost.
    - $(p → q) → q$

---

**Exercise 01:** For each of the following sentences give the translation key and the (propositional) logical form.

1. Either John is in that room or Mary is, and possibly they both are.
2. The fire was set by an arsonist, or there was an accidental explosion in the boiler room.
3. When it rains, it pours.
4. Sam wants a dog, but Alice prefers cats.
5. If Steve comes home late and has not had any supper, we will reheat the stew.
6. Clarence is well educated only if he can read Chuvash.
7. Marsha won't go out with John unless he shaves off his beard and stops drinking.
8. The stock market advances when public confidence in the economy is rising and only then.
9. A necessary but perhaps not sufficient condition for negotiations to commence is for Barataria to cease all acts of aggression against Titipu.

---

## 5.2. *Valuation functions, possible worlds* & *logical entailment*

### 5.2.1. Valuation functions

- The proper definition of the **semantics of PropLog** is therefore formulated in terms of so-called **valuation functions**.
- A *valuation function V* is a function that assigns to every formula of propositional logic a unique truth value (0 or 1).

<img src="https://tva1.sinaimg.cn/large/008i3skNgy1gx8yqfbdh5j30iu08agmc.jpg" alt="poplogic valuation" style="zoom:60%;" />

### 5.2.2. Possible worlds

- A possible world is a way in which things could be. 
- A possible world conforms to the rules of logic, but otherwise allows all atomic propositions to be different from the facts in the *actual world*.
- $[[φ]]$ = $\{V | V$ is a valuation function such that $V(φ) = 1\}$

### 5.2.3. *Tautologies, contradictions, contingencies* & *equivalence*

- $φ$ is a tautology iff $V(φ) = 1$ for all valuation functions $V$.
- $φ$ is a contradiction iff $V(φ) = 0$ for all valuation functions $V$. 
- $φ$ is a contingency iff there is at least one valuation function $V_1$ such that $V_1(φ) = 1$ and there is at least one valuation function $V_2$ such that $V_2(φ) = 0$. 
- $φ$ and $ψ$ are logically equivalent, iff for all valuation functions $V(φ) = V(ψ)$.

### 5.2.4. *Logical entailment* & *informativity*

- Logical entailment: Formula $φ$ logically entails $ψ$ iff for all valuation functions $V$, if $V(φ) = 1$, then $V(ψ) = 1$. 
  - An alternative formulation is this: $φ$ logically entails $ψ$ iff $[[φ]]⊆ [[ψ]]$.
  -  We say that φ is at least as informative as ψ iff $[[φ⊆ ψ]]$, and that $φ$ is strictly more informative than $ψ$ iff $[[φ⊂ ψ]]$.

---

**Exercise 02**: Let $p$, $q$ and $r$ be atomic statements. Which of the following are tautologies, contradictions or contingent statements?

1. $(p \or \neg p)$

2. $(p\or q)$

3. $((p\and q)\to(p\and r))$

4. $(\neg p \and \neg (p\to q))$

5. $(p \or r)\to \neg p)$

   ---

   ### 5.2.5. *Argument schemas* & *validity*

- We defined **logical validity** of so-called **argument schemas.** 
- If $φ1 , φ2 , . . . , φn$ and $ψ$ are forumlas of PropLog, then $φ1,φ2,...,φn/ψ$ is an argument schema.
  - Formulas $φ1,φ2,...,φn$ are the **premisses**, formula $ψ$ is the **conclusion**.
- The argument schema $φ1, φ2, . . . , φn/ψ$ is valid **iff** 
  - For all valuation functions $V$ such that $V(φ1) = V(φ2) = ··· = V(φn) = 1$ it also holds that *V*(ψ) = 1. If valid, we write $φ1,φ2,...,φn \models ψ$.
  - The bitwise OR assignment operator ( $\models $ ) uses the **binary representation of both operands**, does a bitwise OR operation on them and assigns the result to the variable.

---

**Example**: Consider the argument schema: $p ∨ q, ¬q / p$. 

A natural language analogue would be the following. We know or assume the following **premisses**:

- *The murderer is the butler or the gardener.* 

- *The gardener is not the murderer.*

And the **putative** conclusion is: 

- *The butler is the murderer.*

Truth table for checking the validity of argument schema:

<img src="https://tva1.sinaimg.cn/large/008i3skNgy1gx8yvqgbpqj30cw07edfu.jpg" alt="truth table checking" style="zoom:67%;" />

In terms of (types of) possible worlds, so that we can conveniently say that a possible world like $w_6$ in which $p$ and $r$ are false and $q$ is true is a counterexample to validity: **both premises are true, but the conclusion is false.**

<img src="https://tva1.sinaimg.cn/large/008i3skNgy1gx8yzdy47gj30z60cojsk.jpg" alt="method" style="zoom:67%;" />

---

### 5.2.6. *Theorems of propositional logic*

- If $φ$ is a tautology, then $¬φ$ is a contradiction.
- If $φ → ψ$ is a tautology iff $φ$ logically entails $ψ$.

---

**Exercise 03.** Let $p$, $q$ and $T$ be true and let $s$ be false. Find the truth values of the following statements.

1. $(p\and (q \and s))$
2. $s\to p$
3. $(p \to (q \leftrightarrow (T \to s)))$

---

**Exercise 04.** Express the following arguments in symbolic form, and determine whether they are valid.

*The butler or the cook or the chauffeur killed the baron. If the cook killed the baron, then the stew was poisoned, and if the chauffeur killed the baron, there was a bomb in the car. The stew wasn't poisoned, and the butler didn't kill the baron. Therefore, the chauffeur killed the baron.*

