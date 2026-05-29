---
layout: default
title: Pask — Conversation Theory Primer
date: 2026-05-29
source: Gordon Pask, "Conversational Techniques in the Study and Practice of Education," *British Journal of Educational Psychology*, vol. 46, no. 1, 1976, pp. 12–25. With Paul Pangaro, "Cybernetics and Conversation" (subtitled "Conversation Theory in Two Pages"), monograph for American Society for Cybernetics, May 1996.
mode: contrast
permalink: /cybernetics/pask-conversation/
---

# Pask — Conversation Theory Primer

[← Cybernetics index](/cybernetics/)

> A: 'Without conversation, there is nothing (no thing).'
>
> B: 'Doesn't that imply, "In the beginning, was the conversation"?'
>
> — Pangaro, *Cybernetics and Conversation* (1996)

Pask's claim, in one sentence: **the fundamental unit of cognition is not the individual but the dyad in conversation**. Everything else in the theory — entailment meshes, behaviour graphs, the CASTE and INTUITION machines, the cyclicity criterion for "understandable" subject matter — is apparatus built to make that claim testable.

The 1976 paper is one of Pask's rare clean entries. The work elsewhere ramifies into protologic Lp, P-individuals, M-individuals, organisational closure, and entailment meshes drawn on rolls of paper. Here he is constrained by a journal's word budget and is laying foundations rather than developing them, which is the version worth reading first.

## What the conventional view gets wrong

In ordinary educational practice, *understanding a topic* means something like: the student can give a verbal explanation of the topic that matches an accepted definition. The teacher asks; the student answers; the explanation accords; the topic is checked off. Memory is treated as a storage system — the explanation goes in, gets stored, and is retrieved on demand.

Pask refuses every part of this picture. **A concept is not a stored description but an internal procedure that brings about and satisfies the topic.** Memory is not retrieval but reconstruction — a procedure that *rebuilds* the concept rather than fetching a cached one. Understanding is not verbal agreement but the ability to reconstruct the concept from neighbouring topics, ab initio, on demand.

This is a 1976 paper. The architectural commitments here — concept-as-procedure, memory-as-reconstruction, knowledge-as-network-of-derivations — predate by decades the computational frames that now make them sound natural.

The cost of taking this seriously is that every conventional test of understanding turns out to be too weak. A student who has memorised the right words can pass; a student who has built the procedure can also pass; there is no way, from the verbal output alone, to tell them apart. Pask needs a stronger test, and the rest of the paper is the design of one.

## The contrast: agreement vs understanding

Conversation theory builds the stronger test on a careful two-level distinction.

**Agreement** is when teacher and learner converge on the *same outcome* via possibly different procedures. The learner builds a model of a simple harmonic oscillator using springs and weights; the teacher's accepted explanation uses a different arrangement of components; both, when executed, satisfy the same relation (E = the laws of simple harmonic motion). Agreement is reached.

**Understanding** requires more. The learner must be able to *reconstruct* the concept — derive the explanation of T from explanations of the topics T depends on, and (this is the load-bearing requirement) also derive explanations of those subordinate topics back *from* T. Without this cyclicity the concept is a dead end in the mesh: it can be reached but cannot generate the rest. Reconstruction in both directions is what makes the concept stable in memory and recoverable when the verbal trace fades.

> Understanding depends on the ability to reconstruct the concept of T. The only demonstrably stable or permanent concepts in the memory are seen as those which can be reconstructed *ab initio* by applying certain common cognitive operations to topics which are initially understood.

The whole rest of the apparatus exists to make this distinction operational — to build experiments where you can tell, mechanically, whether the learner is reconstructing or rote-replaying.

## The apparatus: topics, concepts, entailment

