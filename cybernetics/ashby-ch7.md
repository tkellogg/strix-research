---
layout: default
title: Ashby Ch 7 — Quantity of Variety
date: 2026-05-17
source: Ashby, W. Ross. *An Introduction to Cybernetics.* Chapman & Hall, 1956.
mode: chiastic restructure
permalink: /cybernetics/ashby-ch7/
---

# Quantity of Variety

*Ashby, *An Introduction to Cybernetics*, Chapter 7. Structure: chiasm. Source vocabulary preserved (variety, constraint, bit, vector, transducer, basin, equilibrium, one-one transformation, Law of Experience).*

[← Cybernetics index](../cybernetics/)

> If he struck it once, the dog came who sat upon the chest of copper money; if he struck it twice, the dog came who had the silver; if three times, then appeared the dog who had the gold.
> — *The Tinder-Box*

Three strikes, three dogs. The matchbox is a regulator. Hold onto that — we come back to it at the end, from the other side.

---

## A. The set, not the thing

"The chloride ion is negatively charged." The lecturer says *the* ion, singular, but he means every ion that ever was — the whole set. Same with *the* petrol engine, *the* growing child, *the* chronic drunkard. Singular grammar, set-shaped reference.

Sometimes the slippage between "individual" and "set" is harmless: the elephant eats with its trunk — true of every elephant, true of one elephant. But sometimes the set says one thing and the individual says the opposite. A gramme of hot hydrogen iodide may be 37% ionised; no single molecule is 37% ionised — each one is fully ionised or not at all. Twenty million women have thirty million children, but Mrs. Everyman doesn't have one and a half kids; the half-child is ten million children rounded weird.

So the first move of cybernetics is to learn to *see the set*. A statement about a set can be true, false, or meaningless when applied to its elements — and vice versa. Stop thinking about *this* message, *this* machine, *this* moment. Start thinking about the cloud of what *could* be there.

A prisoner's wife brings him coffee. The warder, paranoid, asks: what could this cup possibly *say*? Maybe she signals via sweet-or-not, so I'll sugar it heavily and tell him. Maybe via spoon-or-no-spoon, so I'll take the spoon and blame regulations. Maybe via coffee-vs-tea, so I'll point out the canteen only does coffee at this hour. The warder is doing something specific at every step: **he kills communication by collapsing the set of possibilities to one.** Sweet only. No spoon ever. Coffee only. The cup carries information *because* it could have been other than what it is. Strip its alternatives, strip its signal.

This is the load-bearing inversion that runs the whole book: **information lives in the set, never in the thing.** Two soldiers, two countries. Each wife receives "I am well." Country A's prisoners can pick from {I am well, I am slightly ill, I am seriously ill}; Country B's prisoners get only {I am well}. Same phrase, different message — because the *set the phrase came from* is different. The thing is identical. The information isn't.

So we'll stop asking "what does this message say?" and start asking "what set did it come from, and how many distinguishable elements does that set have?" That count gets a name.

---

## B. Counting variety

A set has **variety** equal to the number of distinguishable elements in it.

The set `c, b, c, a, c, c, a, b, c, b, b, a` has twelve elements but variety three — only *a, b, c* are distinct.

But "distinguishable" is the load-bearing word, and it has a twist: variety isn't a property of the set alone. It depends on who's looking. A two-armed semaphore can put each arm in eight positions: 64 combinations. But to a distant observer who can't tell left arm from right arm, "left up, right down" looks identical to "left down, right up" — so the variety collapses to 36, not 64. **The observer is part of the count.** Variety is set + discriminator, never set alone.

Usually we'll measure variety logarithmically — log base 2 of the number of distinct elements. The unit is the **bit** (BInary digiT). The variety of "which sex" is log₂ 2 = 1 bit. The variety of a 52-card deck is log₂ 52 ≈ 5.7 bits. (Log change-of-base: log_b N = (log_a N) / (log_a b). In particular log₂ N = 3.322 × log₁₀ N.)

