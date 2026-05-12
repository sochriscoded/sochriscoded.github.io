+++
draft          = true
title          = "Propositional Logic — The Grammar of Reasoning"
episode_number = 3
description    = "."
youtube_url    = ""
exercises      = []
resources      = []
tags = ["the-joy-of-mathematical-thinking"]
+++

---

# Episode 3: Propositional Logic — The Grammar of Reasoning

## Episode Goal

The viewer should understand the five basic logical connectives (NOT, AND, OR, IF...THEN, IF AND ONLY IF), be able to construct and read truth tables, and understand that compound statements' truth values are completely determined by the truth values of their components.

## Cold Open (2 minutes)

Present a logic puzzle:

> On an island, every person is either a knight (always tells the truth) or a knave (always lies). You meet two people, A and B.
>
> A says: "At least one of us is a knave."
>
> What are A and B?

Walk through the reasoning:
- If A is a knave, then A is lying, so it's false that at least one of them is a knave, meaning both are knights — but then A is a knight, contradiction.
- So A must be a knight, telling the truth: at least one of them is a knave. Since A is a knight, B must be the knave.

This puzzle requires no mathematical knowledge — just careful logical reasoning. That reasoning can be made *systematic* with the tools this episode introduces.

## Main Content

### Segment 1: Negation (NOT) (3 minutes)

If $P$ is a statement, then $\lnot P$ ("not $P$") is the statement that is true when $P$ is false, and false when $P$ is true.

| $P$ | $\lnot P$ |
|-----|-----------|
| T | F |
| F | T |

**Examples:**
- $P$: "$7$ is prime." (True.) $\lnot P$: "$7$ is not prime." (False.)
- $P$: "$4$ is odd." (False.) $\lnot P$: "$4$ is not odd." (True.)

**Key point:** Negation is not about "opposites" in the colloquial sense. The negation of "all cats are black" is *not* "no cats are black" — it's "there exists a cat that is not black." (This foreshadows the quantifier negation rules in Episode 6.)

### Manim Animation Candidate: Truth Value Toggle

Animate a simple switch (like a light switch or a digital toggle). When $P$ is "on" (true), $\lnot P$ is "off" (false), and vice versa. Simple, but it establishes the visual language for truth values that will be used in all subsequent truth table animations.

### Segment 2: Conjunction (AND) (4 minutes)

If $P$ and $Q$ are statements, then $P \land Q$ ("$P$ and $Q$") is true only when *both* $P$ and $Q$ are true.

| $P$ | $Q$ | $P \land Q$ |
|-----|-----|-------------|
| T | T | T |
| T | F | F |
| F | T | F |
| F | F | F |

**Examples:**
- "$2$ is even and $3$ is odd." — True ($T \land T = T$).
- "$2$ is even and $4$ is odd." — False ($T \land F = F$).
- "Paris is in Germany and Tokyo is in Brazil." — False ($F \land F = F$).

**Connection to programming:** `if (x > 0 && x < 10)` — the body executes only when *both* conditions are true. This is conjunction. Viewers with programming experience already use this connective constantly.

