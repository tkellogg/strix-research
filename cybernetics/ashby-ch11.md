---
layout: default
title: Ashby Ch 11 — Requisite Variety
date: 2026-05-19
source: W. Ross Ashby, *An Introduction to Cybernetics* (Chapman & Hall, 1956), Chapter 11 — "Requisite Variety", pp. 202–218. PDF at pespmc1.vub.ac.be/books/IntroCyb.pdf
mode: chiastic
permalink: /cybernetics/ashby-ch11/
---

# Ashby Ch 11 — Requisite Variety

*Chiastic rewrite of W. Ross Ashby's "Requisite Variety" (1956). The chapter opens by setting regulation aside to watch two players at a game table, develops a theorem about that game, and closes by realizing the game was regulation all along — and then that perfect regulation gives perfect control. Source vocabulary preserved: variety, requisite variety, disturbance, regulator, outcome, essential variable, channel, capacity, vector, entropy.*

[← Cybernetics index](/cybernetics/)

---

## Forget regulation — watch the game

Two players, D and R, sit across a table. They both see the same grid:

|       | α | β | γ |
|-------|---|---|---|
| **1** | b | a | c |
| **2** | a | c | b |
| **3** | c | b | a |

D plays first, picking a row. R plays second, knowing D's row, picking a column. The letter at the intersection is the **outcome**. R wants the outcome to be *a*. If it is, R wins.

Inspect the table. R can always win. Whatever D plays, R has a column move that lands on *a*. R isn't just winning, either — by changing the strategy, R could force *b* or *c* at will. **R has complete control over the outcome.**

That's a peculiarly favorable table. Most tables aren't like that.

Here's another, with five rows for D and four columns for R:

|       | α | β | γ | δ |
|-------|---|---|---|---|
| **1** | b | d | a | a |
| **2** | a | d | a | d |
| **3** | d | a | a | a |
| **4** | d | b | a | b |
| **5** | d | a | b | d |

If R wants *a*, R can still win — every row has at least one *a*. If R wants *b*, R loses whenever D plays 3 (no *b* in that row). If R wants *c*, R is helpless — D wins every time.

Different table arrangements give different prospects for R. The interesting question is whether anything general can be said.

## The bound that falls out of the table

Strip out the easy cases — any table where a column repeats outcomes lets R get away with a sloppy strategy (the same R-move covers multiple D-moves). What's left is the case where every column has every outcome distinct. Then R must respond differently to each different D-move. Knowing D's move is essential; no shortcut.

In such a table, R picks one outcome per row — that's R's strategy. The question is how small a set of outcomes R can force, given that D may play every row eventually.

The argument is elementary. R marks an outcome in row 1. To avoid adding a new outcome in row 2, R has to change columns (because in the original column the elements are all different by hypothesis). Same for row 3. R can keep the variety at one outcome only by changing columns every row — and R has only as many columns as moves. Once the columns are exhausted, R must repeat a column, and a new outcome enters the set.