Why bother with logs? Because when varieties combine multiplicatively, their bits add. The farmer can distinguish 8 chick breeds (3 bits); his wife can sex them (1 bit); together they distinguish 8 × 2 = 16 classes (4 bits = 3 + 1). Addition is just less work than multiplication, and the brain takes the offer.

A set "with no variety" — all elements one type — has variety log 2 1 = 0 bits. Zero bits doesn't mean nothing exists. It means nothing distinguishable exists. Worth holding apart.

> **Ex.** A spy in a four-windowed house signals at sea by lighting or not lighting each window. At night the relative positions are invisible. How many distinct signals can he show? (Answer: 5 — the count of *how many* are lit, since arrangement is unobservable. Variety log₂ 5 ≈ 2.3 bits, not 16 = 4 bits.)

The exercise is the inversion of the semaphore. The set of physical configurations is 16, but the set of *distinguishable* configurations is 5. Same physics, different observer, different variety. We're going to need that exact move when we talk about machines.

---

## C. What didn't happen: constraint

Now flip the lens. Up till now, we've been counting what's *in* the set. Now count what's *missing* from it.

**Constraint** is a relation between two sets: the variety actually present is less than the variety that could have been present.

A school takes only boys. Sex has variety 1 bit in general; in this school, variety 0. So 0 < 1: constraint. British traffic lights have three lamps (red, yellow, green), each lit or unlit — eight combinations possible. Only four actually appear. So 4 < 8: constraint.

How severe is a constraint? Look at how much it cuts the possibility space. Tell a rank of soldiers that no two same-birthday men may stand adjacent: barely a cut, slight constraint. Tell them no man may stand to the left of any man taller than himself: now only *one* ordering survives (assuming no ties). Same form ("you may not..."); wildly different severity.

What gives constraint such teeth? Three big classes — and you'll notice they fold back on each other:

**Object as constraint.** A chair has four legs. Each leg, alone in the workshop, has six degrees of freedom in 3D space. Four loose legs: 24 degrees of freedom. Once assembled into the chair, the whole assembly has 6 degrees of freedom — the chair as one rigid body. Where did the other 18 go? They got eaten by the *joins*. Knowing where three legs sit fixes the fourth — it has no freedom anymore. **The very thinghood of a chair — its being one chair rather than four loose legs — is exactly the constraint between its parts.** Object = constraint. The world is *insanely* rich in constraints; we just don't see them because we don't notice the cases that *could* have happened and didn't.

**Law as constraint.** Every law of nature says: of all the vectors of (position, velocity, etc.) you could write on paper, only a smaller set actually appears in nature. Newton's law lets you fill notebooks with planetary trajectories that never happen anywhere in the heavens — and tells you which ones do. The law isn't a description of what's possible; it's an exclusion of most of what's possible. **Every law of nature is a constraint.** Science is the search for constraints — a hunt for the parts of phase space that nothing visits. This is exactly cybernetics' angle: "look at the totality, then ask why the actualities are restricted to some portion of it."

**Prediction as constraint.** Anti-aircraft prediction works only because the aircraft *can't* be anywhere next second. Continuity is a constraint (position, speed, direction can't jump). Aircraft design is a constraint (an A-10 flies like an A-10). Pilot habit is a constraint. The predictor lives in the gap between what the plane could do and what it actually will do. **A perfectly unconstrained aircraft would be unpredictable, and a predictor on it would be useless.** Free behavior is uncrackable; constrained behavior is forecastable.

These three slide into each other: an object is a *thing* because the world enforces a *law* about its parts, and the law lets you *predict* where the fourth leg will be once you've seen three. Object → law → prediction → back to object. Each frames the other.

There's a fourth, and it's the bridge to the second half:

**Machine as constraint.** Run a system, write down what it does, get a protocol — a sequence of states. If the sequence shows no constraint, it looks like a roulette wheel. If it shows the *characteristic* constraint of being machine-shaped (i.e. the same input from the same state always produces the same next state), then we can compress the whole protocol down to two things: the transformation, plus the initial state. The protocol is the dataset; the machine is the constraint that lets us write the dataset as a function. **Calling something "a machine" is shorthand for "this protocol is heavily constrained in a particular way."**