**Connection to circuits:** An AND gate outputs 1 only when both inputs are 1. (Brief mention — don't belabor the circuit connection, but plant the seed for Episode 31.)

### Segment 3: Disjunction (OR) (4 minutes)

$P \lor Q$ ("$P$ or $Q$") is true when *at least one* of $P$ or $Q$ is true.

| $P$ | $Q$ | $P \lor Q$ |
|-----|-----|------------|
| T | T | T |
| T | F | T |
| F | T | T |
| F | F | F |

**Critical point: inclusive vs. exclusive OR.** In everyday English, "or" is often exclusive: "Would you like coffee or tea?" usually means "pick one." In mathematics (and in this series), OR is always *inclusive*: $P \lor Q$ is true when both $P$ and $Q$ are true.

Exclusive or ($P \oplus Q$, or $P$ XOR $Q$) is true when exactly one of $P$ and $Q$ is true. It can be defined as $(P \lor Q) \land \lnot(P \land Q)$. Mention it here but clarify that when we write "or" in this series, we always mean inclusive or.

**Example to work through:**

"A number $n$ is interesting if $n$ is prime or $n$ is a perfect square."

Is $4$ interesting? Yes: $4$ is not prime, but $4$ is a perfect square. ($F \lor T = T$.)

Is $2$ interesting? Yes: $2$ is prime and $2$ is not a perfect square. ($T \lor F = T$.)

Is $9$ interesting? Yes: $9$ is not prime, but $9$ is a perfect square. ($F \lor T = T$.) (Note: $9 = 3^2$.)

Is $6$ interesting? No: $6$ is not prime and $6$ is not a perfect square. ($F \lor F = F$.)

### Segment 4: Conditional (IF...THEN) (6 minutes)

$P \rightarrow Q$ ("if $P$ then $Q$") is false only when $P$ is true and $Q$ is false.

| $P$ | $Q$ | $P \rightarrow Q$ |
|-----|-----|--------------------|
| T | T | T |
| T | F | F |
| F | T | T |
| F | F | T |

**This is the hard one.** The first two rows are intuitive: if the hypothesis is true and the conclusion follows, the implication is true; if the hypothesis is true and the conclusion doesn't follow, the implication is false.

The last two rows — where $P$ is false — are what confuse people. "If pigs can fly, then $2 + 2 = 5$" is *true* in logic, because the hypothesis is false. This feels wrong to most people. Address this directly.

**Why the convention works:** Think of an implication as a *promise*. "If it rains, I will bring an umbrella." When does this promise get broken? Only when it rains and I *don't* bring an umbrella ($P$ true, $Q$ false). If it doesn't rain, I haven't broken my promise regardless of what I do with the umbrella. A promise with a false hypothesis is *vacuously satisfied* — not broken.

**Mark this as a concept that will get its own episode.** Episode 4 is entirely about implication and its subtleties. Here, just introduce the truth table and the promise analogy, and tell the viewer: "This one is important enough that we're going to spend a whole episode on it next time."

### Segment 5: Biconditional (IF AND ONLY IF) (3 minutes)

$P \leftrightarrow Q$ ("$P$ if and only if $Q$," often written "$P$ iff $Q$") is true when $P$ and $Q$ have the *same* truth value.

| $P$ | $Q$ | $P \leftrightarrow Q$ |
|-----|-----|------------------------|
| T | T | T |
| T | F | F |
| F | T | F |
| F | F | T |

**Key point:** $P \leftrightarrow Q$ means two things simultaneously: "$P \rightarrow Q$" and "$Q \rightarrow P$." It asserts that $P$ and $Q$ are logically equivalent — they're true in exactly the same situations.

**Example:** "A triangle is equilateral if and only if all three of its angles are $60°$." This is a single statement that packages two claims: (1) if a triangle is equilateral, then all angles are $60°$, and (2) if all angles are $60°$, then the triangle is equilateral.

In mathematical theorems, "if and only if" signals the strongest kind of relationship: necessary *and* sufficient.

### Segment 6: Building and Reading Truth Tables (5 minutes)

Show how to build truth tables for compound statements with more than two connectives. Work through a concrete example:

**Example:** Determine the truth table for $\lnot(P \land Q) \leftrightarrow (\lnot P \lor \lnot Q)$.

| $P$ | $Q$ | $P \land Q$ | $\lnot(P \land Q)$ | $\lnot P$ | $\lnot Q$ | $\lnot P \lor \lnot Q$ | $\lnot(P \land Q) \leftrightarrow (\lnot P \lor \lnot Q)$ |
|-----|-----|-------------|---------------------|-----------|-----------|------------------------|------------------------------------------------------------|
| T | T | T | F | F | F | F | T |
| T | F | F | T | F | T | T | T |
| F | T | F | T | T | F | T | T |
| F | F | F | T | T | T | T | T |

The biconditional is true in every row. This means $\lnot(P \land Q)$ and $\lnot P \lor \lnot Q$ are *logically equivalent* — they're different expressions of the same logical content. This is **De Morgan's Law** (one of two). Name it, but emphasize that the truth table *proves* it — we don't need to take it on faith.

### Manim Animation Candidate: Truth Table Construction

Animate the truth table being filled in column by column, left to right. Start with the input columns ($P$, $Q$), then compute each intermediate column, highlighting which cells are being used at each step. Use color coding: green for T, red for F. When the final column is complete, if it's all T (a tautology), flash it with a special highlight and label it.

### Manim Animation Candidate: De Morgan's Laws — Visual Circuit

Show two circuits — one for $\lnot(P \land Q)$ and one for $\lnot P \lor \lnot Q$. Animate the same inputs being fed to both circuits and show they always produce the same output. Then morph one circuit into the other, visually demonstrating the equivalence.

## Example Problems for On-Screen Demonstration

### Problem 1: Knight and Knave Extensions

Return to the island of knights and knaves:

> You meet three people: A, B, and C.
>
> A says: "All of us are knaves."
> B says: "Exactly one of us is a knight."
>
> What are A, B, and C?

**Solution:**
- If A is a knight, A tells the truth, so all three are knaves — but then A is a knave. Contradiction. So A is a knave.
- Since A is a knave, A's statement is false: it's not the case that all three are knaves, so at least one of B, C is a knight.
- If B is a knight, B tells the truth: exactly one is a knight. That one must be B (since A is a knave). So C is a knave. Check: A (knave) said "all knaves" — false ✓. B (knight) said "exactly one knight" — true (only B) ✓. Consistent.
- If B is a knave, B's statement is false: the number of knights is not exactly one. Since A is a knave, and at least one of B, C is a knight, and B is a knave, C must be a knight. But then there's exactly one knight (C), making B's statement true — contradiction (B is a knave).

So A is a knave, B is a knight, C is a knave.

**Why this problem is good here:** It exercises conjunction, disjunction, negation, and case analysis. It also demonstrates that systematic logical reasoning can solve problems that feel hopelessly tangled at first.

### Problem 2: De Morgan in Action

Use De Morgan's Laws to simplify: $\lnot((\lnot P \land Q) \lor (P \land \lnot Q))$.

Step by step:
1. Apply De Morgan to the outer $\lor$: $\lnot(\lnot P \land Q) \land \lnot(P \land \lnot Q)$.
2. Apply De Morgan to each inner $\land$: $(P \lor \lnot Q) \land (\lnot P \lor Q)$.
3. This is actually $P \leftrightarrow Q$ — the biconditional. (The original expression was $\lnot(P \oplus Q)$.)

This problem connects De Morgan's Laws, XOR, and the biconditional, showing how logical identities interrelate.

### Problem 3: Evaluate Without a Full Truth Table

Determine the truth value of the following, given $P$ is true, $Q$ is false, and $R$ is true:

$$((P \lor Q) \land (Q \rightarrow R)) \rightarrow (P \land R)$$

Work from the inside out:
- $P \lor Q = T \lor F = T$
- $Q \rightarrow R = F \rightarrow T = T$
- $(P \lor Q) \land (Q \rightarrow R) = T \land T = T$
- $P \land R = T \land T = T$
- $T \rightarrow T = T$

Result: True. (Then ask: is this *always* true, or just true for these specific values? A full truth table or logical argument would be needed to check all 8 combinations of $P$, $Q$, $R$.)

## Closing (1–2 minutes)

Recap the five connectives and their truth tables. Emphasize that these aren't arbitrary rules — they're formalizations of how reasoning works. "And" means both, "or" means at least one, "not" means the opposite, "if...then" means the hypothesis can't be true without the conclusion. Next episode: a deep dive into the conditional, because "if...then" is where most logical mistakes happen.

---

