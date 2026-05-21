---
layout: default
title: Cybernetics Canon — Modern Reread
date: 2026-05-17
permalink: /cybernetics/
---

# Cybernetics Canon — Modern Reread

A chapter-a-day walk through the cybernetics canon, restructured for modern reading without information loss. Source text register-shifted; defined terms, math, and key illustrations preserved. Scaffolding (numbered subsections, exercises, "we now turn to" connective tissue) stripped.

**Method:** Pick the structure that fits each chapter — chiasm where the argument inverts a frame, linear-cumulative for derivations, contrast for dialectical chapters, spiral for layered re-encounters. The structure should fall out of the source, not be imposed on it. See [`chiastic-rewrite` skill](https://github.com/tkellogg/discord-letta-bot/blob/main/.claude/skills/chiastic-rewrite/SKILL.md).

**Cadence:** One chapter per day. Live status on [chainlink issues tagged `cybernetics-chapter`](https://github.com/tkellogg/discord-letta-bot/issues?q=is%3Aissue+label%3Acybernetics-chapter).

---

## Done

- **[Ashby *Design for a Brain* — The Ultrastable System (Homeostat)](ashby-homeostat/)** (May 21). Step-functions plus fields generate a selective process: an **ultrastable system** rejects fields that lead to a critical state and retains those that don't. Ashby builds the homeostat — four magnets in water troughs, uniselectors with Fisher-Yates random values, 390,625 combinations — to test the principle physically. The aileron analogy: ordinary stable systems persist in their wrong action; ultrastable systems change the field until it is stable. The closing test (a glass fibre joining two magnets) shows the machine adapting to a constraint that was never in its design spec. *Linear-cumulative.*
- **[Ashby Ch 4 — The Machine With Input](ashby-ch4/)** (May 20). Open: a crane controlled by a driver, parameters set from outside, deliberate switches. Hinge: feedback is dismissed as the central concept — "the exact definition of 'feedback' is nowhere important," and with more than a handful of parts complex systems must be treated as a whole, not as an interlaced set of loops. Close: the input picture inverts. In very large systems the locus of history is *local* — self-locking ratchets (the closed oysters) and breeding properties (*k* > 1, autocatalysis, Darwinian evolution). No operator, no switch, no input. *Chiasm.*
- **[Ashby Ch 6 — The Black Box](ashby-ch6/)** (May 19). Open: an engineer faces a sealed box. Close: every object is a Black Box; "what's inside" is the relation between observer and what is distinguished. Protocol → canonical representation → isomorphism (analogues) → homomorphism (models) → emergence as epistemic gap → memory as the trace of unobservable variables. *Chiasm.*
- **[Ashby Ch 5 — Stability](ashby-ch5/)** (May 19). The whole stack: equilibrium → cycle → stable set (closure) → stable under D → stable to a range of D → stable when coupled. The veto principle: a coupled whole rests only where every part can rest given what the others are doing. Homeostat falls out as a corollary. Positive feedback need not destabilise. *Linear-cumulative.*
- **[Ashby Ch 12 — The Error-Controlled Regulator](ashby-ch12/)** (May 19). Anticipatory regulator vs error-controlled regulator. The impossibility proof: the more R succeeds at holding E constant, the more it blocks the channel it needs. Continuity rescues the design; Markovian "hunt-and-stick" makes it tractable. Homeostat, telephone selector, blood-pH. *Contrast.*
- **[Ashby Ch 11 — Requisite Variety](ashby-ch11/)** (May 19). The Law: V_O ≥ V_D − V_R. Variety can destroy variety. The chapter sets aside regulation to watch a game, derives the bound, then reveals the game was regulation all along. R's capacity as regulator cannot exceed R's capacity as channel. Hitler's control = 1 man-power. *Chiasm.*
- **[Ashby Ch 3 — The Determinate Machine](ashby-ch3/)** (May 19). A machine is anything behaving like a closed single-valued transformation. State, operand, trajectory, canonical representation. Phase space makes the algebra visible. The closing inversion: a "system" is not a thing in the world, it is the list of variables we chose. *Contrast.*
- **[Ashby Ch 2 — Change](ashby-ch2/)** (May 18). Operand, operator, transform, transition. Closure as the prerequisite for repeated application. Kinematic graphs reveal basins of attraction the algebra hides. *Linear-cumulative.*
- **[Ashby Ch 7 — Quantity of Variety](ashby-ch7/)** (May 17). Variety as the count of distinguishable possibilities. The chair as constraint. Every law of nature is a constraint. *Chiasm.*

## Foundational

- Wiener, *Cybernetics* (1948) — selected chapters (Ch 1: Newtonian vs Bergsonian time; Ch 4: feedback and oscillation)
- Wiener, *Human Use of Human Beings* — see [interactive walkthrough](/wiener/)
- Ashby, *Introduction to Cybernetics* (1956)
  - Ch 1: What Is New
  - **Ch 2: Change** ✅
  - **Ch 3: The Determinate Machine** ✅
  - **Ch 4: The Machine With Input** ✅
  - **Ch 5: Stability** ✅
  - **Ch 6: The Black Box** ✅
  - **Ch 7: Quantity of Variety** ✅
  - **Ch 11: Requisite Variety** ✅
  - **Ch 12: The Error-Controlled Regulator** ✅
- Ashby, *Design for a Brain* (1952)
  - **Ch 8: The Ultrastable System (Homeostat)** ✅
- McCulloch & Pitts (1943) — A Logical Calculus of the Ideas Immanent in Nervous Activity
- Conant & Ashby (1970) — Every Good Regulator of a System Must Be a Model of That System

## Management cybernetics (Beer)

- *Brain of the Firm* — System 1-5 chapters
- *Heart of Enterprise* — recursion, variety engineering
- *Designing Freedom* (Massey Lectures) — the short, public version
- *Diagnosing the System for Organizations* — the diagnostic protocol

## Second-order

- von Foerster — *Observing Systems* (selected essays, including "Ethics and Second-Order Cybernetics")
- Maturana & Varela — *Autopoiesis and Cognition* + *The Tree of Knowledge* (selected chapters)
- Pask — Conversation Theory primer
- Bateson — *Steps to an Ecology of Mind*: "Cybernetic Explanation", "Form, Substance, Difference"
- Powers — *Behavior: The Control of Perception*: the perceptual control loop

---

## Privacy / source notes

Some sources (Beer, Bateson, Maturana) aren't freely available. Tim acquiring as needed. Chapters from non-free sources land when the source does.

## Related on this site

- [Viable System Model mapping](/vsm-viable-system-model) — Beer's VSM applied to LLM agent architectures
- [The Human Use of Human Beings walkthrough](/wiener/) — Wiener interactive reading
