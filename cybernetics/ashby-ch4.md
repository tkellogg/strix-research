---
layout: default
title: Ashby Ch 4 — The Machine With Input
date: 2026-05-20
source: W. Ross Ashby, *An Introduction to Cybernetics* (Chapman & Hall, 1956), Chapter 4 — "The Machine With Input", pp. 42–71. PDF at pespmc1.vub.ac.be/books/IntroCyb.pdf
mode: chiasm
permalink: /cybernetics/ashby-ch4/
---

# Ashby Ch 4 — The Machine With Input

*Chiastic rewrite of W. Ross Ashby's "The Machine With Input" (1956). The chapter opens with a crane operator turning a switch — a machine controlled from outside via its parameters. By the middle it dismantles "feedback" as a useful organising concept for any system with more than a few parts. By the end the "input" picture has inverted entirely: in a system too large for the observer to specify, what determines the system's history is no longer what is fed in but which local properties self-lock or breed. Source vocabulary preserved — parameter, transducer, transient, coupling, immediate effect, diagram of immediate effects, reducibility, self-locking, breeding properties.*

[← Cybernetics index](/cybernetics/)

---

## What you can turn from the outside

In the previous chapter the machine was a unit — a single closed, single-valued transformation taking each state to the next. A real machine, though, is usually one that something can be done *to*. A crane is controlled by its driver. A muscle is controlled by its nerve. The boy dismantling a toy and rebuilding it as a different toy. Same parts, different machine.

To account for this, Ashby extends the apparatus. Just as the states of a machine change, the machine's *transformations* can change. If three transformations *R*₁, *R*₂, *R*₃ act on the same operands, a switch can pick which one is in force. The switch position is the **parameter**.

The distinction is fundamental and on no account is to be slighted:

- A state changing to another state — the machine **behaving** — happens under the machine's internal drive.
- A transformation changing to another transformation — the machine's **way of behaving** changes — happens at the whim of the experimenter, or some outside factor.

A real machine whose behaviour can be represented by such a set of closed single-valued transformations is a **transducer**, or, *machine with input*. The set of transformations is its canonical representation. The parameter, as something that can vary, is its input.

Algebraically: write *R*₁ as *n'* = *n* + 1, *R*₂ as *n'* = *n* + 2, *R*₃ as *n'* = *n* + 3, and collapse them into *R*ₐ: *n'* = *n* + *a*. Here *n* is the operand — what the transformation changes. *a* is the parameter — what selects the transformation. They look alike on the page; they do completely different jobs in the formalism. *a* must be specified before *n* can change.

## What "input" actually means

For an electrical box, input is obvious: a few terminals. For an organism, it isn't. The parameters of the organism are not a few labelled wires; they are co-extensive with **"all variables whose change directly affects the organism."** Light, food, temperature, social signal, every nutrient gradient, every alarm in the environment. The reader must be prepared to interpret "input" as either the few parameters of a simple mechanism or the many parameters of a free-living organism in a complex world. The rigour of the argument does not depend on the number being small.

This already moves the chapter quietly away from the engineer's intuition. The engineer studies a system by perturbing its input incessantly — sweeping frequencies, observing responses. The biologist often sets the conditions once and watches what unfolds. Both are legitimate. The response of the machine after some disturbance, with input subsequently held constant, is the **transient**: the sequence of states produced before the sequence starts repeating itself. A clinical pneumonia is a transient. The whole "complex sequence of events at the ants' nest" — for the cyberneticist, that too is a transient.

## Coupling, properly defined

Two machines can be joined. To couple them is not to weld their innards together — that is what happens when two cars are *coupled* by an accident, and they are too much changed by the process to count as the same machines afterward. **The coupling that interests cybernetics is one that does no violence to each machine's inner working, so that after coupling each machine is still the same machine it was before.** The way to achieve this is to couple input to output. The parameter of one machine is set as a function of the state of the other. Inner workings stay sovereign; the channel is at the boundary.

Concretely: P has output i, j, k; R has parameter *a*. A specification *Z* says "when P is at i, set *a* = 2; when at j, *a* = 3; when at k, *a* = 2." That is the coupling. The two machines, made to share a time-scale, now form a single new machine whose state is the vector (P's state, R's state) and whose behaviour is fully determinate from the parts and the rule *Z*.