So the whole back half of Part I — operands, transformations, basins, equilibrium — was already secretly a story about constraint. We just hadn't named it.

> **Ex.** Sit still for one minute. Try to count every constraint operating in your surroundings. (You can't. That's the point. The chair has 24→6 degrees of freedom; the room has walls; the air is at one temperature, not a million; your body is one body, not a cloud of organs.)

And one more thing about constraint before we pivot — a thing that's going to matter so much it gets its own foreshadow: **learning needs constraint to even be possible.** Pavlov giving paired stimuli with reinforcement only on certain combinations — the experiment works *only* because the full set of combinations is *not* presented. If A is followed equally often by 2, 3, and 5, the subject can't learn "A goes with 2." The maze must hold its shape from day to day or the rat can never learn it. **Learning is possible only to the extent that the world shows constraint.** Reach for that one when we get to the Law of Experience.

---

## C'. What does happen: machines burn variety

OK. We had variety. We had constraint. Now we let a machine chew on a set and watch what happens.

Take a single-valued transformation Z over three states:

> Z: A → B,  B → C,  C → C.

Feed it the set `B B A C C C A A B A` (variety 3). One step: `C C B C C C B B C B` (variety 2). Another step: all C's (variety 1).

**Why is variety falling?** Look at the graph of the transformation: arrows can *merge* (two operands map to one transform), but they can never *split* (one operand can't map to two transforms — that'd violate single-valued). Every merge eats one bit of variety. There's no inverse process to put variety back. So under any single-valued transformation, **variety in a set cannot increase, and usually falls.**

The only exception is a transformation that's **one-one** (over the letters actually present in the set) — every arrow goes to its own distinct target, no merges. One-one preserves variety. Anything else burns it.

This is the same shape as Section A in reverse. A: "stop thinking about the thing, think about the set." Now: "the machine eats the set down to the thing." We started by inflating an individual into its surrounding possibility-cloud; the machine deflates the possibility-cloud back toward a single state. The chapter is folding.

> **Ex.** A multiplicity of genotypes shows the same phenotypic feature. The genotype → phenotype map is some transformation V. What does V do to variety? (Reduces it. Many genotypes, one phenotype. Merge, no split.)

> **Ex.** A tea-taster transforms "leaf sample" into "opinion." If the taster is perfect, the transformation is one-one. If two distinguishable leaves produce the same opinion, the transformation is many-one. The bad-taster is the variety-burner.

> **Ex.** Room temperatures over seven readings: 65, 62, 68, 63, 62, 59, 61. The thermostatically-controlled water-bath: 97, 97, 98, 97, 97, 97, 97. Room variety: high (six distinct values). Bath variety: low (two). If the bath's variety exceeded the room's, the thermostat would be busted. The bath's near-zero variety *is* its regulation.

That last one is where we're heading. A regulator is something that *intentionally drives variety down*. The whole field of cybernetics is downstream of this idea.

So variety naturally decays under a machine left alone. What happens when the machine has *input*?

---

## B'. Counting what does happen: decay and the Law of Experience

Watch the variety of a population of identical machines, each in some state. Let them step forward in time under parameter value P₁. Their variety drops — by the argument just given — until it hits a minimum determined by P₁'s basins and equilibria. Now change the parameter uniformly across all of them to P₂. Two things to notice:

First, *the change itself can't raise variety*. If we apply the same change to every member of the set, two members that were at the same state before the change are still at the same state after. Same merges, no new splits.

Second, the change *can* drop variety further. Why? Because two states of equilibrium under P₁ might both sit in the same basin under P₂. Members that were stuck apart at D and E under P₁ both come to B under P₂. After enough time, everyone's at B. Variety: zero.