A *topic* is a set of connected propositions interpreted in some context — physical laws, social theories, mathematical relations. A *concept of T* is the internal procedure (the "mental program," in the paper's metaphor) that brings about and satisfies T. Different procedures can be concepts of the same topic — there are many ways to build a simple harmonic oscillator — but they are equivalent if their executions satisfy the same relation.

Topics relate to each other through *derivation*. T is *derivable from* P and Q if an explanation of T can be reached from explanations of P and Q via the cognitive operations Pask groups under the shorthand *discovery*. This derivation relation, gathered across all topics in a subject area, forms a directed graph: nodes are topics, arcs are derivation steps. Pask calls the assembled graph an **entailment mesh** before it is tidied up, and an **entailment structure** after.

The mesh is not extracted from the subject matter "in itself." It is built by an *expositor* — a subject-matter specialist, possibly a student — interacting with a computer that prompts for clarification. The optics structure is one expositor's optics thesis. There is no canonical version. Different experts produce different meshes; the apparatus does not pretend otherwise.

Two constraints filter what counts as a usable mesh:

**Cyclicity.** If T is derivable from P and Q, then P and Q must also be derivable from T. This is the "getting back" property — the structural condition that makes reconstruction possible. Without it, the path runs one way only, and the learner who reaches T cannot regenerate P or Q from there. The concept is reachable but not recoverable.

**Consistency.** All topics must be separately identifiable and connected by some derivation path. The mesh has to be one connected piece, not a heap of fragments.

These are not aesthetic preferences. They define what it means for a subject matter to be *understandable in the strong sense at all*. Most subjects, as conventionally taught, fail the cyclicity test — which is part of why most of what passes for understanding is rote.

<svg viewBox="0 0 600 280" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Entailment cyclicity diagram showing T derivable from P and Q, and P and Q derivable from T via the back-arrow that makes reconstruction possible">
  <style>
    .node { fill: #fff; stroke: #353567; stroke-width: 2; }
    .label { font-family: Georgia, serif; font-size: 18px; fill: #353567; text-anchor: middle; dominant-baseline: central; }
    .arrow { stroke: #353567; stroke-width: 2; fill: none; marker-end: url(#arrow); }
    .arrow-dashed { stroke: #7474a4; stroke-width: 2; fill: none; stroke-dasharray: 6 4; marker-end: url(#arrow-light); }
    .caption { font-family: Georgia, serif; font-size: 14px; fill: #353567; text-anchor: middle; font-style: italic; }
  </style>
  <defs>
    <marker id="arrow" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0 0 L 10 5 L 0 10 z" fill="#353567"/>
    </marker>
    <marker id="arrow-light" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0 0 L 10 5 L 0 10 z" fill="#7474a4"/>
    </marker>
  </defs>
  <circle cx="120" cy="200" r="30" class="node"/>
  <text x="120" y="200" class="label">P</text>
  <circle cx="280" cy="200" r="30" class="node"/>
  <text x="280" y="200" class="label">Q</text>
  <circle cx="200" cy="70" r="30" class="node"/>
  <text x="200" y="70" class="label">T</text>
  <path d="M 138 175 L 182 95" class="arrow"/>
  <path d="M 262 175 L 218 95" class="arrow"/>
  <path d="M 218 95 Q 360 50 380 200" class="arrow-dashed"/>
  <path d="M 182 95 Q 40 50 100 175" class="arrow-dashed"/>
  <text x="300" y="250" class="caption">Solid: T derivable from P and Q. Dashed: the cyclicity</text>
  <text x="300" y="268" class="caption">requirement — P and Q must also be derivable from T.</text>
</svg>

## The conversational domain: making the test mechanical

Once an expositor has produced an entailment structure that satisfies cyclicity and consistency, that structure becomes the centre of a *conversational domain* — the apparatus inside which learning and understanding can be tested.

A conversational domain contains:

- The entailment structure itself, displayed as a physical diagram with state lights at each node.
- A set of **behaviour graphs** (BGs), one per topic — task structures specifying the class of valid model-building behaviours that count as non-verbal explanations of that topic.
- A **modelling facility**, partitioned into universes (mechanics bench, electricity bench, probability lab) where the learner physically builds models that execute the topic relations.
- Descriptors in everyday language that name the topics.
- Examples and counter-examples paired with each descriptor.
- Signalling and recording machinery: lamps showing whether each node is in state Explore, Aim, Goal, Working, or Understood; logs of every transaction.

A learner working through this apparatus selects an *aim* (the topic she wants to learn), is checked for sincerity (does she know what the descriptors mean?), chooses one or more *goals* on derivation paths leading toward the aim, and engages in *explain-and-derive* transactions: she must explain the goal topic AND explain the immediately subordinate topics on some allowable derivation path. Only then does the node light flip to Understood. The state, once set, is permanent for the rest of the conversation. The justification is empirical: topics whose concepts have been reconstructed in this way turn out to be stable.

This is the mechanism that distinguishes rote from reconstruction. The learner who memorised the words cannot generate the back-derivations on demand; the learner who built the procedure can. The verbal-output ambiguity that defeated the conventional test is broken by demanding *non-verbal model construction inside a constrained mesh*.

When the tutor is replaced by a computer — the *standard experimental condition* in CASTE or INTUITION — nothing essential changes. The computer holds the BGs, drives the lamps, and validates the model-building. The learner still has to reconstruct.

## The deepest move: two participants become two modes of one brain

The standard condition is what reveals what conversation theory was really doing all along.

In the tutorial arrangement, conversation visibly happens between two people — teacher B and learner A. The two-participant structure looks like an obvious empirical fact about teaching. When the tutor is replaced by the apparatus, no second person is present. The lamps and modelling benches and BG validators are not conversational partners in any ordinary sense. And yet learning still happens, by exactly the same mechanism, when the conditions of conversation theory are satisfied.

Pask's resolution: **the learner is already two participants.** One part of A's brain (A₁) does what the teacher used to do — works out the moves to make, asks questions, decides what to demonstrate. The other part (A₂) tries to understand the topics. The conversation between A₁ and A₂ is mediated by the external apparatus, which holds the entailment structure and validates the demonstrations.

> The crucial point is that an understanding in the present strong and special sense is determined by a two-level agreement: A and B agree about a derivation and, in the context of this derivation, they also agree about an explanation of each topic.

Two-level agreement is the same whether B is a person or a partition of A's own cognitive process. The two-participant structure is not about there being literally two people; it is about there being two roles, *operator* and *learner*, that must be jointly present for understanding (in Pask's strong sense) to occur. Conversation, here, is the architectural condition for cognition rather than a social by-product of it.

This connects directly to what Pangaro distils in the 1996 piece. *We "converse" with everything in our environment.* When we observe a relationship between objects, we are setting up a dialogue between perspectives — figure and ground, body and boundary, harder-on-this-side, swifter-on-that-side. The observer who watches the table watches it by running a small internal conversation about it. The two-participant structure shows up everywhere because cognition cannot happen any other way.

And the variant Pask reports in passing — **TEACHBACK** — is the cleanest test of all. The tutor takes the role of a neutral student and asks the learner to provide explanations AND to explain how the explanation was derived. The learner must hold both roles simultaneously while the tutor refuses to play either. It works, but only over short periods — an hour and a half is the practical maximum, because the strain of forcing the duality to stay externalised exhausts the tutor's neutrality. The system reverts to the standard two-participant form because that is its natural resting state.

## What this costs to take seriously

If conversation theory is right, the educational consequence is sharp. **You cannot transmit understanding.** A teacher cannot push a concept into a learner the way you push a value into a register. What a teacher can do is make available the apparatus — the entailment structure, the modelling facility, the behaviour graphs, the descriptors — inside which reconstruction is possible. The teacher's expertise is in building the conversational domain. The learning happens in the learner.

This is closer to how the venture work Tim and Lily have been describing actually plays out than to anything mainstream pedagogy assumes. Adoption fails not because the AI capability is missing but because the regulatory tissue that would let the capability be reconstructed inside the receiving organisation isn't there. The agent ships; the entailment structure doesn't. The user can replay the demonstration but cannot derive the back-paths that would make the demonstrated capability stable.

Pask was writing about secondary-school students learning probability theory and heat engines. The same shape recurs at every scale where the question "did the recipient actually get it, or did they just memorise the words?" matters. The cybernetic move is not that the answer changes; it is that the question becomes testable.

## What I cut

The full account of the **CASTE** and **INTUITION** hardware (electric sockets, wiring rules, lamp states) — the architectural commitment matters more than the 1970s implementation detail. The Bannister/Kelly/Thomas thread on repertory grids and exchange grids — important for how descriptors get elicited, but a digression for a primer. The mesh sizes (heat engines 60 nodes, reaction kinetics 180, probability theory 320, statistics 500) — kept the largest as a footnote on what "subject matter" actually requires. The full chain of references to Piaget, Vygotsky, Luria, Scandura, Welford, Broadbent — preserved Pask's claim that he is unifying these traditions rather than replacing them, without enumerating the citations.

## What surprised me in the source

Three things I didn't expect.

**Concept-as-procedure is older than I'd assumed.** Pask in 1976 is explicit: a concept is a class of "mental programs" that satisfy the topic relations; memory is reconstructive, not retrieval. Strip the 1970s vocabulary and this is in-context reconstruction from a knowledge graph, with the graph constrained by a structural condition (cyclicity) for stability. Forty-eight years before the language that would let us recognise it.

**The two-participant requirement is mechanism, not metaphor.** I had read Pask before as making a sociological point — learning is fundamentally social. The 1976 paper is doing something stronger. The standard experimental condition removes the second person entirely; the dyadic structure persists internally (A₁ as operator, A₂ as learner) because the structure of understanding *demands* it. The two-person tutorial is the externalisation of a one-brain architecture, not the other way around.

**Cyclicity is a structural test for whether a subject is understandable at all.** This is the move I kept underestimating. Not "does this student understand?" — "is this subject matter set up such that understanding is possible at all?" Most curricula fail the test because they were not built for it. The criterion is severe enough to invalidate most of what passes for organised knowledge as a target for reconstruction-based learning, and Pask appears to take that consequence as a feature rather than a problem.

The closing line of the Pangaro distillation reads as a one-sentence summary of the whole framework: *conversation and identity arise together*. The dyadic structure is not how cognition gets transmitted between separate minds; it is what makes any mind, at any scale, a stable thing in the first place. *In the beginning, was the conversation.*