If P affects R but R does not affect P, P is said to **dominate** R — the action is one-way. If each affects the other, the loop closes.

A consequence Ashby will return to often: **defining the parts does not determine the whole.** Two identical pairs of machines coupled differently produce different new machines. The behaviour of the whole becomes determinate only when the coupling is also specified.

## The bombshell

When the parts affect each other reciprocally — when each affects the other — *feedback may be said to be present*. This is the definition Ashby is going to use, and almost immediately he is going to tell us why it doesn't matter very much.

> *"In fact, there need be no dispute, for the exact definition of 'feedback' is nowhere important. The fact is that the concept of 'feedback', so simple and natural in certain elementary cases, becomes artificial and of little use when the interconnexions between the parts become more complex."*

Mathematicians want "feedback" to mean reciprocal influence in the equations. Practical engineers want a visible wire, a deliberate connexion of effect back from R to P. The mathematician's definition would force them to say the ordinary pendulum exhibits "feedback" between its position and its momentum — which they find mystical. The engineer's definition leaves the theory chaotic and riddled with irrelevancies. Ashby refuses to arbitrate and tells us why arbitration would be pointless.

Then the move that, for a 1956 cybernetics textbook, is genuinely shocking. With four parts, each affecting the other three, you can trace **twenty** circuits through the system. And:

> *"Knowing the properties of all the twenty circuits does not give complete information about the system. Such complex systems cannot be treated as an interlaced set of more or less independent feedback circuits, but only as a whole."*

> *"For understanding the general principles of dynamic systems, therefore, the concept of feedback is inadequate in itself. What is important is that complex systems, richly cross-connected internally, have complex behaviours, and that these behaviours can be goal-seeking in complex patterns."*

This is the chapter's hinge. The popular picture of cybernetics — the science of feedback loops — gets dismissed by the canonical text, in passing, in a paragraph. Feedback is fine for two parts. It is **inadequate in itself** as the organising concept of the field. The rest of the book is about what replaces it: variety, regulation, the diagram of immediate effects, requisite-variety bounds, the Black Box. Not loops drawn on a whiteboard.

## What an "effect" actually is

Having demoted feedback, Ashby has to give a sharper account of what "X has an effect on Y" means. The test is operational: hold all other variables fixed at some pair of states differing only in X; if Y's transition is the same, X has no immediate effect on Y. If it differs, X does.

It is the same test the visitor uses on the strange room with the wall of switches. Try one. Does the light change? It is also the same test the experimenter has been using all along, made explicit:

> *"The result is deduced directly from the system's observed behaviour, and depends only on what the system does, not on why it does it."*

Draw an arrow from X to Y if and only if X has an immediate effect on Y. The resulting picture is the **diagram of immediate effects**. The arrow has a precise meaning: a channel of communication runs from X to Y. (This will come back as the formal statement in Ch 8.) Where two immediate-effect arrows join head to tail, an *ultimate* effect runs the full length; the diagram of ultimate effects is the transitive closure. If X has no ultimate effect on Y, Y is **independent** of X.

A system can be **reducible** — its diagram of immediate effects falls into disconnected pieces, and the apparent "whole" is in fact two systems that share nothing. The concept of reducibility is structural, not statistical, and it will matter in Ch 13.

Ashby tucks one delight into this section: a charming letter from "Graveside, Wit's End, Haunts," in which the householder describes a haunted house tormented by ghostly Singing and sardonic Laughter, governed by exact laws of incense and organ-playing, and begs the reader to determine the manipulations needed to quiet the place. It is an exercise in deducing the diagram of immediate effects from a verbal protocol. It is also a demonstration that the apparatus does not depend on terrestrial physics — what matters in cybernetics is "the extent to which the observed behaviour is regular and reproducible," not the substrate.

## The pivot

Up to here the chapter has built an apparatus for analysing coupled machines whose parameters and states are fully specifiable. Now Ashby turns the page.

> *"Cybernetics, however, looks forward to being able to handle systems of vastly greater complexity — computing machines, nervous systems, societies."*

A system is **very large**, in Ashby's sense, if the observer cannot completely specify, observe, control, or predict it with the resources at his disposal. Not large in mass. Large in distinctions. The number of particles in a jar of gas. The number of genes in the stock-breeder's herd. The number of neurons in the cortex — Lashley reminding us that "every nerve cell in the cerebral cortex may be excited in every activity"; von Neumann counting 10¹⁰ neurons in a central nervous system and noting "we have absolutely no past experience with systems of this degree of complexity."

