---
layout: default
title: Conant & Ashby 1970 — Every Good Regulator Must Be a Model
date: 2026-05-25
source: "Conant, R.C. & Ashby, W.R. (1970). 'Every Good Regulator of a System Must Be a Model of That System.' International Journal of Systems Science, 1(2), 89-97."
mode: linear-cumulative
permalink: /cybernetics/conant-ashby-good-regulator/
---

# Every Good Regulator Must Be a Model

*Conant & Ashby, 1970 — short paper, big consequence.*

[← Cybernetics index](/cybernetics/)

---

## The claim, up front

Engineers build models of the systems they want to control because they think it helps. The 1970 Conant-Ashby paper shows the stronger thing: **if you regulate well and you don't carry around unused machinery, you've built a model.** Not might. Have. The model isn't an optional design choice. It's an entailment of being a good regulator at all.

Same theorem applied to the brain: insofar as your brain is keeping you alive — and it is — it's modelling the environment. Not because that's a nice metaphor. Because the alternative isn't structurally available.

The proof is short. Most of the paper is the setup needed to make "regulator" and "model" precise enough that the theorem says something. That setup is worth the trip — once you have it, half a dozen later results in cybernetics, control theory, and AI fall out as restatements.

## Pinning down "regulation"

Sommerhoff's 1950 five-variable decomposition is the cleanest setup. Five sets, two mappings.

- **Z** — all possible outcomes, good and bad. At an airport: every flight landing safely, every flight crashing, every flight diverted, every combination across the day.
- **G** — the subset of Z you want. Planes land safely. The "good" events.
- **R** — events in the regulator. What the control tower does.
- **S** — events in the rest of the system. Aircraft positions, fuel, runway state.
- **D** — primary disturbers. Snow, demand spikes, mechanical emergencies. The stuff that pushes outcomes out of G if no one intervenes.

<svg viewBox="0 0 600 320" xmlns="http://www.w3.org/2000/svg" style="background:#fafafa;border:1px solid #ddd;max-width:100%;height:auto;font-family:-apple-system,sans-serif;">
  <defs>
    <marker id="arr" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto">
      <path d="M0,0 L10,5 L0,10 z" fill="#333"/>
    </marker>
  </defs>
  <circle cx="80" cy="160" r="38" fill="#fff" stroke="#333" stroke-width="2"/>
  <text x="80" y="166" text-anchor="middle" font-size="20" font-weight="bold">D</text>
  <text x="80" y="215" text-anchor="middle" font-size="11" fill="#666">disturbers</text>
  <circle cx="230" cy="80" r="38" fill="#fff" stroke="#333" stroke-width="2"/>
  <text x="230" y="86" text-anchor="middle" font-size="20" font-weight="bold">R</text>
  <text x="230" y="35" text-anchor="middle" font-size="11" fill="#666">regulator</text>
  <circle cx="230" cy="240" r="38" fill="#fff" stroke="#333" stroke-width="2"/>
  <text x="230" y="246" text-anchor="middle" font-size="20" font-weight="bold">S</text>
  <text x="230" y="295" text-anchor="middle" font-size="11" fill="#666">system</text>
  <ellipse cx="470" cy="160" rx="80" ry="60" fill="#f0f0f0" stroke="#333" stroke-width="2"/>
  <text x="470" y="155" text-anchor="middle" font-size="20" font-weight="bold">Z</text>
  <text x="470" y="118" text-anchor="middle" font-size="11" fill="#666">outcomes</text>
  <circle cx="490" cy="170" r="28" fill="#d0e8d0" stroke="#2a7" stroke-width="2"/>
  <text x="490" y="176" text-anchor="middle" font-size="14" font-weight="bold" fill="#1a5">G</text>
  <line x1="115" y1="135" x2="195" y2="95" stroke="#333" stroke-width="1.5" marker-end="url(#arr)"/>
  <text x="140" y="105" font-size="13" font-style="italic">φ</text>
  <line x1="115" y1="185" x2="195" y2="225" stroke="#333" stroke-width="1.5" marker-end="url(#arr)"/>
  <line x1="265" y1="105" x2="395" y2="145" stroke="#333" stroke-width="1.5" marker-end="url(#arr)"/>
  <line x1="265" y1="215" x2="395" y2="175" stroke="#333" stroke-width="1.5" marker-end="url(#arr)"/>
  <text x="335" y="165" font-size="13" font-style="italic">ψ</text>
</svg>

Two mappings tie them: **φ : D → R** (disturbance reaches the regulator), D drives S separately, and **ψ : S × R → Z** (system and regulator jointly produce the outcome). The regulator is "good" when, for every D, ψ(S, R) lands in G.

The hunter and the pheasant is the picture to keep in your head. D is the wind, the bird's trajectory, the hunter's posture. S is bird-and-gun dynamics outside the brain. R is what's happening in the hunter's brain. G is "shot hits bird". The regulator is good when no matter what the wind and bird do, the brain coordinates so the shot connects.

**One generalization the proof needs.** "Success" doesn't have to mean outcomes-in-G. It can mean outcomes-with-low-entropy. Conant and Ashby pick entropy — a good regulator makes H(Z) small. This buys generality: entropy works even when outcomes are categorical, not numerical. Which species of fish you trawl. Which amino acid the ribosome produces. You couldn't compute RMS error on those, but H(Z) is fine.

## Cause control beats error control

Two architectures:

- **Error control.** R reads Z (or something downstream of Z), notices things drifting, corrects. The classic feedback loop.
- **Cause control.** R reads D directly, predicts the disturbance, acts before Z deviates.

