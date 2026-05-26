---
layout: default
title: McCulloch & Pitts 1943 — A Logical Calculus of the Ideas Immanent in Nervous Activity
date: 2026-05-26
source: "McCulloch, W. S. & Pitts, W. (1943). 'A Logical Calculus of the Ideas Immanent in Nervous Activity.' *Bulletin of Mathematical Biophysics*, 5, 115–133."
mode: linear-cumulative
permalink: /cybernetics/mcculloch-pitts-1943/
---

# A Logical Calculus of the Ideas Immanent in Nervous Activity

*McCulloch & Pitts, 1943 — the paper that made neural nets a mathematical object.*

[← Cybernetics index](/cybernetics/)

---

## The move

The brain is a net of neurons. Each neuron either fires or doesn't — all-or-none, no gradations. **Once you take that seriously, a firing neuron is no longer a biological event; it's a proposition.** True when the cell fires, false when it doesn't. The wiring between neurons becomes the logical structure between propositions: this fires only when *these others* fired, with *those* inhibitors silent, one synaptic delay ago.

That's the whole move. Once you make it, everything the brain does is logic running on time-stepped propositions, and the question "what can a brain in principle compute" turns into "what can this calculus express." McCulloch and Pitts answer it.

This is the paper that gives neural nets their first piece of mathematics. Not the paper that gives them learning (that's Rosenblatt fourteen years later), not the paper that gives them gradients (Werbos, Rumelhart, much later). The paper that says: here is the formal object. Here is what it can be. Here is what it can compute. Everything after — perceptrons, backprop, transformers — inherits from this frame.

## Five assumptions

The model is brutally simple. Real neurons are messier, but the assumptions are picked so the messiness drops out of the calculus:

1. **All-or-none.** A neuron's output is a single bit per timestep — it fires or it doesn't.
2. **Threshold.** A fixed number of excitatory synapses must fire simultaneously to make the neuron fire. The number is the *threshold*. It doesn't depend on history or on where on the cell the synapses land.
3. **One delay only.** The only meaningful time cost is *synaptic delay* (~0.5 ms in real neurons). Conduction along the axon is fast enough to ignore. Time is discrete, ticking at one synaptic delay per step.
4. **Inhibition vetoes.** A single firing inhibitory synapse onto a neuron prevents that neuron from firing this step, regardless of how many excitatory synapses are active.
5. **Fixed wiring.** The structure of the net doesn't change.

Assumption (5) is the one that looks fatal — no learning, no plasticity. The paper undoes it later by showing learning is equivalent to a different kind of wiring. Hold the thought.

## Neuron = proposition

Number the neurons $c_1, c_2, \ldots, c_n$. Write $N_i(t)$ for the proposition "*neuron $c_i$ fires at time $t$.*" Then the assumptions translate directly:

A neuron with two excitatory inputs from $c_1, c_2$ and threshold 1 fires whenever either input fired one step ago. So

$$N_3(t) \equiv N_1(t-1) \lor N_2(t-1).$$

Threshold 2 instead: needs both.

$$N_3(t) \equiv N_1(t-1) \land N_2(t-1).$$

Add an inhibitor:

$$N_3(t) \equiv N_1(t-1) \land \neg N_2(t-1).$$

That's it. Boolean logic on the past, one step ago. McCulloch and Pitts give it a name: a **temporal propositional expression** (TPE) — a formula built from past values of input neurons using disjunction, conjunction, negation, and the time-shift operator $S$ (where $SP(t) \equiv P(t-1)$).

## Feedforward nets are exactly TPEs

Call a net *cyclic* if there's a directed loop in its wiring, *acyclic* (or "order 0") if not. Acyclic nets are feedforward — signals run from input neurons through layers to output neurons without ever returning.

For these, McCulloch and Pitts prove the equivalence in both directions:

**Theorem 1.** *Every feedforward net is equivalent to some TPE.*

**Theorem 2.** *Every TPE can be built by some feedforward net.*

The proof is constructive. For Theorem 2, four wiring patterns suffice as a basis:

<svg viewBox="0 0 640 360" xmlns="http://www.w3.org/2000/svg" style="background:#fafafa;border:1px solid #ddd;max-width:100%;height:auto;font-family:-apple-system,sans-serif;">
  <defs>
    <marker id="arr" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto">
      <path d="M0,0 L10,5 L0,10 z" fill="#333"/>
    </marker>
    <marker id="inh" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="8" markerHeight="8" orient="auto">
      <circle cx="5" cy="5" r="4" fill="#fff" stroke="#333" stroke-width="1.5"/>
    </marker>
  </defs>

  <text x="320" y="22" text-anchor="middle" font-size="13" font-weight="bold">Four primitives (one synaptic delay each)</text>

  <!-- (a) delay -->
  <g>
    <circle cx="60" cy="100" r="14" fill="#fff" stroke="#333" stroke-width="1.5"/>
    <text x="60" y="105" text-anchor="middle" font-size="11">1</text>
    <circle cx="160" cy="100" r="14" fill="#fff" stroke="#333" stroke-width="1.5"/>
    <text x="160" y="105" text-anchor="middle" font-size="11">2</text>
    <line x1="78" y1="100" x2="142" y2="100" stroke="#333" stroke-width="1.5" marker-end="url(#arr)"/>
    <text x="110" y="138" text-anchor="middle" font-size="11">(a) delay</text>
    <text x="110" y="155" text-anchor="middle" font-size="10" fill="#555">N₂(t) ≡ N₁(t−1)</text>
  </g>

  <!-- (b) OR -->
  <g>
    <circle cx="260" cy="80" r="14" fill="#fff" stroke="#333" stroke-width="1.5"/>
    <text x="260" y="85" text-anchor="middle" font-size="11">1</text>
    <circle cx="260" cy="120" r="14" fill="#fff" stroke="#333" stroke-width="1.5"/>
    <text x="260" y="125" text-anchor="middle" font-size="11">2</text>
    <circle cx="360" cy="100" r="14" fill="#fff" stroke="#333" stroke-width="1.5"/>
    <text x="360" y="105" text-anchor="middle" font-size="11">3</text>
    <text x="378" y="105" font-size="10" fill="#666">θ=1</text>
    <line x1="278" y1="84" x2="342" y2="96" stroke="#333" stroke-width="1.5" marker-end="url(#arr)"/>
    <line x1="278" y1="116" x2="342" y2="104" stroke="#333" stroke-width="1.5" marker-end="url(#arr)"/>
    <text x="320" y="155" text-anchor="middle" font-size="11">(b) OR (threshold 1)</text>
  </g>

  <!-- (c) AND -->
  <g>
    <circle cx="460" cy="80" r="14" fill="#fff" stroke="#333" stroke-width="1.5"/>
    <text x="460" y="85" text-anchor="middle" font-size="11">1</text>
    <circle cx="460" cy="120" r="14" fill="#fff" stroke="#333" stroke-width="1.5"/>
    <text x="460" y="125" text-anchor="middle" font-size="11">2</text>
    <circle cx="560" cy="100" r="14" fill="#fff" stroke="#333" stroke-width="1.5"/>
    <text x="560" y="105" text-anchor="middle" font-size="11">3</text>
    <text x="578" y="105" font-size="10" fill="#666">θ=2</text>
    <line x1="478" y1="84" x2="542" y2="96" stroke="#333" stroke-width="1.5" marker-end="url(#arr)"/>
    <line x1="478" y1="116" x2="542" y2="104" stroke="#333" stroke-width="1.5" marker-end="url(#arr)"/>
    <text x="520" y="155" text-anchor="middle" font-size="11">(c) AND (threshold 2)</text>
  </g>

  <!-- (d) AND-NOT -->
  <g>
    <circle cx="160" cy="240" r="14" fill="#fff" stroke="#333" stroke-width="1.5"/>
    <text x="160" y="245" text-anchor="middle" font-size="11">1</text>
    <circle cx="160" cy="290" r="14" fill="#fff" stroke="#333" stroke-width="1.5"/>
    <text x="160" y="295" text-anchor="middle" font-size="11">2</text>
    <circle cx="280" cy="265" r="14" fill="#fff" stroke="#333" stroke-width="1.5"/>
    <text x="280" y="270" text-anchor="middle" font-size="11">3</text>
    <text x="298" y="270" font-size="10" fill="#666">θ=1</text>
    <line x1="178" y1="244" x2="262" y2="261" stroke="#333" stroke-width="1.5" marker-end="url(#arr)"/>
    <line x1="178" y1="286" x2="262" y2="269" stroke="#333" stroke-width="1.5" marker-end="url(#inh)"/>
    <text x="220" y="325" text-anchor="middle" font-size="11">(d) AND-NOT (inhibition)</text>
    <text x="220" y="340" text-anchor="middle" font-size="10" fill="#555">N₃(t) ≡ N₁(t−1) ∧ ¬N₂(t−1)</text>
  </g>

  <!-- legend -->
  <g transform="translate(420, 220)">
    <line x1="0" y1="20" x2="40" y2="20" stroke="#333" stroke-width="1.5" marker-end="url(#arr)"/>
    <text x="50" y="24" font-size="11">excitatory</text>
    <line x1="0" y1="45" x2="40" y2="45" stroke="#333" stroke-width="1.5" marker-end="url(#inh)"/>
    <text x="50" y="49" font-size="11">inhibitory</text>
  </g>
</svg>

Every TPE is a finite tree of these operations applied to delayed inputs. Build the tree, replace each operation with its primitive net, and you have a feedforward net that realizes the expression. The induction runs on formula depth.

**Any Boolean function of past inputs you can name, some feedforward net computes.** The brain (under these assumptions) is not less expressive than the propositional calculus; it is exactly as expressive.

The illusion of *paradoxical heat* gets used as a worked example. Hold a cold object briefly to the skin and you feel heat; hold it longer and you feel only cold. With one heat receptor, one cold receptor, and a small acyclic net of AND, OR, and AND-NOT gates with delays, you can construct the firing pattern the perception requires. The point is not the neurophysiology — it's that the perceptual fact and the wiring diagram are now the same kind of object.

## The equivalence theorems — the model is robust

The paper has been making one set of assumptions about how neurons work. Are those the right ones? McCulloch and Pitts answer: *it doesn't matter.* A series of theorems shows that the obvious alternatives are equivalent — every behavior realizable under one assumption is realizable under any other, possibly with a different net, possibly with a different time delay.

**Theorem 4.** *Relative inhibition and absolute inhibition are equivalent.* If an inhibitory synapse just *raises* the threshold (rather than vetoing absolutely), some other net does the same thing.

**Theorem 5.** *Extinction is equivalent to absolute inhibition.* If a recently-fired neuron has a temporarily-raised threshold (a kind of refractory effect), that, too, can be replaced by inhibitory wiring.

**Theorem 6.** *Temporal summation can be replaced by spatial summation.* If real neurons accumulate excitation over short intervals, you can simulate it with delaying chains feeding into a threshold gate.

These theorems are the paper protecting itself from being beaten by future neurophysiology. **Whatever the brain turns out to actually do at the synapse level, the logical calculus survives** — the wiring diagram absorbs the difference. This is what they mean by *equivalent in the extended sense*: same input-output relation, perhaps a different number of synaptic delays.

## Theorem 7 — learning is recurrence

Then the unexpected one:

**Theorem 7.** *Alterable synapses can be replaced by circles.*

The assumption that net structure is fixed (assumption 5) seemed to rule out learning. It doesn't. A learning rule that strengthens an axonal terminal whenever it fires concurrently with the postsynaptic neuron — the proto-Hebb rule, six years before Hebb writes it down — is *equivalent* to a fixed net containing the right loop. The "learned" synapse is replaced by a circular subnet that, once excited together with the postsynaptic neuron, keeps a memory of that pairing alive in its own reverberating activity.

This is the move that makes the rest of the paper possible. It says: **memory and learning are not separate phenomena that the model can't reach. They are recurrent structure.** Anything that looks like long-term change in a feedforward net is short-term activity in a net with circles. So the question of what the brain can do becomes: what can nets with circles do?

## Nets with circles — recursion enters

Acyclic nets only refer to a finite past — at most as far back as the longest delay path. Once you allow circles, signals can reverberate, and the net can refer to arbitrarily distant past events. The proposition expressed by a cyclic net's firing isn't just a Boolean function of the last few input bits; it's a *recursive function* of the entire history.

The math gets heavy. McCulloch and Pitts solve cyclic nets by reducing them to a system of equations among the cyclic neurons (Theorem 8), then characterize which logical expressions are realizable by such nets (Theorems 9–10). The exact form of the characterization is dense, but the upshot is clean: **the class of behaviors realizable by neural nets with circles is exactly the class of behaviors a Turing machine can produce with the same inputs and outputs** — modulo whether you give the net a tape.

Their closing remark, from the body of the paper:

> Every net, if furnished with a tape, scanners connected to afferents, and suitable efferents to perform the necessary motor-operations, can compute only such numbers as can a Turing machine; and each of the latter numbers can be computed by such a net.

A net of these idealized neurons, augmented with memory, is *computationally equivalent to a Turing machine.* This is a 1943 paper — Turing's "On Computable Numbers" is only seven years old. McCulloch and Pitts are saying: the natural model of the nervous system, taken seriously as a logical object, lands exactly on the universal computing machine. Not by analogy. Provably.

## The epistemology kicker

The last section ("Consequences") is short and gets philosophical fast. Two pieces stand out.

**Knowledge is incomplete by construction.** From the structure of the model, you can compute the next state from the current state, but you can't run backward — disjunctions destroy information. Circles make reference to past events indefinite. So even a fully-specified brain in a fully-specified world doesn't yield a complete picture of either past or environment. *Our knowledge of the world, including ourselves, is incomplete as to space and indefinite as to time.* This is forced by the model, not added to it.

**No net, no fact.** Every idea, every sensation, every perception is realized as activity within the net. Change the net — tinnitus, paresthesias, hallucinations, delusions, disorientation — and the facts the net was reporting on go with it. *If our nets are undefined, our facts are undefined, and to the "real" we can attribute not so much as one quality or "form."* Kant's *thing in itself* is now a wiring question.

**Psychons.** Earlier psychologists used "psychon" loosely to name the elementary mental unit. McCulloch and Pitts pin it down: a psychon is no less than the activity of a single neuron. Since neural activity is inherently propositional, *all psychic events have an intentional, or semiotic, character* — they're about something, in the way propositions are. Psychology, on this model, is two-valued propositional logic running on biological substrate.

## What the paper installs in the canon

- **Neuron-as-proposition.** The single move the rest of computational neuroscience inherits.
- **Threshold logic as the formal object.** Perceptrons, logistic regression, ReLU networks — all are continuous relaxations of this.
- **Time as discrete synaptic ticks.** RNNs, transformers, every model with a step parameter inherits this.
- **Equivalence theorems as model robustness.** The pattern of "this seeming alternative is really the same calculus" reappears in every later abstraction over neural substrate.
- **Learning = recurrence (Theorem 7).** The deep reason memory and computation are not separable — held by every recurrent architecture, every transformer with KV cache, every model where state is structure.
- **Turing-completeness of recurrent nets with tape.** The result rediscovered by Siegelmann and Sontag for RNNs (1991, with reals); used by every "transformers are Turing-complete with enough scratch tokens" argument since.
- **Net-as-substrate-of-experience.** The epistemic claim that runs from McCulloch through Maturana to predictive processing: what we know is what the net realizes, and only that.

## What's missing — for the modern reader

What the paper does *not* contain is striking once you list it:

- **No learning rule.** Theorem 7 says learning is equivalent to recurrence, but doesn't say how a brain *acquires* the right recurrence. Hebb (1949), Rosenblatt (1958), backpropagation (1986).
- **No analog values.** Everything is 0/1. Continuous weights are a later concession to gradient-based optimization.
- **No noise.** The model is deterministic. Stochastic neurons (Boltzmann machines), dropout, sampling all come much later.
- **No architecture beyond "wire it up."** The systematic study of architectures — feedforward layers, convolutional structure, attention — is a half-century away.

The paper is the seed, not the tree. But the seed contains every later branch as a constraint: anything you build on neural substrate inherits the all-or-none assumption (or relaxes it explicitly and pays a price), the discrete-time tick (or claims continuous time and pays a price), the proposition-per-neuron view (or has to articulate what it's replacing it with).

## Connections in this canon

- **[Wiener Ch 4 — Feedback and Oscillation](../wiener-ch4/).** Both papers (1943, 1948) treat nervous activity as a system to be analyzed mathematically. McCulloch-Pitts treats firing patterns; Wiener treats stability over loops. The two pictures compose: a net of M-P neurons in a Wiener feedback loop is the substrate of the cerebellar tremor's mathematical description.
- **[Ashby Ch 3 — The Determinate Machine](../ashby-ch3/).** Ashby's framework — state, transformation, closure — is general enough to contain M-P nets as a special case (states = firing patterns, transformation = the wiring's update rule). Ashby's chapter is the abstract substrate; McCulloch-Pitts is one concrete instance.
- **[Conant & Ashby — Every Good Regulator Must Be a Model](../conant-ashby-good-regulator/).** The C-A theorem says a good regulator must instantiate a model of its environment. M-P gives the *medium* in which such a model can be instantiated in a brain: a net of threshold-logic neurons. The two together — *what brains compute = propositional logic over time, and what they must compute = models of the world* — frame the brain-as-model picture that runs through Helmholtz to predictive processing.

## What I cut

- Most of the formal apparatus from Section 3 (Theorems 8–10): the recursion-theoretic characterization of realizable expressions, the prehensible classes, the residue arithmetic in equation (9). The technical claim survives in the prose ("nets with circles = recursive functions = Turing-equivalent with tape"); the manipulations don't earn their keep for a non-specialist read.
- The Carnap/Russell-Whitehead notation digression — interesting historically (Pitts had a working knowledge of *Principia*-style logic at 20), but the calculus is more legible in modern symbols.
- Section-numbered subdivisions (§1, §2, §3, §4) replaced by topical headings.
- The full enumeration of Figure 1 (la–li) — kept only the load-bearing primitives (a–d) in the SVG, dropped (e–i) which were illustrative compositions.
- The neurophysiology asides on "internuncial neurons" and inhibitor-substance hypotheses — not load-bearing once the equivalence theorems collapse the alternatives.

## What I added

- Bold load-bearing one-liners marking the punchlines (the proposition move, every TPE is realizable, learning = recurrence, Turing-equivalence).
- The "What the paper installs in the canon" section explicitly tying each result to a downstream inheritance, since the paper's significance is largely downstream.
- The "What's missing" enumeration, which the original couldn't write because it was 1943.
- The SVG of the four primitive nets, which the original had as Figure 1 panels (a)–(d) in heavily mid-century typography.

## Structure choice

**Linear-cumulative.** McCulloch and Pitts' argument *accumulates*: assumptions → calculus → feedforward equivalence → robustness → learning-as-recurrence → cyclic nets → Turing equivalence → epistemic consequences. Each result depends on the prior ones. The chapter description on chainlink (#211) called it correctly — this is a derivation paper, and chiasm imposed on a derivation makes the math harder to follow. The structure is the proof.
