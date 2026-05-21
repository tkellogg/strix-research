---
layout: default
title: Ashby Design for a Brain — The Ultrastable System (Homeostat)
date: 2026-05-21
source: W. Ross Ashby, *Design for a Brain* (Chapman & Hall, 1952), Chapter 8 — "The Ultrastable System", pp. 90–102. PDF at archive.org/details/designforabrain.
mode: linear
permalink: /cybernetics/ashby-homeostat/
---

# Ashby Design for a Brain — The Ultrastable System (Homeostat)

*Linear-cumulative rewrite of Chapter 8 of Ashby's Design for a Brain (1952). The chapter builds: step-functions plus fields generate a selective process; that process defines an ultrastable system; a physical machine — the homeostat — instantiates it; the machine differs from an ordinary stable system in a specific way (less specification, more orders of stability); and the machine then exceeds its own specification by adapting to constraints the designer never put in the spec. Source vocabulary preserved: step-function, main variable, field, critical state, terminal field, ultrastability, uniselector, parameter, region.*

[← Cybernetics index](/cybernetics/)

---

## The problem, restated

The book opened with a kitten learning not to walk into the fire. Chapter 5 turned that into a definition: a system is **adapted** when its variables — animal plus environment — are coordinated so the whole system is stable in a region of phase-space we care about.

Chapter 6 and 7 then narrowed the mechanism. An observed system can change from one form of behaviour to another **only** if some parameter has changed value. And if no deus ex machina is allowed to reach in from outside, the parameters that change must be *inside* the system, behaving as step-functions: variables that hold a value, then jump.

So the final form of the problem is short.

**Step-functions, by their changes in value, will change the behaviour of the system. What can ensure that the step-functions change *appropriately*?**

This chapter answers that.

## Two reciprocal actions

Step-functions and fields couple in two directions.

First direction. When a step-function changes value, the **field** of the main variables changes — the entire map of trajectories in phase-space is replaced by a new map. We saw this in Chapter 7.

Second direction. **Fields differ in how their trajectories relate to the critical states** — the points or surfaces at which step-functions will change value. Some fields are arranged so almost every starting state leads its trajectory across a critical state. Other fields are arranged so almost no trajectory does. Given a distribution of critical states and a distribution of starting states, swapping one field for another changes the proportion of trajectories that will trip a step-function change.

Each action evokes the other. A step-function change reshapes the field. The new field, depending on its geometry, may or may not lead the system back to a critical state. If it does, another step-function changes. If it doesn't, the process stops.

## The ultrastable system

Call a system **ultrastable** when it is absolute (closed, state-determined) and contains enough step-functions that we can ignore the finiteness of their number.

Watch its main variables after release from some state. If the field leads the representative point to a critical state, a step-function changes and the field is replaced. If the new field again leads to a critical state, another step-function changes. And so on.

For the process to stop, one and only one thing is required: the new field must not lead the representative point to a critical state. Call such a field **terminal**.

If you watch only the main variables, you see field after field being rejected until one is retained. The process is **selective towards fields**.

This is the load-bearing claim of the chapter, and it's worth stating cleanly:

**An ultrastable system acts selectively towards the fields of its main variables, rejecting those that lead the representative point to a critical state and retaining those that do not.**

Everything else in the chapter — and most of the rest of the book — is the consequence of this principle.

## Critical states around a region

A biological system has a region of phase-space it must stay inside: body temperature in a band, blood pH in a band, blood glucose in a band, oxygen tension in a band. Outside that band, things break.

So look at the case where the critical states **surround a region** — they form a kind of fence in phase-space. The representative point is started somewhere inside.

Suppose two main variables A and B. Field I leads the point out toward the fence. It crosses a critical state. A step-function flips. Field II appears. Field II again leads the point further out, crosses another critical state, flips another step-function. Field III appears. Field III happens to contain a stable resting state, but from where the point currently sits, the trajectory still drifts out toward the fence — one more critical state met, one more step-function changes, Field IV.

Field IV is stable inside the region. The point moves to its resting state and stops. No further critical states. No further step-function changes. From now on, if you examine the field of the main variables, it is stable.