Size by itself doesn't invalidate the apparatus. The theorems stay true. **What changes is their applicability** — what the observer can actually do with them when full specification is impossible.

## Specifying what you can't fully specify

If you cannot enumerate the parts and their couplings individually, you must specify them by rules — each rule applying to many parts — and supplement the specification with a sampling procedure. "Couple them at random" is *not enough*. Random with replacement is a different network from random without. Allowing output to be wired to output is a different network from requiring input-to-output. The sampling rule is part of the specification. Without it, "random" is just hand-waving.

This is the surprise: it is, in a sense, possible for an observer to specify a system that is too large for him to specify. He specifies broadly, then delegates the detail to a source other than himself — a deck of cards, a random-number table, a coin. The particular final system is selected by the supplementary process, not by him. The statistical machine is not one machine; it is a *set* of machines drawn from a distribution.

## When the network thins itself

In a fully cross-coupled large system every variable would have an immediate effect on every other — n² − n arrows. The other extreme is total independence — no arrows. Real systems sit between, and they slide along the range by two mechanisms:

1. Fewer immediate effects in the diagram (sparser coupling at the design level).
2. **Thresholds** — variables that fail to vary because their input never exceeds some bound. A variable holding still has no immediate effect on anything else, and nothing has an immediate effect on it. Threshold effectively *removes its arrows*.

So a "rising threshold" in a network, or equivalently a rising fraction of constant variables, cuts the system functionally into smaller and smaller sub-systems. The same physical network, under a higher threshold, behaves as if it had been chopped apart.

