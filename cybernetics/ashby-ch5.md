---
layout: default
title: "Ashby Ch 5 — Stability"
date: 2026-05-19
permalink: /cybernetics/ashby-ch5/
---

# Stability

> *Bellman called it "that much overburdened word with an unstabilised definition."*

Ashby refuses to fix a better terminology. He fixes the **facts** instead, then lets the words point at them. We'll do the same.

The chapter builds in one direction: from a single unchanging point, outward through cycles, sets, displacements, and finally to the homeostat — where stability is no longer a property of the parts but a **veto** exchanged between them.

---

## Invariant

Under every meaning of "stability" sits one idea: *something does not change while everything else does*.

Tilt a cube 5° and let it go. The state "tilt = 1°" is true at one moment, false the next. But the state **"tilt ≤ 6°"** stays true forever. That bound is invariant for the system.

Tilt a cone on its point, the same 5°. The bound "tilt ≤ 6°" is falsified within an instant, and so is any wider bound. The system's states cannot be put inside any finite region along the trajectory. That is **instability**.

**Stability is the existence of an invariant bound. Instability is the failure to find one.**

---

## State of equilibrium

The simplest invariant: a state the transformation leaves alone.

$$T(x) = x$$

Algebraically, find the fixed points. For

$$T:\begin{cases} x' = 2x - y + 2 \\ y' = x + y + 3 \end{cases}$$

set $(x', y') = (x, y)$ and solve. One equilibrium: $(-3, -1)$.

For differential systems, the condition is $dx/dt = 0$ on every component. In

$$dx/dt = 2x - y^2, \quad dy/dt = xy - 1/2$$

the state $(1/2, 1)$ is equilibrial — every derivative vanishes; the system stops moving.

Equilibrium is the point form of stability — invariance at a single state, defined entirely by the algebra, with no reference yet to *neighbours* or *disturbances*.

---

## Cycle

Equilibrium generalises to a set that the transformation walks through and returns from.

If
$$T:\begin{array}{c|cccccccc} & a & b & c & d & e & f & g & h \\ \hline & c & h & b & h & a & c & c & g \end{array}$$

then starting from $a$: $a \to c \to b \to h \to g \to c \to b \to h \to g \to \ldots$

The representative point repeatedly traverses

$$c \to b \to h \to g \to c$$

Equilibrium is a cycle of length 1.

---

## Stable set (closure)

Step up again. Drop the requirement that the transformation visit the states in any order — just that it never leave the set.

Take an unclosed $T$ that has *no* equilibrium and *no* cycle. But the subset $\{b, g\}$ has the property

$$T:\begin{array}{c|cc} & b & g \\ \hline & g & b \end{array}$$

$T$ on this set produces no new state. The set is **stable with respect to $T$**.

This is the same relation Ashby called **closure** in Ch 2. The new word "stable set" is the same fact dressed for a new purpose: only on a stable set can $T$ be applied to all its powers without escaping. Only what is closed under change can survive change.

**A set is stable iff the transformation cannot leave it.**

---

## Disturbance

So far, every notion has been *local to the algebra*. None has asked: *what if something nudges the system?*

A disturbance is just a second transformation. Let $T$ be the system's law, $a$ a state of equilibrium, $D$ a displacement-operator. Apply $D$ once, then iterate $T$:

$$D(a), \; TD(a), \; T^2D(a), \; T^3D(a), \; \ldots$$

If this sequence converges back to $a$:

$$\lim_{n \to \infty} T^n D(a) = a$$

then $a$ is **stable under displacement $D$**.

The three textbook cases, now in one frame:

- **Cube on its face.** $D$ tilts it 5°. $T$ (gravity) brings it back to 0°. Stable.
- **Cone on its point.** Same $D$. $T$ takes it anywhere but 0°. **Unstable.**
- **Billiard ball on a table.** $D$ moves it. $T$ neither restores nor amplifies. Limit is $D(a)$, not $a$. **Neutral.**

Asking what happens after displacement is only worth asking *if $a$ was equilibrial to start with*.

---

## The disturbance matters

A pencil on its square-cut base is stable to a 1° push and unstable to a 5° push. Same pencil, same $T$ — different $D$ gives a different answer.

