---
layout: default
title: Ashby Ch 2 — Change
date: 2026-05-18
source: W. Ross Ashby, *An Introduction to Cybernetics* (Chapman & Hall, 1956), Chapter 2 — "Change", pp. 9–23. PDF at pespmc1.vub.ac.be/books/IntroCyb.pdf
mode: linear-cumulative
permalink: /cybernetics/ashby-ch2/
---

# Ashby Ch 2 — Change

*Linear-cumulative rewrite of W. Ross Ashby's "Change" (1956). Definitions stack; each section builds on the previous one. The chapter ends by visualizing what the algebra hid — basins of attraction in the dynamics of repeated change. Source PDF at [pespmc1.vub.ac.be](https://pespmc1.vub.ac.be/books/IntroCyb.pdf).*

---

## Difference, finite

Cybernetics' most fundamental concept is **difference**: either two things are recognizably distinct, or one thing has changed over time. Every chapter in the book leans on this. Plants growing, planets aging, machines moving — they're all change from one state to another.

A choice has to be made up front: continuous change (infinitesimals, calculus) or discrete change (finite jumps, counting). Ashby picks discrete. Money in a bank account doesn't change by less than a penny. Every important question about a finite-step system can be decided by simple counting — so you can always be sure you're right. The continuous case can be recovered later as a limit, once the discrete case is firmly understood. Nothing is lost.

## The vocabulary of a single change

Pale skin under sunshine darkens. Something acted on (pale skin), a factor acting (sunshine), what it became (dark skin). Three words for the three roles:

- **operand** — what gets acted on
- **operator** — what acts
- **transform** — what the operand becomes

The change itself, written

> pale skin → dark skin

is the **transition**. Specify a transition by naming the two states and which became which. That's the whole apparatus for one change.

## Transformation: a set of transitions

A single transition is too thin to be useful. Sunshine doesn't only darken skin — it also warms cold soil, exposes photographic plates, bleaches pigment. The operator "exposure to sunshine" induces a whole *set* of transitions, one for each operand it can act on.

That set is a **transformation**. Another example: the Caesar shift that turns each letter into the next one in the alphabet (Z wrapping back to A), so CAT becomes DBU. Written as a table:

```
A → B
B → C
…
Y → Z
Z → A
```

Crucially, a transformation is defined by *what* it does — the table of operand-to-transform pairs — not by *why* the change happens. We may know something about the physical operator (we know things about sunlight), but that knowledge isn't essential. What we must know is the transformation it effects. Cybernetics describes systems by their input-output table, not their inner workings. This is the move that lets the same machinery handle skin, plates, codes, and chess positions in one breath.

## Closure: when transforms stay inside

Apply a transformation to its operands. Look at the set of transforms. If every transform is already in the set of operands — if no new element was created — the set is **closed** under the transformation.

The Caesar shift is closed: every letter goes to a letter. "Multiply by 2 on the operands {1,2,3,4}" is *not* closed — it produces 8, which isn't in the original set.

Closure is a property of the pair (transformation, operand set), not of either alone. Change the operands or change the rule and closure may flip. And — keeping faith with the previous section — closure is checked from the table itself, not from anything we know about the underlying cause.

This matters more than it looks. Closure is the condition under which a transformation can be applied *again* to its own output. An unclosed transformation takes one step and then jams.

## Three flavors of single-valuedness

A transformation is **single-valued** if each operand maps to exactly one transform. (Multi-valued transformations exist and matter later, in stochastic and incompletely-specified systems.)

Inside single-valued, two sub-cases:

- **one-one**: every transform is also distinct from every other. The transformation has an inverse — given the transform, you can recover the unique operand. The Caesar shift is one-one.
- **many-one**: at least two operands collapse to the same transform. Information about which operand it was is destroyed. Most real-world transformations are many-one.

A special case: the **identity transformation**, where every transform equals its operand. Nothing changes. Necessarily one-one if the operands are distinct. In compressed notation: *n′ = n*.

## Compression: notation that scales

Writing every transition out by hand gets unwieldy. The notation collapses:

- Add a prime to the operand to mean its transform. So "*n* goes to *n* + 3" becomes *n′ = n + 3*, with the operand set noted separately.
- Or, name the transformation *T* and write *T(n)* for the transform of *n*. The double application is *T(T(n))*, usually shortened to *T*²(*n*).