<figure style="margin: 2rem 0;">
<svg viewBox="0 0 720 260" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Three diagrams of immediate effects under rising threshold. Left: a fully active 4x4 grid where every node has arrows to its neighbors. Middle: 30 percent of nodes have gone constant (shown grey) and their arrows are gone, leaving smaller connected sub-graphs. Right: 50 percent constant, leaving isolated pairs and singletons.">
<style>
.lbl { font: 12px sans-serif; fill: #555; text-anchor: middle; }
.title { font: 600 13px sans-serif; fill: #222; text-anchor: middle; }
.node-on { fill: #1f4f8b; }
.node-off { fill: #d0d0d0; }
.edge-on { stroke: #1f4f8b; stroke-width: 1.2; opacity: 0.55; }
</style>
<!-- Panel 1: fully active -->
<g transform="translate(20,20)">
  <text class="title" x="100" y="-4">low threshold</text>
  <g>
    <!-- 4x4 grid -->
    <g class="edge-on">
      <line x1="20" y1="20" x2="60" y2="20"/>
      <line x1="60" y1="20" x2="100" y2="20"/>
      <line x1="100" y1="20" x2="140" y2="20"/>
      <line x1="140" y1="20" x2="180" y2="20"/>
      <line x1="20" y1="60" x2="60" y2="60"/>
      <line x1="60" y1="60" x2="100" y2="60"/>
      <line x1="100" y1="60" x2="140" y2="60"/>
      <line x1="140" y1="60" x2="180" y2="60"/>
      <line x1="20" y1="100" x2="60" y2="100"/>
      <line x1="60" y1="100" x2="100" y2="100"/>
      <line x1="100" y1="100" x2="140" y2="100"/>
      <line x1="140" y1="100" x2="180" y2="100"/>
      <line x1="20" y1="140" x2="60" y2="140"/>
      <line x1="60" y1="140" x2="100" y2="140"/>
      <line x1="100" y1="140" x2="140" y2="140"/>
      <line x1="140" y1="140" x2="180" y2="140"/>
      <line x1="20" y1="180" x2="60" y2="180"/>
      <line x1="60" y1="180" x2="100" y2="180"/>
      <line x1="100" y1="180" x2="140" y2="180"/>
      <line x1="140" y1="180" x2="180" y2="180"/>
      <line x1="20" y1="20" x2="20" y2="60"/>
      <line x1="20" y1="60" x2="20" y2="100"/>
      <line x1="20" y1="100" x2="20" y2="140"/>
      <line x1="20" y1="140" x2="20" y2="180"/>
      <line x1="60" y1="20" x2="60" y2="60"/>
      <line x1="60" y1="60" x2="60" y2="100"/>
      <line x1="60" y1="100" x2="60" y2="140"/>
      <line x1="60" y1="140" x2="60" y2="180"/>
      <line x1="100" y1="20" x2="100" y2="60"/>
      <line x1="100" y1="60" x2="100" y2="100"/>
      <line x1="100" y1="100" x2="100" y2="140"/>
      <line x1="100" y1="140" x2="100" y2="180"/>
      <line x1="140" y1="20" x2="140" y2="60"/>
      <line x1="140" y1="60" x2="140" y2="100"/>
      <line x1="140" y1="100" x2="140" y2="140"/>
      <line x1="140" y1="140" x2="140" y2="180"/>
      <line x1="180" y1="20" x2="180" y2="60"/>
      <line x1="180" y1="60" x2="180" y2="100"/>
      <line x1="180" y1="100" x2="180" y2="140"/>
      <line x1="180" y1="140" x2="180" y2="180"/>
    </g>
    <g>
      <circle cx="20" cy="20" r="4" class="node-on"/>
      <circle cx="60" cy="20" r="4" class="node-on"/>
      <circle cx="100" cy="20" r="4" class="node-on"/>
      <circle cx="140" cy="20" r="4" class="node-on"/>
      <circle cx="180" cy="20" r="4" class="node-on"/>
      <circle cx="20" cy="60" r="4" class="node-on"/>
      <circle cx="60" cy="60" r="4" class="node-on"/>
      <circle cx="100" cy="60" r="4" class="node-on"/>
      <circle cx="140" cy="60" r="4" class="node-on"/>
      <circle cx="180" cy="60" r="4" class="node-on"/>
      <circle cx="20" cy="100" r="4" class="node-on"/>
      <circle cx="60" cy="100" r="4" class="node-on"/>
      <circle cx="100" cy="100" r="4" class="node-on"/>
      <circle cx="140" cy="100" r="4" class="node-on"/>
      <circle cx="180" cy="100" r="4" class="node-on"/>
      <circle cx="20" cy="140" r="4" class="node-on"/>
      <circle cx="60" cy="140" r="4" class="node-on"/>
      <circle cx="100" cy="140" r="4" class="node-on"/>
      <circle cx="140" cy="140" r="4" class="node-on"/>
      <circle cx="180" cy="140" r="4" class="node-on"/>
      <circle cx="20" cy="180" r="4" class="node-on"/>
      <circle cx="60" cy="180" r="4" class="node-on"/>
      <circle cx="100" cy="180" r="4" class="node-on"/>
      <circle cx="140" cy="180" r="4" class="node-on"/>
      <circle cx="180" cy="180" r="4" class="node-on"/>
    </g>
  </g>
  <text class="lbl" x="100" y="218">whole system reacts</text>
</g>
<!-- Panel 2: 30 percent constant -->
<g transform="translate(260,20)">
  <text class="title" x="100" y="-4">rising threshold</text>
  <g class="edge-on">
    <line x1="60" y1="20" x2="100" y2="20"/>
    <line x1="100" y1="20" x2="140" y2="20"/>
    <line x1="60" y1="60" x2="100" y2="60"/>
    <line x1="100" y1="100" x2="140" y2="100"/>
    <line x1="140" y1="100" x2="180" y2="100"/>
    <line x1="20" y1="140" x2="60" y2="140"/>
    <line x1="60" y1="140" x2="100" y2="140"/>
    <line x1="140" y1="140" x2="180" y2="140"/>
    <line x1="20" y1="180" x2="60" y2="180"/>
    <line x1="140" y1="180" x2="180" y2="180"/>
    <line x1="60" y1="20" x2="60" y2="60"/>
    <line x1="100" y1="20" x2="100" y2="60"/>
    <line x1="100" y1="100" x2="100" y2="140"/>
    <line x1="140" y1="100" x2="140" y2="140"/>
    <line x1="140" y1="140" x2="140" y2="180"/>
    <line x1="180" y1="100" x2="180" y2="140"/>
    <line x1="180" y1="140" x2="180" y2="180"/>
    <line x1="20" y1="140" x2="20" y2="180"/>
  </g>
  <g>
    <circle cx="20" cy="20" r="4" class="node-off"/>
    <circle cx="60" cy="20" r="4" class="node-on"/>
    <circle cx="100" cy="20" r="4" class="node-on"/>
    <circle cx="140" cy="20" r="4" class="node-on"/>
    <circle cx="180" cy="20" r="4" class="node-off"/>
    <circle cx="20" cy="60" r="4" class="node-off"/>
    <circle cx="60" cy="60" r="4" class="node-on"/>
    <circle cx="100" cy="60" r="4" class="node-on"/>
    <circle cx="140" cy="60" r="4" class="node-off"/>
    <circle cx="180" cy="60" r="4" class="node-off"/>
    <circle cx="20" cy="100" r="4" class="node-off"/>
    <circle cx="60" cy="100" r="4" class="node-off"/>
    <circle cx="100" cy="100" r="4" class="node-on"/>
    <circle cx="140" cy="100" r="4" class="node-on"/>
    <circle cx="180" cy="100" r="4" class="node-on"/>
    <circle cx="20" cy="140" r="4" class="node-on"/>
    <circle cx="60" cy="140" r="4" class="node-on"/>
    <circle cx="100" cy="140" r="4" class="node-on"/>
    <circle cx="140" cy="140" r="4" class="node-on"/>
    <circle cx="180" cy="140" r="4" class="node-on"/>
    <circle cx="20" cy="180" r="4" class="node-on"/>
    <circle cx="60" cy="180" r="4" class="node-on"/>
    <circle cx="100" cy="180" r="4" class="node-off"/>
    <circle cx="140" cy="180" r="4" class="node-on"/>
    <circle cx="180" cy="180" r="4" class="node-on"/>
  </g>
  <text class="lbl" x="100" y="218">sub-systems emerge</text>
</g>
<!-- Panel 3: 50 percent constant -->
<g transform="translate(500,20)">
  <text class="title" x="100" y="-4">high threshold</text>
  <g class="edge-on">
    <line x1="60" y1="20" x2="100" y2="20"/>
    <line x1="140" y1="60" x2="180" y2="60"/>
    <line x1="60" y1="100" x2="60" y2="140"/>
    <line x1="100" y1="140" x2="140" y2="140"/>
    <line x1="20" y1="180" x2="20" y2="140"/>
    <line x1="180" y1="100" x2="180" y2="140"/>
  </g>
  <g>
    <circle cx="20" cy="20" r="4" class="node-off"/>
    <circle cx="60" cy="20" r="4" class="node-on"/>
    <circle cx="100" cy="20" r="4" class="node-on"/>
    <circle cx="140" cy="20" r="4" class="node-off"/>
    <circle cx="180" cy="20" r="4" class="node-off"/>
    <circle cx="20" cy="60" r="4" class="node-off"/>
    <circle cx="60" cy="60" r="4" class="node-off"/>
    <circle cx="100" cy="60" r="4" class="node-off"/>
    <circle cx="140" cy="60" r="4" class="node-on"/>
    <circle cx="180" cy="60" r="4" class="node-on"/>
    <circle cx="20" cy="100" r="4" class="node-off"/>
    <circle cx="60" cy="100" r="4" class="node-on"/>
    <circle cx="100" cy="100" r="4" class="node-off"/>
    <circle cx="140" cy="100" r="4" class="node-off"/>
    <circle cx="180" cy="100" r="4" class="node-on"/>
    <circle cx="20" cy="140" r="4" class="node-on"/>
    <circle cx="60" cy="140" r="4" class="node-on"/>
    <circle cx="100" cy="140" r="4" class="node-on"/>
    <circle cx="140" cy="140" r="4" class="node-on"/>
    <circle cx="180" cy="140" r="4" class="node-on"/>
    <circle cx="20" cy="180" r="4" class="node-on"/>
    <circle cx="60" cy="180" r="4" class="node-off"/>
    <circle cx="100" cy="180" r="4" class="node-off"/>
    <circle cx="140" cy="180" r="4" class="node-off"/>
    <circle cx="180" cy="180" r="4" class="node-off"/>
  </g>
  <text class="lbl" x="100" y="218">isolated pairs and singletons</text>
</g>
</svg>
<figcaption style="font: 12px sans-serif; color: #666; text-align: center; margin-top: 0.5rem;">Diagram of immediate effects under rising threshold. As more variables sit constant (grey), the same physical network functionally fragments into smaller and smaller sub-systems. After Ashby's Fig. 4/20/1.</figcaption>
</figure>

The point is not the picture itself but what it allows: a continuous parameter — "height of threshold," "proportion of variables constant" — that varies the wholeness of the system from totally joined to totally unjoined. Wholeness becomes a *statistical degree*, not a structural fact. And what the observer can know about that degree, he can know without specifying any individual coupling.

## Local properties

In a sparsely-coupled, repetitive system, a property of interest may exist *locally* — at some few variables — without that determining whether it also exists in another, distant clump. Contrast a test tube of silver nitrate with a thermostat. In the test tube the property "Ag and Cl coupled as AgCl" exists over and over again in independent instances throughout the solution; one such pairing has no effect on the great majority of others. In the thermostat there is no such repeatability — every property at any point is decisive for what happens at every other point.

The next two sections name the two local properties that are about to dominate the rest of the chapter.

## Self-locking

Some properties, once developed at a part, become inaccessible to whatever would undo them. A colony of oysters: each oyster receives the danger signal and shuts. But once shut, it cannot receive the safety signal that would re-open it. Were these the only forces at work, the colony would pass entirely into the closed state. A solution of reacting molecules where one product is insoluble: each molecule reaching that form falls out of solution and out of further reaction; the system depletes irreversibly in that direction. Workers in an unpleasant industry, finding pleasanter employment during a layoff, who will pass readily from the unpleasant to the pleasant but refuse to pass back.

> *"In general, therefore, changes that are self-locking are usually of high importance in determining the eventual state of the system."*

Self-locking at the part-level becomes one-way monotone at the system level. If *n* counts how many parts have the property, the transformation obeys *n'* ≥ *n*. The system has a ratchet.

## Breeding

The other case. The existence of the property at one place changes — usually raises — the probability that the property will exist, one time-step later, at another place. A trail of gunpowder along a line, on fire at the fourth inch, will probably be on fire at the third and fifth one moment later. An attractive car sold into one house raises the chance it will be sold to adjacent houses. A scarce food source: one member of a starving species lowers the chance of survival for the next.

When this can be summarised as *n'* = *k* *n*, with *k* positive and independent of *n*, the history of the population of parts-with-the-property depends sharply on whether *k* is above or below 1.

- ***k* < 1.** The property fades. The number of radium atoms in pitchblende. The population of a species sliding into extinction.
- ***k* = 1.** Population constant. Dissociation at equilibrium. Knife-edge — any deviation drops it into one of the other two regimes.
- ***k* > 1.** The property "breeds." The system is potentially explosive — *"either dramatically, as in an atom bomb, or insidiously, as in a growing epidemic."* Autocatalysis. Combustion. Fashion. Avalanches. Rabbits.

And then the line that pays for the chapter:

> *"It is at this point that the majestic development of life by Darwinian evolution shows its relation to the theory developed here of dynamic systems. The biological world... is a system with something like the homogeneity and the fewness of immediate effects considered in this chapter. In the early days of the world there were various properties with various k's. Some had k less than 1 — they disappeared steadily. Some had k equal to 1 — they would have remained. And there were some with k greater than 1 — they developed like an avalanche, came into conflict with one another, commenced the interaction we call 'competition', and generated a process that dominated all other events in the world and that still goes on."*

That is the chiasm closing. The chapter opened with a crane operator turning a switch — a parameter set from outside, deliberately, to select one of a few transformations. It closes with autocatalysis, gunpowder, evolution: no operator, no switch, no input from outside the system at all. The locus of what determines the system's history has migrated from external control through coupling to local properties of self-locking and breeding. The "input" picture has inverted.

## What carries forward

Four things from this chapter recur:

- **Parameter ≠ variable.** State changes happen under the machine's internal drive; transformation changes happen at the whim of something outside. Conflating the two is fatal to the formalism.
- **Coupling is binding input to output, leaving inner workings alone.** Defining the parts does not determine the whole. The coupling specification is part of the system specification.
- **Feedback is not the central concept of cybernetics.** Beyond a handful of parts, the system must be treated as a whole. The diagram of immediate effects, variety, and regulation will do the work feedback is too thin to do.
- **In very large systems, what matters is local: self-locking and breeding.** The history of the system is determined by which monotone ratchets and which *k* > 1 processes it contains, not by external input. This is the framing Ch 11 (Requisite Variety) and Ch 12 (Error-Controlled Regulator) will live inside.

---

[← Cybernetics index](/cybernetics/)