So "stable" without a specified $D$ is shorthand. When we say a radio circuit is stable, we mean *to the voltage fluctuations one expects* — not to a lightning strike. The shorthand works because $D$ is conventional. In biology, where the conventions are not shared, $D$ has to be made explicit or the discussion has no content.

**A system is stable to a range of disturbances, not in itself.**

---

## Continuous systems and the small disturbance

In real systems, small disturbances act incessantly: thermal noise on circuits, vibration on mechanics, biological flutter on cells. Only states that are stable in the sense above can actually persist. Unstable equilibria exist in theory but get washed out by the perpetual jiggle.

For continuous systems, $D$ usually adds small numerical amounts to the components:

$$(x_1, \ldots, x_n) \to (x_1 + d_1, \ldots, x_n + d_n)$$

Specialised tests for stability (eigenvalues, Lyapunov functions) become available here. The general method — trace $D(a), TD(a), T^2D(a), \ldots$ and watch the limit — is laborious but always works. The specialised tests are faster but apply only to linear, continuous cases. In biological material, the general method is often the only one that applies at all.

---

## Feedback and the false shortcut

A familiar special case: the system is a single loop. The shortcut: track a small displacement around the loop. If it comes back diminished, the feedback is **negative** and the system is (commonly) stable.

The shortcut is useful but **unreliable in the presence of complication**. Consider

$$x' = \tfrac{1}{2}y, \quad y' = \tfrac{1}{2}x$$

From $(10, 12)$: an increase in $y$ from 10 to 12 produces an increase in $x$ from 5 to 6. From $(12, 10)$: an increase in $x$ produces an increase in $y$. Each variable has a positive effect on the other. By the shortcut, the loop is **positive feedback** and the system should diverge.

It doesn't. Iterating from any state, the system converges to $(0, 0)$. It is **stable around the origin**, despite the loop being algebraically positive.

The shortcut confuses local sign with global behaviour. *Feedback* is a useful concept inside the range it was made for and unsuitable outside it. Stability is more general than feedback, and the algebraic test (iterate and watch) is more reliable than the loop-sign heuristic.

**Positive feedback does not imply instability. Negative feedback does not imply stability. The iteration tells you.**

---

## Undesirable stability

Stability is praised as if it were a virtue. It is not — it's a structural property, and structural properties are neutral to value.

- **Petrol on fire.** Once lit, the burning state is stable. Disturb it (half-extinguish it) and it returns to fully lit. A fireman finds this stability extremely undesirable.
- **Population IQ.** If the more intelligent reproduce less than the less intelligent, IQ falls. But the very low cannot reproduce at all, so the floor is around 90. Stability at 90. Not a goal — a basin.
- **Causalgia.** A partially severed nerve forms a regenerative circuit at the injury site, motor impulses feeding back into sensory. The circuit has **two stable equilibria** — minimal conduction (comfortable) and maximal conduction (severe pain). A top-heavy see-saw that rests at either extreme. The patient knows from the inside that stability can be good or bad.

Goal-seeking behaviour is stable behaviour around an equilibrium. So is addiction, so is a lit fire, so is the painful state of an injured nerve. The structure is the same; the value depends on which state the basin contains.

---

## Equilibrium in the part and the whole

Now Ashby lifts the topic from individual systems to **coupled** ones — and stability becomes a property of agreement between parts.

Couple two systems, $A \leftrightarrow B$, and suppose the whole is at equilibrium. The whole's state is a vector $(s_A, s_B)$. If the whole is unchanging, both components are unchanging.

$A$'s input is determined by $B$'s state, which is fixed. So $A$ is in equilibrium **under the conditions $B$ is providing**. Symmetrically for $B$.

Reverse it: if $A$ is equilibrial under conditions from $B$, and $B$ is equilibrial under conditions from $A$, then neither moves and the whole is equilibrial.

**The whole is at equilibrium iff each part is at equilibrium in the conditions the others provide.**

This is more powerful than it looks. It turns equilibrium of a coupled system into a joint condition — a fixed point in *each part's behaviour space conditional on the other*. The whole cannot rest unless every part can rest *given what the other is doing*.