A second representation, useful later: the **matrix**. Operands across the top, possible transforms down the left, a + at the intersection where one becomes the other, 0 elsewhere. The matrix view makes structure visible (rows of zeros mean a state never gets produced; columns of zeros aren't possible for closed transformations) that the table form hides.

Different notations, same content. The matrix becomes load-bearing in later chapters on Markov chains and probabilistic transformations.

## Power: closure makes repetition possible

A closed single-valued transformation can be applied again to its own output. Apply Alpha (the Caesar shift) twice: A becomes B, B becomes C; net effect A → C. Applied across the alphabet, the double application is itself a transformation — the **square**, *T*². Triple application is *T*³, the **cube**. Higher powers similarly.

Finding *T*² doesn't require rewriting the whole table. There's an algebraic shortcut, **elimination**. Given *T*: *n′ = n + 1*, the second application is *n″ = n′ + 1*. Substitute: *n″ = (n + 1) + 1 = n + 2*. So *T*²: *m′ = m + 2*. The notation change from *n* to *m* is cosmetic — just to keep operand and transform from getting confused.

A subtler example: *T*: *n′ = 2n − 3*. Then *n″ = 2n′ − 3 = 2(2n − 3) − 3 = 4n − 9*. So *T*²: *m′ = 4m − 9*. Three applications: *n‴ = 2n″ − 3 = 2(4n − 9) − 3 = 8n − 21*. So *T*³: *m′ = 8m − 21*.

Repeat the trick to get any power. The cybernetic point: closure is what makes the question "what does the system do after many steps?" even askable. Without closure the question is malformed — the machine jams.

## Product: combining different transformations

Two different transformations, applied in sequence, also yield a transformation. Apply *T* to *b*, get *T(b)*. Apply *U* to that, get *U(T(b))*. This composed transformation is the **product**, written *UT* (read right-to-left: *T* first, then *U*).

Order matters. *UT* and *TU* are generally different transformations. Composing skin-darkening with photographic exposure in one order is not the composition in the other order. This non-commutativity is structural — it shows up everywhere a system has multiple regulators or layered controls. Two interventions applied in opposite orders can produce different outcomes from the same starting state.

The product *UT* may not even exist: if some transform produced by *T* isn't in *U*'s operand set, the composition is undefined at that point. Same closure principle, generalized to two transformations.

## Kinematic graph: dynamics made visible

So far everything has been algebraic — tables, formulas, matrices. The final move of the chapter is visual, and it changes what you can see.

Take a closed transformation. Draw each operand as a node. Draw an arrow from *A* to *B* if and only if *A* → *B* in one step. The picture is the **kinematic graph**.

Example. Take

```
U: A B C D E
   D A E D D
```

Apply *U* to *C*: get *E*. Apply again: *E* → *D*. Apply again: *D* → *D*. The series is *C, E, D, D, D, …* — *D* forever. Apply *U* to *A*: *A, D, D, D, …* — same fate. Drawn as a graph:

```
C → E → D ← A ← B
```

with *D* having an implicit self-loop. Every starting state in this graph eventually arrives at *D* and stays there.

That property — every starting state eventually arrives at one specific resting state — is invisible in the original table. It's instantly visible in the graph. Now consider a more complex transformation:

<div style="margin: 2em 0; text-align: center;">
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 720 320" width="100%" style="max-width: 720px;">
  <style>
    .node { fill: #f4f0e8; stroke: #333; stroke-width: 1.5; }
    .attractor { fill: #d8c8a0; stroke: #333; stroke-width: 2; }
    .label { font-family: Georgia, serif; font-size: 14px; text-anchor: middle; dominant-baseline: central; fill: #222; }
    .arrow { stroke: #555; stroke-width: 1.3; fill: none; marker-end: url(#arrowhead); }
    .basin-label { font-family: Georgia, serif; font-size: 12px; font-style: italic; fill: #777; text-anchor: middle; }
  </style>
  <defs>
    <marker id="arrowhead" markerWidth="8" markerHeight="8" refX="7" refY="3" orient="auto">
      <polygon points="0 0, 8 3, 0 6" fill="#555" />
    </marker>
  </defs>

  <!-- Basin 1: Fixed point H -->
  <text x="120" y="30" class="basin-label">Basin 1: fixed point</text>
  <circle cx="60" cy="80" r="18" class="node" />
  <text x="60" y="80" class="label">M</text>
  <circle cx="120" cy="80" r="18" class="node" />
  <text x="120" y="80" class="label">B</text>
  <circle cx="180" cy="80" r="20" class="attractor" />
  <text x="180" y="80" class="label">H</text>
  <path d="M 78 80 L 102 80" class="arrow" />
  <path d="M 138 80 L 160 80" class="arrow" />
  <path d="M 195 70 A 14 14 0 1 1 195 90" class="arrow" />

  <!-- Basin 2: 3-cycle A→D→I→A -->
  <text x="380" y="30" class="basin-label">Basin 2: 3-cycle</text>
  <circle cx="290" cy="80" r="18" class="node" />
  <text x="290" y="80" class="label">L</text>
  <circle cx="350" cy="80" r="18" class="node" />
  <text x="350" y="80" class="label">P</text>
  <circle cx="290" cy="140" r="18" class="node" />
  <text x="290" y="140" class="label">C</text>
  <circle cx="350" cy="140" r="20" class="attractor" />
  <text x="350" y="140" class="label">N</text>
  <circle cx="420" cy="140" r="20" class="attractor" />
  <text x="420" y="140" class="label">A</text>
  <circle cx="490" cy="100" r="20" class="attractor" />
  <text x="490" y="100" class="label">D</text>
  <circle cx="490" cy="180" r="20" class="attractor" />
  <text x="490" y="180" class="label">I</text>
  <path d="M 290 98 L 290 122" class="arrow" />
  <path d="M 350 98 L 350 122" class="arrow" />
  <path d="M 308 140 L 332 140" class="arrow" />
  <path d="M 368 140 L 402 140" class="arrow" />
  <path d="M 438 132 L 478 108" class="arrow" />
  <path d="M 490 120 L 490 162" class="arrow" />
  <path d="M 478 172 L 438 148" class="arrow" />

  <!-- Basin 3: 2-cycle E↔Q -->
  <text x="620" y="30" class="basin-label">Basin 3: 2-cycle</text>
  <circle cx="560" cy="80" r="18" class="node" />
  <text x="560" y="80" class="label">J</text>
  <circle cx="620" cy="80" r="18" class="node" />
  <text x="620" y="80" class="label">K</text>
  <circle cx="560" cy="220" r="18" class="node" />
  <text x="560" y="220" class="label">F</text>
  <circle cx="620" cy="220" r="18" class="node" />
  <text x="620" y="220" class="label">G</text>
  <circle cx="600" cy="150" r="20" class="attractor" />
  <text x="600" y="150" class="label">E</text>
  <circle cx="680" cy="150" r="20" class="attractor" />
  <text x="680" y="150" class="label">Q</text>
  <path d="M 568 96 L 590 132" class="arrow" />
  <path d="M 614 98 L 605 130" class="arrow" />
  <path d="M 570 205 L 590 168" class="arrow" />
  <path d="M 620 202 L 668 165" class="arrow" />
  <path d="M 620 150 L 660 150" class="arrow" />
  <path d="M 680 168 L 620 152" class="arrow" />

  <text x="360" y="305" class="basin-label">Sixteen operands, three basins. Shading marks the attractor — the part the system can't escape.</text>
</svg>
</div>

The graph fragments into three components. Some chains end at states that loop back to themselves (the fixed point *H*). Some end at cycles of two or more states that the system circulates through indefinitely (the 3-cycle *A→D→I→A* and the 2-cycle *E↔Q*). Each connected component is a **basin**: the set of starting states that all drain into one attractor. The image is a watershed map. Drop a representative point anywhere on the country, and the basins tell you which sea it ends up in.

This is the chapter's payoff. The algebraic vocabulary — operand, transform, closure, power, product — was built so we could *describe* repeated change precisely. The kinematic graph reveals what the algebra is describing: dynamics have shape. Some shapes funnel everything toward fixed points. Some trap states in cycles. Some have multiple basins that never communicate.

The word for whether a basin's endpoint is reached and stayed at — and what makes some endpoints "endpoints" rather than transients — is **stability**. That's Chapter 5.

---

[← Cybernetics index](/cybernetics/)