Repeat this with another input change, then another. **Each parameter change tends to drive the set's variety down further.** The members of the set become less and less differentiable by their initial state and more and more determined by the sequence of inputs they've been through.

Ashby names this the **Law of Experience**: a uniform change at the inputs of a set of transducers tends to drive the set's variety down. Or, more vividly:

> **Information put in by change at a parameter tends to destroy and replace information about the system's initial state.**

Run the same routine on a complicated machine every morning, and over time the experimenter doesn't need to know what state it was in last night — the routine has washed last night out. The kids of marked individuality who all go through the same school become more characteristic of the school than of their original individualities (Ashby's example, not mine — and yes, there's a lot to argue with there, but the mathematical bones are real). Boot sequences, training regimes, pedagogies, rituals: all of them are exploiting the Law of Experience whether they know the name or not.

This is the mirror image of Section B. There we counted variety so we knew what *could* be distinguished. Now we count it so we know what's *being erased*. Same instrument, opposite direction.

---

## A'. The thing, not the set

We started by saying: stop thinking about the individual, start thinking about the set. We end by noticing that the machine — left alone, or driven by input — is *also* doing that, but in reverse. It's taking the set and squeezing it back into the individual.

A set of replicates with high variety: I genuinely don't know which state any one machine is in. Wait. Variety falls. Now I know more about each one without ever observing it. In the extreme — one basin, one equilibrium — I can predict each machine's terminal state with certainty, without ever looking. **My uncertainty about the state decays exactly because variety decays.**

Said another way: if the variety in the set is the information stored, then *information stored can only diminish*. The cup of coffee carries three messages (hot, tepid, cold) if delivered fast. After an hour, two (tepid, cold). After a day, one (cold). The channel's capacity for information collapses as the set collapses.

This is the inversion of the prisoner's coffee from Section A. There: the warder *killed* communication by collapsing alternatives. Now: time and physics do it for free. Both are constraint-events. The warder was a regulator (intentional). Time is a regulator (passive, thermodynamic). Same shape, different agent.

And so back to the matchbox. Strike once: dog with copper. Strike twice: dog with silver. Strike three: dog with gold. Three strikes, three states, variety log₂ 3 ≈ 1.6 bits. The matchbox is the smallest regulator a fairy tale can hold: a parameter (number of strikes), a transducer (the box), a set of states (which dog appears), and a one-one transformation between strike-count and outcome. Variety perfectly preserved across the channel — no merges, no losses, the matchbox doesn't forget.

That's why it's magic. Almost every real machine in the world burns variety. The Tinder-Box is the rare object that doesn't. The whole rest of cybernetics is about what to do when you can't get a tinder-box and have to settle for the lossy kind.

---

*End of Chapter 7.*

[← Cybernetics index](../cybernetics/)

---

## Restructure notes

- Macro chiasm: **A. set vs thing → B. counting variety → C. constraint (what didn't happen) → C'. machines burn variety (what does happen) → B'. counting decay → A'. thing vs set (inverted)**. The pivot is the move from "count what's missing" to "count what's vanishing."
- Dropped: ~30 of ~40 exercises, all section numbering (7/1 through 7/25), the probability digression (7/4), the components-vary-independently degrees-of-freedom mechanics (kept the chair example because it's load-bearing for "object as constraint"), most of the Pavlov table and the letter-association example (kept the conclusion as foreshadow), the replicates-vs-single-machine epistemology section (folded into A'), the parameter-graph example with A B C D E F (the prose explanation does the work).
- Preserved: every named term, every defined concept, the bit math, the semaphore-vs-spy inversion (best illustration of observer-dependence), the prisoner's coffee (best illustration of communication-needs-set), the chair, the three laws-of-nature/object/prediction triplet, the tea-taster and water-bath exercises (best one-one and regulator illustrations), the Law of Experience full statement.
- Recurring chiasms within beats: warder-collapses-possibilities → physics-collapses-possibilities; observer changes 64→36 → transformation changes 3→1; learning needs constraint → Law of Experience uses constraint to erase initial state.