**If the critical states surround a region, the ultrastable system is selective for fields that are stable within the region.**

So far, this has been purely logical. Every claim in the chapter so far is about a defined object — an absolute system with step-functions and critical states arranged a certain way — and what such an object would do if it existed.

Ashby's next move is to build one.

## The Homeostat

To test the reasoning against something independent of the reasoning, Ashby built a machine that satisfies the definition of an ultrastable system. He called it the **homeostat**.

The construction:

**Four units.** Each unit carries on top a pivoted magnet. The angular deviations of the four magnets from their central positions are the four **main variables**.

**Each unit emits a DC output proportional to its magnet's deviation from centre.** In front of each magnet sits a trough of water, with electrodes at each end producing a potential gradient. A wire on the magnet dips into the water, picks up a potential corresponding to the magnet's position, and feeds it to the grid of a triode. The triode's anode-cathode circuit is biased so that the output current is approximately proportional to the magnet's deviation.

**The four units are joined so each one's output is sent to the other three.** Each unit therefore receives an input current from each of the other three. These input currents act on the magnet through coils, so the torque on the magnet is approximately proportional to the algebraic sum of the currents.

**Before each input current reaches its coil, it passes through a commutator (which sets polarity) and a potentiometer (which sets gain).** Together: 32 parameters, by hand.

So far the machine is a dynamic system of four coupled magnets, with thirty-two knobs determining the field. Some knob settings produce stable fields, in which the magnets return to centre after a disturbance. Other settings give a runaway. As of this stage the system is not yet ultrastable — the parameters are fixed at the values the operator chose.

**Now replace the hand-set parameters with switches that route through a uniselector** — a stepping switch. Each uniselector has twenty-five positions; the values built onto the positions were taken from Fisher and Yates' table of random numbers. Four uniselectors (one per unit), twenty-five positions each, give 25⁴ = 390,625 combinations of parameter-values.

**The uniselectors step only when needed.** A relay closes the uniselector-coil circuit *only when* a magnet diverges far from centre — past a critical state at about 45°. A separate clock interrupts the coil circuit at regular intervals, so as long as the relay is closed, the uniselector keeps stepping; as soon as the relay opens, the stepping stops.

The system now has eight variables — four magnet deviations and four uniselector positions. The eight together are absolute. The four magnet deviations are the main variables. The four uniselector positions are the step-functions. The critical states are the ~45° magnet deviations. They form a "cube" around the origin in the phase-space of main variables.

**This satisfies the definition of an ultrastable system.** And empirically, it acts the way the definition says it should.

