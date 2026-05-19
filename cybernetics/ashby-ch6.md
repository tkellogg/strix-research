---
layout: default
title: "Ashby Ch 6 — The Black Box"
date: 2026-05-19
permalink: /cybernetics/ashby-ch6/
---

# The Black Box

> *Open: an engineer has a sealed box and wants to know what's inside.*
>
> *Close: there are no insides. Every object is a Black Box. "What's inside" is the relation between you and what you can distinguish.*

The chapter inverts. It opens in the engineer's workshop — a literally sealed device, dials and levers, find out what it contains. By the middle it has widened to every act of observation: the bicycle, the brain, the dog. At the end it has flipped completely: **memory** is not a thing the dog has; it is a name for what the observer cannot see.

The frame the chapter opens with — *something is hidden, I will find it out* — is the frame the chapter dissolves.

---

## The engineer and the sealed box

The problem arose literally in electrical engineering. A sealed bomb-sight becomes defective. Open it or scrap it? You aren't allowed to open it. You have terminals for input — apply any voltages, shocks, signals you like — and terminals for output, from which you record what you can. Deduce what's inside.

Sometimes the box is sealed by secrecy. Sometimes by inconvenience: a telephone engineer in the middle of working machinery that can't be dismantled for an idle question. Sometimes by biology: the clinician with an aphasic patient, the psychologist with a rat in a maze, the child learning a door handle. The mechanism is *not open to inspection*. You have to work around the casing.

Most experimenters treat the casing as a nuisance — something between them and the answer. The Black Box theorist treats it as the situation. The questions become:

- How should an experimenter proceed when faced with a Black Box?
- What properties of the contents are discoverable, and what are fundamentally **not** discoverable?
- How should the investigation be made efficient?

These questions can only be asked if you accept, at least temporarily, that the casing exists. Then you can develop a scientific epistemology.

---

## The two harmless conventions

Drop every assumption about what's inside — it might have just fallen from a Flying Saucer. You have **resources for acting on it** (prodding, light, voltage) and **resources for observing** (camera, thermometer, voltmeter). By acting and observing, you couple yourself to the Box. You and it form one system with feedback.

For the coupling to be reproducible, the set of inputs and the set of outputs must be **decided in advance**. Every real system has indefinitely many possible inputs and outputs. The orderly investigation is the one in which you've chosen which ones.

Two conventions:

1. **Inputs are levers and pointers** — like the controls on a domestic oven. "Input state" = the configuration a snapshot of the controls would show.
2. **Outputs are dials** — the position of every pointer at a moment is the output state.

The experimenter is now an engineer on a ship's bridge, sitting before a set of levers and telegraphs, watching a row of dials. Almost every real system — biological, economic, electrical, conversational — fits this representation.

---

## The protocol and the canonical representation

*A man cannot step twice into the same water; neither can he twice conduct the same experiment.* He can only perform another experiment that differs in some agreed-negligible way. What he records is a **protocol**: a long sequence, drawn out in time, of the input and output states at each moment.

> 11:18 a.m. — I did nothing. The Box emitted a steady hum at 240 c/s.
> 11:19 — I pushed the switch K. The note rose to 480 c/s and remained steady.
> 11:20 — Accidentally I pushed the button "!". The Box increased in temperature by 20°C.

Or, when the variables are coded:

| Time | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | ... |
|------|---|---|---|---|---|---|---|---|---|---|
| Input · output | a g | a j | a f | a f | a f | b f | b h | b h | a h | ... |

The primary data of any Black Box investigation is a sequence of vectors with two components: **(input state, output state)**.

From this follows the deduction that does most of the chapter's work:

**All knowledge obtainable from a Black Box of given input and output is such as can be obtained by re-coding the protocol. All that, and nothing more.**

You may have expected something. Others may have. None of that matters. The protocol is final.

A note on skill: **none is required**. Random variations of the input — *guided by throws of a die* — are as defensible as any other strategy, when nothing is known. Skill only enters once you have prior experience with Boxes of the same class. With a Flying Saucer device, you throw dice.

---

## Absoluteness and inaccessible states

What the experimenter looks for first is **determinacy**: does the next state, given input and current output, follow single-valuedly from the present? He sorts the protocol into a transformation table, one row per input state, and asks whether each cell is consistent. If so, the Box is a **determinate machine**, and its canonical representation is now in his hand.

If a cell is multi-valued, he has two moves:

1. **Add variables.** A chemist's reaction looks indeterminate until he accounts for trace chloride. Much of research is the search for additional variables that restore determinacy.
2. **Drop down to statistical determinacy.** The system may not be predictable step-by-step but predictable in averages — a Markov chain. (Ashby returns to this in Ch 9.)