---

## Power of veto

Stated dynamically: trajectories of the coupled whole pass through many joint states. At some moment $B$'s state happens to make $A$'s current state equilibrial — $A$ wants to stop. But $B$ may not be in equilibrium under $A$'s state. $B$ moves. $B$'s move changes $A$'s input. $A$'s equilibrium points shift. $A$ starts moving again.

*$A$ proposed an equilibrium. $B$ vetoed it.*

**Each part of a coupled system has, in effect, a power of veto over the states of equilibrium of the whole. No state of the whole is equilibrial unless every part accepts it in the conditions given by the rest.**

This is the chapter's deepest move. Stability of a coupled system is not a property of any part — it is the **intersection of the rest-states** of every part. The system can rest only where everybody can rest at once. Most joint states fail this test. The few that pass it are what we observe as "settled" behaviour.

---

## The homeostat

The veto principle makes the homeostat readable.

The homeostat is two coupled parts: $A$ (four needles with coils, potentiometers, mutually interacting) and $B$ (a relay plus four 25-position stepping switches — 781,250 internal states).

- $B$ has been wired so that **with the relay energised**, *no* state of $B$ is equilibrial — the switches keep stepping.
- $B$ has been wired so that **with the relay not energised**, *every* state of $B$ is equilibrial — the switches stop.
- $B$ has been coupled to $A$ so that the relay is **un-energised when and only when $A$'s needles are at or near centre**.

Set the homeostat a problem (change an input to $A$). The combined system runs. By the veto principle, the whole can rest only where $B$ rests — i.e., only where the relay is un-energised — i.e., only where $A$'s needles sit near the centre.

$B$ **vetoes every equilibrium of $A$ except the centred ones.**

Every diagram in *Design for a Brain* reduces to one sentence: "trajectory of a system running to a state of equilibrium." The homeostat does nothing more than that. The interest is in how much intricate physiological and psychological behaviour fits inside that one sentence.

---

## Summing up — stability is compound

The stack:

1. **Equilibrium** — a state unchanged by $T$.
2. **Cycle** — a set $T$ walks around.
3. **Stable set / closure** — a region $T$ cannot leave.
4. **Stable under disturbance $D$** — $\lim T^n D(a) = a$.
5. **Stable to a range of $D$** — every disturbance in the range returns.
6. **Stable when coupled** — every part's equilibrium accepted by every other part.

You can't apply "stability" unambiguously until you've named which level you're at and, for the last three, which $D$ or which coupling. The word is shorthand. When the shorthand confuses, delete it and write the actual states, transformations, and trajectories instead.

The chapter ends with a foreshadow: asking what a complex system "will do" can be answered fully (every detail of its trajectory) or topologically ("it will return to its usual state" / "it will diverge ever further"). Stability is the topological answer — the first non-trivial thing one can say about a very large system without naming every variable. This is why the concept survives the imprecision: it is the simplest property that scales.

---

*Structure choice — linear-cumulative. Ashby genuinely builds: each stability concept extends the previous one. The chapter's final move (veto / homeostat) is the payoff of the construction, not a frame inversion.*

*What was cut: the algebraic exercises (Ex. 1–11 in §5/3, the kinematic-graph exercises, the bus-spacing exercise, the train question), the apologetic preamble about "today's terminology is unsatisfactory", the reference forward-pointers to §S.9/6 etc.*

*What was kept: every defined term (invariant, equilibrium, cycle, stable set, displacement, stable under D, neutral, undesirable stability, veto, homeostat), every example (cube/cone/billiard-ball, lit petrol, causalgia, IQ floor, homeostat), every algebraic case (linear two-variable, the differential system, the "positive feedback that converges" surprise), the explicit recovery of "closure" as the same fact under a new name, and the closing topological foreshadow.*

*What was added: the load-bearing one-liner at each level — "Stability is the existence of an invariant bound", "A set is stable iff the transformation cannot leave it", "A system is stable to a range of disturbances, not in itself", "Positive feedback does not imply instability", "The whole is at equilibrium iff each part is at equilibrium in the conditions the others provide". These compress what Ashby spreads over a paragraph each.*