<svg viewBox="0 0 540 360" xmlns="http://www.w3.org/2000/svg" style="max-width:640px;display:block;margin:1.5em auto;">
  <defs>
    <marker id="arr" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0 0 L 10 5 L 0 10 z" fill="#333"/>
    </marker>
  </defs>
  <!-- Title -->
  <text x="270" y="22" text-anchor="middle" font-family="serif" font-size="16" font-weight="bold">One homeostat unit (schematic)</text>
  <!-- Magnet pivot -->
  <circle cx="120" cy="120" r="40" fill="none" stroke="#333" stroke-width="2"/>
  <line x1="120" y1="120" x2="155" y2="100" stroke="#c44" stroke-width="3"/>
  <circle cx="120" cy="120" r="3" fill="#333"/>
  <text x="120" y="80" text-anchor="middle" font-family="serif" font-size="13">M (magnet)</text>
  <text x="160" y="135" font-family="serif" font-size="11" fill="#c44">deviation</text>
  <!-- Water trough -->
  <rect x="60" y="180" width="120" height="20" fill="#cce" stroke="#336" stroke-width="1"/>
  <line x1="120" y1="160" x2="120" y2="180" stroke="#333" stroke-width="1.5" stroke-dasharray="3,2"/>
  <text x="120" y="215" text-anchor="middle" font-family="serif" font-size="11">water trough (potentiometer)</text>
  <text x="50" y="195" text-anchor="end" font-family="serif" font-size="11">+V</text>
  <text x="190" y="195" font-family="serif" font-size="11">−V</text>
  <!-- Triode -->
  <rect x="220" y="170" width="80" height="40" fill="none" stroke="#333" stroke-width="2"/>
  <text x="260" y="195" text-anchor="middle" font-family="serif" font-size="12">triode</text>
  <line x1="180" y1="190" x2="220" y2="190" stroke="#333" stroke-width="1.5" marker-end="url(#arr)"/>
  <!-- Output to other units -->
  <line x1="300" y1="190" x2="380" y2="190" stroke="#333" stroke-width="1.5" marker-end="url(#arr)"/>
  <text x="340" y="183" text-anchor="middle" font-family="serif" font-size="11">output → other units</text>
  <!-- Inputs back -->
  <line x1="380" y1="120" x2="160" y2="120" stroke="#333" stroke-width="1.5" marker-end="url(#arr)"/>
  <text x="270" y="113" text-anchor="middle" font-family="serif" font-size="11">inputs from other units → coils A, B, C</text>
  <!-- Commutator -->
  <rect x="380" y="240" width="50" height="30" fill="#fee" stroke="#333" stroke-width="1.5"/>
  <text x="405" y="259" text-anchor="middle" font-family="serif" font-size="10">commutator</text>
  <!-- Potentiometer -->
  <rect x="450" y="240" width="50" height="30" fill="#efe" stroke="#333" stroke-width="1.5"/>
  <text x="475" y="259" text-anchor="middle" font-family="serif" font-size="10">potentiometer</text>
  <text x="440" y="290" text-anchor="middle" font-family="serif" font-size="11">parameter pair (polarity, gain)</text>
  <!-- Uniselector -->
  <rect x="380" y="310" width="120" height="35" fill="#ffe" stroke="#c80" stroke-width="2"/>
  <text x="440" y="332" text-anchor="middle" font-family="serif" font-size="12">uniselector (25 random positions)</text>
  <line x1="440" y1="270" x2="440" y2="310" stroke="#c80" stroke-width="1.5" stroke-dasharray="4,3"/>
  <!-- Critical state trigger -->
  <line x1="300" y1="200" x2="380" y2="310" stroke="#c44" stroke-width="1.2" stroke-dasharray="2,2"/>
  <text x="360" y="265" font-family="serif" font-size="10" fill="#c44">when |M| &gt; 45° → step</text>
</svg>

The simplest case: one unit fed back into itself through one uniselector coil. The operator displaces the magnet. If the field happens to be stable (the first uniselector position is "right"), the magnet returns to centre on its own — corrected. The operator then reverses the polarity of the output-input junction, making the field unstable. A runaway develops; the magnet crosses the critical state; the uniselector steps. The first new position happens to give a stable field — the magnet returns. Reverse the polarity again; another runaway; this time three uniselector positions give unstable fields and are rejected before the fourth gives stability.

Two units interacting: same pattern, more interesting. The diagram of immediate effects is 1↔2. The operator reverses the commutator on 1→2 by hand. Runaway. The uniselector on 2→1 changes position. The first new value happens to give stability. Where, before, an upstroke disturbance in unit 2 caused an upstroke in unit 1, after the uniselector change the same disturbance causes a *downstroke* — the action 2→1 has been reversed by the uniselector to compensate for the operator's reversal of 1→2.

The homeostat does what the logical definition says an ultrastable system should do.

## What's different about ultrastable

Now compare ultrastable with ordinary stable. Both are absolute. Both have, viewed at the level of all their variables, a single permanent field.

But compare an ordinary stable system's full field with an ultrastable system's **main-variable** field. The ordinary stable system shows one permanent field. The ultrastable system shows **a succession of transient fields, concluded by a terminal field that is stable**.

The aileron analogy makes the consequence concrete. An autopilot is a stable system: when the plane rolls right, the output rolls the ailerons to push left. The plane is now self-correcting against turbulence. The homeostat, properly wired, would do the same.