Some states in the protocol can never be returned to. A new state, once past, is **inaccessible** — no input combination brings it back. The dramatic case: investigating a new enemy mine leads to an explosion. Less dramatic but identical in structure: experimenting on an organism that learns. The naïve state is gone after the first trial, and no input recovers it. The psychologist who needs the naïve state takes a new individual; he is implicitly studying the species, not the organism.

Either restrict the investigation to a closed, freely accessible set of states, or enlarge the input set so more transitions become available. The mechanism is not unique either. Shannon showed that any given behaviour can be produced by an indefinitely large number of relay networks. A given diagram of immediate effects can be realised by infinitely many internal arrangements. **The behaviour does not specify the connections.**

---

## Isomorphism — what is interchangeable

The Box, fully studied, is specified **up to an isomorphism**.

A photographic negative and its print are isomorphic in pattern, though opposite in brightness. A map and its country are isomorphic, when the map is accurate. A stone thrown up at 50 ft/s and the graph $y = 50x - 16x^2$ are isomorphic, though one is matter and the other is ink.

The deepest case Ashby gives: three machines, none alike on the surface, all interchangeable in behaviour.

- A **mechanical** system — an axle rotating against a spring, a heavy wheel dipped in a viscous trough. Input dial $u$, output dial $v$.
- An **electrical** system — a voltage source, an inductor, a resistor, a capacitor, an integrating ammeter. Input dial $x$, output dial $y$.
- A **mathematical** system — the differential equation $a \, d^2z/dt^2 + b \, dz/dt + cz = w$. Input $w$, output $z$.

Tune the constants. Start each from rest. Drive any of the inputs with any sequence whatever. The three outputs match, throughout an infinite number of tests, along their whole length. Cover the casings and they are **indistinguishable through observation**.

This is the foundation of every modelling practice in science. Solving the differential equation = looking at the math model = "applied mathematical physics." Building the electrical circuit and reading $y$ = "an analogue computer." Building the mechanical version = "a physical model." The big general-purpose digital computer is remarkable precisely because *it can be programmed to become isomorphic with any dynamic system whatever*.

**Formally:** two canonical representations are isomorphic iff a one-one transformation of the states (input and output) of one machine into those of the other converts one representation to the other.

A re-labelling of **states** is fully free. A re-labelling of **variables** is more constrained — if $(x_2, y_3)$ maps to $(\alpha, \beta)$ and $(x_3, y_1)$ to $(\gamma, \delta)$, then $(x_2, y_1)$ must map to $(\alpha, \delta)$. The variable re-labelling preserves the **diagram of immediate effects**; the state re-labelling does not.

There is an even more general transformation — combining variables. $u = x - y$, $v = x + y$ may collapse a coupled system into two independent ones. This is the "method of normal coordinates" in mathematical physics: the obvious diagram is exchanged for an isomorphic form where the variables are independent. What the transformation preserves is the **characteristic way of behaving** — the normal modes.

---

## Homomorphism — what is reducible

Strict isomorphism is the strongest equality: two Boxes are isomorphic when interchanging them would be undetectable.

A weaker, more useful relation: **homomorphism**. A many-one transformation, applied to the more complex machine, reduces it to a form isomorphic with the simpler.

Two pendulums, one beating seconds, the other half-seconds: not isomorphic. But homomorphic — they become isomorphic if you halve one of the timescales. A 5-state machine that always lands in $\{f, h, j\}$ is homomorphic with a 3-state machine that captures only the recurrent block. An observer with **less power of discrimination** — one who cannot tell $a$ from $b$ from $c$ — sees only the simpler machine. *Homomorphism is the formal expression of less-than-full discrimination.*

The classical example: **arithmetic on Even and Odd**.

| · | Even | Odd |
|---|------|-----|
| Even | Even | Even |
| Odd | Even | Odd |

This is an infinitesimal fraction of the multiplication table, yet **complete within itself**. It is the first homomorphism considered in mathematics. Knowledge can be partial in respect to the whole and complete in respect to itself.

Homomorphisms also exist **inside a single machine**: between its various simplifications that still preserve the property of being machine-like. Not every grouping of states gives a homomorphism. The grouping must preserve determinacy — when the lumped states transition, they must transition consistently. An observer who lumps states arbitrarily may end up with a system that looks indeterminate, and will (rightly) try to refine his measurements.

The simplifications of a machine form a **lattice**: top, the fully discriminated machine; bottom, the trivial one-state machine "it persists." Between them, every coarser-grained view. *Closure* — being a machine at all — is the lattice's floor. Persistence is the most rudimentary property; everything else is what you add by distinguishing more states.

