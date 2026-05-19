---
layout: default
title: Ashby Ch 3 — The Determinate Machine
date: 2026-05-19
source: W. Ross Ashby, *An Introduction to Cybernetics* (Chapman & Hall, 1956), Chapter 3 — "The Determinate Machine", pp. 24–41. PDF at pespmc1.vub.ac.be/books/IntroCyb.pdf
mode: contrast
permalink: /cybernetics/ashby-ch3/
---

# Ashby Ch 3 — The Determinate Machine

*Contrast rewrite of W. Ross Ashby's "The Determinate Machine" (1956). The chapter opens with what looks like a confident definition of "machine" pointing outward at the world. It closes by inverting that definition: there is no machine out there, only a list of variables we chose to track. Source vocabulary preserved — determinate machine, state, operand, trajectory, canonical representation, closure, vector, phase space.*

[← Cybernetics index](/cybernetics/)

---

## What looks like a definition

A **determinate machine** is anything that behaves like a closed, single-valued transformation. That is the whole thing.

The definition refers to a way of behaving, not to a material object. Cybernetics studies determinateness — systems that follow regular, reproducible courses — not the matter underneath. A heavy iron frame holding beads on springs, released repeatedly from the same starting position, passes through the same succession of states each time. Each state is an **operand**. The sequence of states is a **trajectory**. The transformation that takes each state to the next is the machine's **canonical representation** — the machine is said to *embody* the transformation.

Other things that fit the same shape:

- A bacterial culture doubling each hour: *n*' = 2*n*.
- A clock's hands ticking forward: *n*' = *n* + *k*. Whatever drives it — mainspring, gravity, the elasticity of brass, the friction of oil — Ashby calls the **operator**, and dismisses it as arbitrary, poorly defined, of little scientific use. The transformation is what we have. The "what makes it go" is not.
- Lobar pneumonia, in the days before sulphonamides, passing through Infection → consolidation → red hepatisation → grey hepatisation → resolution → health. The states are not numbers. The transformation is still well-defined.
- A stickleback courtship dance: the male's zigzag releases the female's approach, which releases his swim-to-nest, which releases her follow, which releases his head-into-entrance, and so on through trembling, spawning, fertilising. Each reaction releases the next. A trajectory of biological states, every arrow proved by Tinbergen with dummy tests.

The general claim, after these examples: every determinate machine, real or imagined, can be put in correspondence with a closed single-valued transformation. The transformation is what science talks about. The operator is poorly defined. Science doesn't need it.

## Closure is not optional

The typical machine can always be allowed to run a little longer simply by leaving it alone. No particular limit exists to how far you can iterate. That means the transformation must allow itself to be raised to any power: *T*(*a*), *T*²(*a*), *T*³(*a*), and on without end. If any step lands on something for which *T* isn't defined, the machine has nowhere to go and the formalism collapses.

So: the transformation that represents a machine must be closed. This will keep coming back.

## Discrete is enough

Smooth-running machines look like a violation. Ashby answers in two moves.

First: take the discrete step small enough and it approximates continuity to any tolerance you want. The continuous case is a limit of the discrete one, recoverable later.

Second, and more pointed: real observation is always discrete. The "continuity" we attribute to natural events lives in the observer's imagination, not in the data. The natural system is observed at discrete points; our transformation represents it at discrete points; there is no contradiction to resolve.

(Discrete has an advantage continuous loses. Every property is unambiguously either present or absent. No subtlety, no vagueness. Deductions stay secure.)

## Vectors: when one number isn't enough

A ship isn't at a number — it's at a latitude *and* a longitude. Weather isn't a number — it's a barometer reading, a temperature, a cloudiness, a humidity. Compound states need compound notation.

A **vector** is a tuple (*a*₁, *a*₂, ..., *aₙ*) whose components together specify the state. The transformation operates on the vector as a whole, even though its definition usually describes how each component changes individually. Two vectors are equal only if every component matches. If one has different components from the other (numbers vs. letters, say) they aren't even comparable.

If two coins each show Head or Tail, the system has four vector-states: (*H,H*), (*H,T*), (*T,H*), (*T,T*). A child's preference — always rotate (*H,H*) to (*T,H*), with various other preferences for the rest — is a transformation on these four states, just as legitimately as any equation.

Notation falls out of this. If the operand is the vector (*a*, *b*, *c*), three **sub-transformations** specify the whole thing:

```
a' = b
b' = c
c' = b + c
```

Three lines, six symbols, all the dynamics. The whole project of mathematical physics — Newton's laws of motion, the canonical equations of any dynamic system — is to write these sub-transformation rules and read out the trajectory.

## Phase space: the algebra made visible

When the components of a vector are numbers, the vector becomes a point, and the transformation becomes an arrow from point to point. The plane filled with these arrows is the **phase space** of the system. Each starting point traces a trajectory by following arrows.