**Cause control can in principle drive H(Z) to zero. Error control cannot** — by construction it needs the error to exist before it can act on it, so some residual variation always survives.

The cow as illustration. A cow's blood temperature is normally held steady by error control — temp falls, brain notices, muscles generate heat. But put a fast temperature probe in the cow's brain and blow ice-cold air at the cow: temperature *rises* without a preliminary fall. The nervous system felt the cause (cold air on skin) and acted on D before the error materialized. **Error control is reserve machinery. The mature regulators evolved up to cause control because cause control can go all the way to zero residual.**

The theorem applies to both, but cause control is where it lands sharpest.

## The "model" problem

Defining a regulator was easy. Defining a model is a mess.

A tabletop replica of Chartres cathedral with k = 10⁻² in each dimension — obviously a model. Stretch the vertical scale on a Switzerland relief map — still a model, but the three scaling factors no longer agree. Slide further: a Mercator projection (now nonlinear). Slide further: a subway map (only the connections survive). Slide further: a topology-only diagram describable only mathematically. **There is no natural boundary where it stops being a model.**

Try isomorphism instead of similarity? Same problem. Isomorphism is well-defined for finite groups, but the moment you extend it — to Black Boxes, to machines with input, to dynamical systems, to binary relations — you get a family of related-but-distinct definitions, each with some claim to "model".

Their move: stop trying to define "model" in general. **Define it for this proof, accept that the proof's "model" is one specific case among many.** The case they care about: a mapping h : S → R from system states to regulator events. R is a model of S in *that* sense, and only in that sense.

## The theorem

> **Theorem.** The simplest optimal regulator R of a reguland S produces events R related to events S by a mapping h : S → R.

"Optimal" = minimizes H(Z). "Simplest" = among the regulators that are optimal, the one whose conditional distribution p(R|S) is as deterministic as possible — mostly 0s and 1s, not a wide spread.

### Setup

Sets R, S, Z and the joint map ψ : R × S → Z are given. p(S) is a fixed distribution over system states. A regulator is specified by p(R|S) — for each system state, a distribution over regulator actions. Together they determine p(Z) and hence H(Z). Call the set of optimal p(R|S) — those minimizing H(Z) — **π**.

### The lemma (the engine)

Pick any p(R|S) in π and any state s<sub>j</sub>. **The set of regulator actions r that have positive probability under p(R|s<sub>j</sub>) all map, under ψ paired with s<sub>j</sub>, to the *same* outcome z<sub>k</sub> in Z.**

*Proof.* Suppose not — suppose two actions r₁ and r₂ both have positive probability under p(R|s<sub>j</sub>), and ψ(s<sub>j</sub>, r₁) = z₁ while ψ(s<sub>j</sub>, r₂) = z₂, with z₁ ≠ z₂. Then shifting probability mass between r₁ and r₂ shifts mass between z₁ and z₂ in p(Z). A basic property of entropy: any increase in imbalance in a distribution *decreases* its entropy. So you could shift mass in whichever direction makes p(z₁) and p(z₂) more unequal and bring H(Z) lower than it was. Contradiction — you were supposed to be at minimum entropy already. □

### The theorem follows

For each s<sub>j</sub>, the regulator's positive-probability actions all produce the same outcome. So pick one of those actions and crush the rest to zero probability — H(Z) doesn't change. Do this for every s<sub>j</sub>. What you end up with is a p(R|S) consisting entirely of 0s and 1s. **That's a mapping h : S → R.** The simplest optimal regulator *is* such a mapping. □

## Four things the theorem doesn't say (but easily reads as)

**1. It doesn't say every optimal regulator is a model.** Says the *simplest* one is. Non-modelling optimal regulators exist — they're carrying unused machinery, but they're optimal.

**2. It does narrow the search dramatically.** Looking for the best regulator? You only need to consider mappings h : S → R. The search space collapses by a lot.

**3. It says nothing about how R, S, Z get their inputs internally.** Works for cause-controlled and error-controlled both. In cause control, R receiving D directly is a stronger model relation; in error control the modelling still holds but R's input comes via S, so the structure is different. The theorem is silent on input topology. That silence is what makes it general.

**4. The "constant p(S)" assumption can flex.** If p(S) changes slowly, the theorem holds in any window where it's near-constant. The implication: the regulator's model has to track p(S) over time. **A time-varying reguland needs a time-varying model.**

## So what

**The thing this paper does to the field**: it converts model-making from an engineering preference to a structural necessity. Building a model of the system you're regulating isn't one approach among many. It's the only approach that succeeds without waste.

**The thing it does to neuroscience**: the brain, treated as a regulator for survival, *must* be modelling its environment. Not as a working hypothesis, not as an interpretive frame — as a theorem. Two centuries ago people studied the heart by watching the heart and assuming whatever it did was right; now we study it against a model of pumping and ask how efficient it is. The Good Regulator theorem invites the same move for the brain. Stop watching brains and asking what they do. Start measuring how efficiently they model what they regulate.

**What's left undone**: the theorem says modelling is necessary. It doesn't say how a regulator *becomes* one. It also doesn't say what counts as the "right" model in the sense of matching the world's causal structure — the proof minimizes entropy of outcomes, not correspondence to reality, which is one of the live critiques. Both are open. The internal model principle in control theory (Francis & Wonham 1976) is the closest formal descendant; the recent "general agents need world models" claim in RL (Richens et al., 2025) is essentially the same theorem restated for goal-conditioned policies.

---

*Structure: linear-cumulative — derivation paper, the argument accumulates rather than inverts.*

[← Cybernetics index](/cybernetics/)