A **model** of a system is usually a homomorphism — and not even a tight one. The tin mouse is a model of a living mouse, *provided one ignores the tinniness of the one and the proteinness of the other*. Formally: a homomorphism of the model is isomorphic with a homomorphism of the original. The relation is symmetric — either can model the other. The higher in their respective lattices the matching homomorphisms sit, the better the model.

---

## Pivot — every object is a Black Box

Here the chapter inverts.

Ashby has been speaking as if the Black Box is the special case: the engineer's sealed device, the rat in the maze, the alien artefact. But:

> *A bicycle is not a Black Box, for we can see every connecting link.* — We delude ourselves. The ultimate links between pedal and wheel are interatomic forces. Of these we see nothing. The child who learns to ride does so with the working knowledge that pressure on the pedals makes the wheels go round.

**Real objects are all Black Boxes. We have been operating with Black Boxes all our lives.**

The theory of the Black Box is not a corner of engineering. It is the theory of real objects, when close attention is given to *the question, relating object and observer, of what information comes from the object and how it is obtained*.

> "A study of the real world thus becomes a study of transducers." — Goldman.

The frame the chapter opened with — *something is hidden behind a casing* — is now revealed as the universal situation. Every object an observer encounters is a Black Box. The "interior" is whatever the observer's instruments distinguish. There is no privileged inside.

---

## Emergence as an artefact

Once the casing is universal, the apparent paradox of "emergent" properties dissolves.

The classical examples:
1. Ammonia (gas) + hydrogen chloride (gas) → ammonium chloride (solid). A property the reactants didn't have.
2. Carbon + hydrogen + oxygen, all tasteless, combine into sugar with a sweet taste.
3. Twenty amino-acids, none self-reproducing, combined into a self-reproducing bacterium.

In every example the prediction was based on **far less knowledge** than a canonical representation. "Hydrogen chloride is a gas" is one bit of one variable. The canonical representation of an amino-acid would be the set of all electrical and mechanical forces that can affect it, paired with the set of all states it can be in. Given that, the behaviour of any coupling of amino-acids is predictable. **Emergence appears at the gap between the partial knowledge that was extrapolated and the full knowledge that would have predicted.**

Emergence is not in the system. It is in the gap between what the observer knew and what the system contained.

(With this said: when the range from part to whole is very large, the properties at the two ends genuinely tend to differ. The Exciseman in his district can mark every building as part of the brewing trade and call it "localised." The map-maker of England, unable to mark a county as the seat of brewing, calls it "not localised." Both correct. *What is true at one end of the scale may be false at the other.* Rubber molecules have no inherent contractility; stretch one out and let it go and nothing happens. Yet rubber contracts. Why? Many molecules jostle each other and force the majority to lengths below their maxima, like a fifty-foot rope on a crowded beach. The macro property is a statistic of micro non-properties.)

---

## Very large systems and the topological method

As the system gets bigger, the protocol-and-canonical-representation method becomes prohibitively laborious. Newtonian mechanics solves three bodies with difficulty, six bodies barely at all, twenty thousand stars not as full trajectories. What is the astrophysicist to do?

He must be careful what question he asks. He must ask for what he *really* wants to know, not what he thinks he wants. The beginner asks for the trajectory of every star. Given the volumes of numerical tables, he realises he didn't want that. The real question is usually simple: *will the cluster contract to a ball or spread out into a disc?*

The topological method, developed since Poincaré, answers questions of this kind without ever computing the laborious trajectories. The stability theory of differential equations is the same move: deduce the main features of the solutions without writing the full solutions out.

This is the right approach to a Black Box too large to study in full detail. **The brain, for the cybernetically-minded psychologist, is a Box of this kind.** Lewin attempted such a topological psychology in the 1930s; topology wasn't yet developed enough to be a tool. By Bourbaki it is. The possibility of a psychology that is **at once rigorous and practical** is now before us.

---

## The incompletely observable Box

Now the deepest move. So far the dials have all been visible. What if some are hidden?

A system has parts $A$ and $Z$, both fed by an input $I$. The interesting behaviour $B$ occurs only when $I = \alpha$ *and* $Z = y$. And $Z$ is at $y$ only after $I$ has previously had the value $m$.

**Observer One** sees both $A$ and $Z$. He reports: $B$ happens whenever $Z = y$ and $I = \alpha$ right now. The system has no memory; current state suffices.

**Observer Two** can see only $A$ and $I$, not $Z$. Knowledge of the present is not enough — $Z$ varies and he can't see it. But he notices that $B$ appears iff $I$ went through the sequence $m, \alpha$. The earlier value of $I$ predicts now. **He must postulate that the system has memory.**

The correspondence