Now reverse the ailerons. The autopilot, perfectly wired the wrong way, persists in its wrong action to the end — when the plane rolls right, the wrongly-wired autopilot pushes it further right, and continues doing so all the way down. The homeostat, wrongly wired, also persists in its wrong action — but **only until the rising deviation crosses a critical state**. Then a step-function changes. On the first new field that gives stability, the homeostat returns the plane to horizontal and now corrects for further disturbances.

There's a real difference here, and it justifies the prefix **ultra**. The autopilot is stable around one field. The homeostat is stable around its *choice of fields* — if the operative field is unstable, it will change the field until the field is stable. The degree of stability is one order higher.

A second difference: **less specification**. An autopilot must be wired to the ailerons with care. An ultrastable pilot could be wired to the ailerons at random; it would find a working wiring on its own. A linear system of n variables requires correct specification of at least n parameters to be stable. An ultrastable system of n main variables needs only about six independent specification items — the number of independent items in the specification of the system itself. **A large system can be made stable with much less detailed specification if it is made ultrastable.**

This is the design principle that makes the homeostat interesting. Not that it is stable. That it is stable *without having to be told how*.

## The constraint test

The chapter closes with a result Ashby evidently liked, and it deserves attention because it's where the machine outruns its specification.

The homeostat finds a terminal field. That field is stable in conjunction with whatever values the rest of the system's parameters happen to have. Every absolute system carries an indefinitely large number of parameters with it — the electrostatic charge on the bodies, the chemistry of the room, the gain on the triodes — most of which are taken for granted because they have well-understood "obvious" values. **The terminal field is stable given all of them, whether they were the obvious values or not.**

To test that, after the machine was completed, Ashby imposed complications that had never crossed his mind during design. One: he joined the front two magnets with a light glass fibre so they could only move together. Three units interacting, stable; the operator displaced magnet 1 to verify the stability. Then he joined magnets 1 and 2 with the fibre. The constraint made the system unstable. But the resulting drift across a critical state evoked step-function changes, and a new terminal field appeared. The new field was stable — verified by a second displacement.

Then the operator gently lifted the fibre away. The system became unstable again.

**The new step-function values had "taken notice of" the fibre.** They were not the values that gave stability without the fibre. They were the values that gave stability *with* the fibre. Lift the fibre, and the new arrangement no longer applies.

This is small. It is also, in retrospect, the whole point.

The principle of ultrastability is a logical principle. It says: such a system, if it exists, will select for terminal fields. It does *not* say what the terminal field will be stable against. The homeostat answers: against everything that happens to be true of the system at the moment a step-function settles, including things the designer never specified. The machine adapts to constraints it was never told existed. That is what "adapted to its environment" means, with the metaphysics taken out.

---

*Chapter 9 takes this principle into living organisms — Jennings on Stentor, then up the phylogenetic tree.*

---

**What I cut.** Most of the worked example in §8/7 (the four-field trajectory in phase-space — kept the verbal description, cut the figure-by-figure walkthrough). The references at the chapter's end. The aside on "rigorously true" exceptions to the selectivity statement, which Ashby himself flags as a temporary imprecision cleaned up in §13/4. The full polarity-reversal play-by-play on Figures 8/8/4 and 8/8/5 — kept the structural beats, dropped the per-stroke commentary. Section numbering throughout.

**What I added.** Bolded load-bearing one-liners. The schematic SVG of one homeostat unit. The "constraint test" framing in the closing section is mine — Ashby presents §8/10 in the flat 1950s register; the line "the machine outruns its specification" is the load-bearing claim made explicit. The "metaphysics taken out" closing line is mine.

**Structure choice.** Linear-cumulative. The chapter builds: two reciprocal actions → the ultrastable system → critical states around a region → the homeostat → the contrast with ordinary stable → the constraint test. The argument doesn't invert mid-chapter (chiasm), synthesize opposites (contrast), or revisit the same idea at deeper register (spiral). It accumulates from the logical principle to the physical demonstration to the principle exceeding itself. §8/10 (the fibre test) reads like a chiastic close on a linear build — the machine outruns the principle that defined it — but I'd rather call the chapter linear honestly than force a chiasm for the sake of structural variety.