If the table has *r* rows (D's variety) and *c* columns (R's variety), the variety in the outcomes R can force is at least *r/c*. Take logs (which is what's almost always convenient) and:

**V_O ≥ V_D − V_R**

Variety in the outcome is at least D's variety minus R's variety. The only way to push outcome variety down is to push R's variety up by the same amount.

That's the **Law of Requisite Variety**.

The picturesque form: **only variety in R can force down the variety due to D. Variety can destroy variety.**

## What the law is, and isn't

The law isn't about matter. It isn't about machines. It isn't about brains, organisms, ecosystems, or markets. It's a statement about what arrangements of a rectangular table are possible. No experiment can overthrow it, in the same sense that no experiment can overthrow "three objects can't be arranged as a square."

This is the law's strength and its weirdness. It applies anywhere there's a structure with the shape of the game — D varies, R responds, an outcome happens — regardless of what the boxes contain. The substrate doesn't matter. Only the variety counts.

## Same theorem, Shannon's version

The tabular form is one face of the law. Spread the fluctuation out over time and let D, R, E (the outcome) be incessant information sources, and the same theorem comes back in entropy:

**H(E) ≥ H(D) − H(R)**

Same shape: the entropy in the outcomes has a floor set by D's entropy minus R's entropy. To push the floor down, raise R's entropy.

This is the form that matches **Shannon's Theorem 10** about correction channels: if a message is corrupted by noise, the noise that a correction channel can remove is bounded by the channel's capacity. Map disturbance → noise, regulator → correction channel, constant outcome → zero-entropy message. The diagrams are the same diagram.

## The game was regulation all along

Now go back and notice what the players actually were.

There's a set of **disturbances** D arriving from outside the organism. There's a set of **essential variables** E that have to stay in a narrow acceptable range η for the organism to live. Between D and E sits the world — call it **T**, the table — which would, left alone, let D's variety push E outside η.

The **regulator** R sits between D and T. R reads D and acts so that, after T does its thing, E stays in η. The diagram of immediate effects:

<svg viewBox="0 0 320 140" xmlns="http://www.w3.org/2000/svg" style="max-width:480px;display:block;margin:1em auto;">
  <defs>
    <marker id="arrow" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0 0 L 10 5 L 0 10 z" fill="#333"/>
    </marker>
  </defs>
  <circle cx="40" cy="70" r="24" fill="none" stroke="#333" stroke-width="2"/>
  <text x="40" y="76" text-anchor="middle" font-family="serif" font-size="20">D</text>
  <circle cx="160" cy="30" r="24" fill="none" stroke="#333" stroke-width="2"/>
  <text x="160" y="36" text-anchor="middle" font-family="serif" font-size="20">R</text>
  <circle cx="160" cy="110" r="24" fill="none" stroke="#333" stroke-width="2"/>
  <text x="160" y="116" text-anchor="middle" font-family="serif" font-size="20">T</text>
  <circle cx="280" cy="70" r="24" fill="none" stroke="#333" stroke-width="2"/>
  <text x="280" y="76" text-anchor="middle" font-family="serif" font-size="20">E</text>
  <line x1="60" y1="60" x2="140" y2="38" stroke="#333" stroke-width="2" marker-end="url(#arrow)"/>
  <line x1="60" y1="80" x2="140" y2="105" stroke="#333" stroke-width="2" marker-end="url(#arrow)"/>
  <line x1="180" y1="42" x2="245" y2="65" stroke="#333" stroke-width="2" marker-end="url(#arrow)"/>
  <line x1="180" y1="100" x2="245" y2="78" stroke="#333" stroke-width="2" marker-end="url(#arrow)"/>
</svg>

D feeds R; D and R together feed T; T produces E. Read it from the outside: D is variety entering, E is variety remaining after R and T have done their work.

The law applies to R as a channel: **R's capacity as a regulator cannot exceed R's capacity as a channel of communication.** The amount of disturbance R can neutralize is bounded by how much information about D can flow through R.

Now everything about the table game maps back. Restricting to columns-without-repeats was the condition that R has full information about D. The bound V_O ≥ V_D − V_R was already the bound on disturbance suppression. Calling it "regulation" was added vocabulary — the mathematics was already done.

## The biological line, and the dictator

A species survives, primarily, by blocking the flow of variety to the gene-pattern. The gene-pattern is the essential variable; the world is the disturbance. Everything between — sense organs, nervous system, behavior — is regulator. Sensitive skin, responsive nerves, curiosity that drags more variety into the system than is immediately needed: this looks like the organism inviting disturbance, but the law explains it. The only way to push down the disturbance reaching the gene-pattern is to take a lot of variety into the organism as **information** and use it inside R to cancel the disturbance arriving through T. The two flows aren't competitors; the inside flow is what kills the outside flow.

In its simple form, the law is intuitively obvious and barely worth stating. A press photographer who needs to shoot twenty distinct subjects (different exposures, different distances) needs a camera with at least twenty distinct settings if all the negatives are to come out uniformly exposed and sharp. Of course.

In its quantitative form, the law develops its power on systems large enough that intuition fails. **How much could a dictator control a country? It is commonly said that Hitler's control over Germany was total. So far as his power of regulation was concerned, the law says that his control amounted to just 1 man-power, and no more.** One person can carry a bounded amount of information per unit time; the disturbances threatening a country vastly exceed that. Whether the literal claim is true is for the future to decide; its virtue now is being exact and uncompromising.

## Regulation becomes control

Suppose R is a perfect regulator. Then E equals whatever target was set, regardless of D. So if some outsider C decides what the target should be — *a* this round, *b* next round, then a sequence — and feeds that decision into R, the outsider gets exactly that sequence at E. The diagram now has two independent inputs:

```
D → T → E
       ↑
C → R
```

C controls E completely, despite D's interference. **Perfect regulation of the outcome by R makes possible complete control over the outcome by C.**

Read the other direction: if C wants to control E and there's a noisy channel D corrupting the signal, then the way to recover control is to interpose R, taking inputs from both C and D. R isn't replacing the channel; it's the only thing that lets C's variety arrive at E intact.

Control depends on regulation. The two are the same theorem read with different boxes labeled differently.

## What "constant" really means

The chapter's emphasis on holding outcomes constant can mislead. Living organisms are not, in general, immobile.

A searchlight tracking an aircraft swings through a large range of angles relative to the earth — and holds, throughout, an angle of zero relative to the aircraft. Both descriptions are correct; they refer to different variables. A driver steering a car along a winding road makes constant adjustments to the wheel — and holds, throughout the trip, the distance between car and verge nearly constant.

Many activities of living organisms have this double aspect. From outside you see motion; relative to the right variable you see constancy. The whole apparatus of the law — "hold E inside η" — covers tracking, copying, anti-copying, and arbitrarily complex relations between variables, by letting η be whatever shape it needs to be. "Make x do whatever y does" is "hold x − y at zero." "Make w track twice v's rate of change" is "hold w − 2 dv/dt at zero." Constant-at-zero of the right derived variable IS the behavior.

## What the basic formulation already covers

The single-D, single-R, single-T setup looks too simple to be general. It isn't:

- **Multiple disturbances?** Let D be a vector. A cyclist dealing with traffic and gusts has a two-component D.
- **Noisy T?** The boundary between D and T was provisional. Re-draw it to absorb the noise into D. Then T has no extra input; the formulation holds.
- **Initial-state dependence?** Let D's vector include T's initial state.
- **Compound targets** (the thermostat must hold 36–37°C and return within a minute if displaced by 10°)? Let E be a vector and let η specify each component separately.
- **Interacting regulations** (a signalman handling several trains as a pattern)? Nothing requires D, R, T, E to be internally simple. Single letters represent vectors of arbitrary complexity.

The basic formulation is capable, in principle, of including cases of any degree of internal complexity. **Wherever there is a disturbance, a regulator, and an outcome to be held in a target set, the law applies and the bound holds.**

---

## What I cut / what I added / structure choice

**Structure:** chiasm — A (set aside regulation, watch a game) → B (game has a bound: V_O ≥ V_D − V_R) → C (entropy version, same theorem) → C' (game IS regulation, R is a channel) → B' (regulation → control, perfect regulator gives complete control) → A' (the basic formulation covers compound disturbance, noise, vectors — back to the world). The chapter's argument inverts midway: the abstract game turns out to have been regulation the whole time. Chiasm fits.

**Cut:**
- All 21 section numbers (11/1 through 11/21)
- All 11 exercises (the cyclist, the insect's optic nerve, the ship's telegraph, the general with 10 divisions)
- §11/8's full Shannon-entropy derivation — kept the resulting inequality H(E) ≥ H(D) − H(R) but dropped the H(R,E), H(D,R) algebra steps
- §11/9's k-repetition extension — adds nothing the core theorem doesn't already say
- §11/10's repeat-defense of the law's mathematical status — said once
- §11/12's Sommerhoff "directive correlation" comparison table — historical aside
- §11/13's extended press-photographer/Hitler discussion compressed; kept Hitler line (it's the chapter's killer)
- §11/15's three additional searchlight/driver/x−y examples — kept the first two
- §11/16–21 (Variations) compressed to a single bulleted paragraph

**Added:**
- SVG of the D→R→T→E immediate-effects diagram (source has it as ASCII; SVG renders cleanly)
- Bold on the load-bearing one-liners: "variety can destroy variety," "Hitler's control amounted to just 1 man-power," "perfect regulation makes complete control possible," "R's capacity as a regulator cannot exceed R's capacity as a channel"
- The "game IS regulation" frame inversion is sharpened — Ashby's source telegraphs the move; the chiastic rewrite makes it the structural pivot

**Preserved:**
- Both example tables (Table 11/3/1 perfect-control and 11/4/1 partial-control) reproduced
- Core inequality V_O ≥ V_D − V_R in both log and entropy form
- Connection to Shannon's Theorem 10 (correction channels)
- The gene-pattern / sensitive-skin / curiosity discussion
- Searchlight and driver examples (both forms of "constant")
- The list of what the basic formulation covers (compound disturbance, noise, initial state, compound target, internal complexity)

**Source:** ~6000 words → ~1700 words (~28%). On target.