$$I \text{ at } m \text{ earlier} \;\;\Longleftrightarrow\;\; Z \text{ at } y \text{ now}$$

makes "$I$ a step earlier" and "$Z$ now" informationally equivalent. To know one is to know the other. They are different routes to the same content.

One and Two are not in conflict. They are observing **different systems**: $I + A + Z$ versus $I + A$. The same physical apparatus, framed by two different choices of observable, has memory and does not. Memory is not a property of the apparatus.

**General rule.** If a determinate system is only partly observable and thereby becomes not predictable for that observer, the observer may be able to restore predictability by taking the system's past into account — i.e., by **postulating memory**. Memory is the trace of unobservable variables, projected into the time axis. It is a relation between system and observer.

> *Memory in the brain is only partly objective. No wonder its properties have sometimes been found unusual or paradoxical. The subject requires thorough re-examination from first principles.*

The chapter's last example — a digital calculator with a magnetic tape. Whether it has memory depends on whether you can see the tape. The observer who sees the magnetisation says the next output follows from the present configuration; no memory needed. The observer who cannot see the tape says: ten minutes ago a switch was closed, and that's why a 1 comes out now. Memory.

Or the friend's dog. A car goes past outside. The dog rushes to the corner and cringes. To you, causeless. Then your friend says, "He was run over by a car six months ago." Memory — but only because you couldn't observe the trace inside him.

> *If one is not careful one says that the dog "has" memory, and then thinks of the dog as having something, as he might have a patch of black hair. One may then be tempted to start looking for the thing; and one may discover that this "thing" has some very curious properties.*

---

## Closure: the frame inverted

The chapter began with a sealed box and an experimenter who wanted to know what was inside.

It ends with the recognition that every object is a Black Box and "what is inside" is whatever the observer has chosen to discriminate. **The inside is not a feature of the object. It is the relation between the object and the observer's instruments.**

- **Determinacy** — the property that the protocol can be re-coded into a canonical representation — is what makes "machine-like" a meaningful predicate.
- **Isomorphism** — equality between representations under a one-one re-labelling — is what makes models and analogues possible. The differential equation, the electrical circuit, and the mechanical system are interchangeable because they are isomorphic.
- **Homomorphism** — the formal expression of less-than-full discrimination — is what makes science practicable on systems too large to study in their full state space. Every model is a homomorphism.
- **Emergence** is the residue of partial knowledge being extrapolated past what it can support.
- **Memory** is the name an observer gives to what he cannot see.

The cybernetic move is to **stop locating these properties inside the object** and start locating them in the **transduction** between object and observer. The conjurer is miraculous because some of his significant variables are hidden. The brain may be miraculous for the same reason. Strip the casing and the miracle becomes a determinate machine — but **the casing is universal**. There is no operation that strips it away. There is only the operation of widening the set of variables you can observe.

The protocol is final. The protocol is also all there is.

---

*Structure choice — chiasm. The chapter opens with "find out what's inside the sealed box" and ends with "every object is sealed; inside is what you can distinguish." The middle (S.6/17 — "real objects are in fact all Black Boxes") is the pivot. Isomorphism and homomorphism on the way in, emergence and memory on the way back out.*

*What was cut: the worked transition tables (Ex. 1–7 of §6/5), the algebraic exercises throughout §6/9 and §6/10, the diagram-of-immediate-effects exercises in §6/7, the kinematic-graph rearrangement figures of §6/9. The lattice-of-simplifications worked example (the six forms of the Ex. 6/13/2 system) is summarised rather than enumerated.*

*What was kept: the bomb-sight / telephone / aphasic / rat / door-handle list, both harmless conventions, the protocol example with the Flying Saucer Box, the fundamental deduction ("all knowledge … re-coding the protocol; all that, and nothing more"), Shannon's relay-network non-uniqueness, the three-machine isomorphism (mechanical / electrical / differential equation), the universal-digital-computer remark, the Even-Odd multiplication homomorphism, the lattice with top = full discrimination and bottom = "it persists", the rubber-and-rope-on-a-beach example, the ammonia / sugar / amino-acid emergence list, the brewing-Exciseman-vs-map-maker scale paradox, the topology / star-cluster move, the $I, A, Z$ correspondence and the rule about memory, the magnetic-tape and the dog-and-car examples.*

*What was added: the explicit chiastic framing, the load-bearing one-liners ("All knowledge obtainable … is such as can be obtained by re-coding the protocol", "Real objects are all Black Boxes", "Memory is the trace of unobservable variables, projected into the time axis"), the closing summary that names what each concept actually does (determinacy → machine-likeness, isomorphism → analogues, homomorphism → models, emergence → epistemic gap, memory → hidden variables).*