<div class="figure">
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 480 360" width="100%" style="max-width: 540px;">
  <style>
    .axis { stroke: #444; stroke-width: 1.5; fill: none; }
    .diag { stroke: #c33; stroke-width: 1.5; fill: none; stroke-dasharray: 4 4; }
    .arrow { stroke: #226; stroke-width: 1.2; fill: none; marker-end: url(#a3); }
    .pt { fill: #226; }
    .attractor { fill: #c33; stroke: #c33; }
    .label { font: 12px sans-serif; fill: #222; }
    .label-c { font: 11px sans-serif; fill: #c33; }
  </style>
  <defs>
    <marker id="a3" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M0,0 L10,5 L0,10 Z" fill="#226" />
    </marker>
  </defs>
  <!-- axes -->
  <line x1="40" y1="320" x2="440" y2="320" class="axis" />
  <line x1="40" y1="320" x2="40" y2="20" class="axis" />
  <text x="450" y="324" class="label">x</text>
  <text x="32" y="16" class="label">y</text>
  <!-- y=x diagonal -->
  <line x1="40" y1="320" x2="340" y2="20" class="diag" />
  <text x="346" y="24" class="label-c">y = x</text>
  <!-- arrows: each arrow at 45° up-left toward the diagonal -->
  <!-- (8,4) -> (6,6): start (200, 280), end (180, 240) -->
  <line x1="200" y1="280" x2="180" y2="240" class="arrow" />
  <circle cx="200" cy="280" r="3" class="pt" />
  <text x="208" y="285" class="label">(8,4)</text>
  <circle cx="180" cy="240" r="3" class="pt" />
  <text x="186" y="232" class="label">(6,6)</text>
  <!-- (10,2) -> (6,6) — same destination, different start -->
  <line x1="240" y1="300" x2="184" y2="244" class="arrow" />
  <circle cx="240" cy="300" r="3" class="pt" />
  <!-- (4,10) -> (7,7) -->
  <line x1="120" y1="220" x2="170" y2="190" class="arrow" />
  <circle cx="120" cy="220" r="3" class="pt" />
  <!-- (12,2) -> (7,7) -->
  <line x1="280" y1="300" x2="178" y2="195" class="arrow" />
  <circle cx="280" cy="300" r="3" class="pt" />
  <!-- (3,9) -> (6,6) -->
  <line x1="100" y1="240" x2="178" y2="248" class="arrow" />
  <circle cx="100" cy="240" r="3" class="pt" />
  <!-- (14,4) -> (9,9) -->
  <line x1="320" y1="280" x2="220" y2="180" class="arrow" />
  <circle cx="320" cy="280" r="3" class="pt" />
  <!-- (2,12) -> (7,7) -->
  <line x1="80" y1="200" x2="174" y2="194" class="arrow" />
  <circle cx="80" cy="200" r="3" class="pt" />
  <!-- accumulation labels on the line -->
  <circle cx="180" cy="240" r="4" class="attractor" />
  <circle cx="178" cy="194" r="4" class="attractor" />
  <text x="48" y="346" class="label">Phase space of x' = ½(x+y), y' = ½(x+y). Every point hops 45° toward the line y = x and stops.</text>
</svg>
</div>

The whole range of possible behaviours is now visible at once, frozen into a single display. Properties that would have taken pages of algebra to prove show up at a glance: where trajectories accumulate, which states are equilibria, whether basins exist. For three components you can still draw something. Beyond three, the diagram is notional, but the topological intuition often carries you farther than the equations would.

## The setup looks complete

The picture so far: machines exist in the world. Transformations live on paper. The canonical correspondence between them is what science does. Give us a machine, we read off a transformation. Give us a transformation and an initial state, we compute a trajectory. The trajectory is the prediction.

Then Ashby breaks it.

## The pendulum that won't behave

Suppose we have a real pendulum, forty centimetres long. We draw it aside to 30°, release it, record its position every quarter-second. We get 30° → 10° → –24°. Our first estimate of the transformation, under these conditions, is

```
ﬂ  30°   10°
   10°  –24°
```

Then, as good scientists, we check. We draw the pendulum to 10°, release it, and a quarter-second later it is at +3°. The transformation isn't single-valued. The pendulum is contradicting itself.

We cannot give up single-valuedness — to do so is to give up prediction. So one of our assumptions has to go.

## What was actually wrong

Our first impulse was to point at the pendulum and say "the system is *that thing there*." Every material object, though, contains an infinity of possible variables: length, position, mass, temperature, electrical conductivity, crystalline structure, chemical impurities, radioactivity, velocity, reflecting power, tensile strength, surface moisture, bacterial contamination, optical absorption, elasticity, shape, specific gravity, and on and on. We can't study them all. We never try.

What we do, in practice, is pick a list. We say: the system *consists of* these variables. With the pendulum, our first list was just one entry — angular deviation. That list didn't yield single-valuedness, so we extend it. We try (angular deviation, mass of bob) — still no. We try (angular deviation, angular velocity) — and singleness arrives.

The fix wasn't to look at the world more carefully. The fix was to redefine what counted as the system.

## The inversion

The system is not the thing. **The system is the list of variables we chose.**

Sometimes the discovery of the right list is monumental — Newton finding that you can't predict motion without momentum, or Gowland Hopkins finding that rats' behaviour on diets won't go single-valued until you include vitamins. Sometimes it is trivial — you tighten a loose screw, or remove an impurity from the water-supply. The mechanism varies. The pattern is identical: you change the variable list, and singleness either arrives or doesn't.

The earlier claim — *every* determinate dynamic system corresponds to a single-valued transformation — now reads differently. It is not a fact about the world. It is a fact about which subjects science admits as its objects of study. Systems that won't go single-valued are dismissed as "chaotic" or "non-sensical" and refused study.

> It is we who decide, ultimately, what we will accept as "machine-like" and what we will reject.

The chapter opened with a confident definition pointing outward at the world. It closes with the recognition that the definition was always pointing inward — at the observer's choice of where to draw the system's edges, which variables to admit, which to ignore.

## What carries forward

Three things from this chapter recur through the rest of the book:

- **The canonical representation** is the transformation, not the machinery. We talk about transformations and the machines we ascribe to them, never about "what's really going on inside."
- **Closure is mandatory.** A transformation that can't be raised to arbitrary powers can't represent a machine.
- **Choosing the variables IS doing the science.** Picking the wrong list, and watching your transformation fail to be single-valued, is the signal that you have not yet identified a system.

The rest of cybernetics is built on these three.

---

[← Cybernetics index](/cybernetics/)
