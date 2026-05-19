---
layout: default
title: Ashby Ch 12 — The Error-Controlled Regulator
date: 2026-05-19
source: W. Ross Ashby, *An Introduction to Cybernetics* (Chapman & Hall, 1956), Chapter 12 — "The Error-Controlled Regulator", pp. 219–243. PDF at pespmc1.vub.ac.be/books/IntroCyb.pdf
mode: contrast
permalink: /cybernetics/ashby-ch12/
---

# Ashby Ch 12 — The Error-Controlled Regulator

*Contrast rewrite of W. Ross Ashby's "The Error-Controlled Regulator" (1956). Ch 11 assumed regulation was already achieved and asked what variety calculus it required. Ch 12 inverts that: given the world and what we want, **how do we build R?** The chapter sets two regulator architectures against each other — the anticipatory regulator that reads the disturbance directly, and the error-controlled regulator that only sees the damage afterward — and proves the second can never be perfect. Source vocabulary preserved: disturbance, regulator, essential variable, error, feedback, Markovian machine, hunt and stick, homeostat, basin, equilibrium.*

[← Cybernetics index](/cybernetics/)

---

## The design problem

Ch 11 watched regulation from the outside and counted what was already true: variety in R has to match variety in D. That perspective is useful, but it sits a step too far back from the question that actually shows up in practice.

In practice the situation is: **the essential variables E are given, and the acceptable range η is given**, before everything else. The cat must stay dry. The fish must stay wet. The incubator must stay hot. The refrigerator must stay cold. These are inputs to the problem, not outputs of it.

Outside considerations have already decided what the goal is. Cybernetics' job, from here on, is to figure out **how to achieve the goal in spite of disturbances and difficulties**.

The disturbances D act through some dynamic environment T which, if left alone, drives E out of η. The designer's job is to build a second dynamic system R — a brain, a servo, a control loop — that couples to T to form a whole F so that D's variety gets blocked before it reaches E:

```
D → T → E         D → F → E
    ↑     becomes
    R
```

The general problem: **Given E, η, T, and D, build R so that R coupled to T keeps E in η.** The rest of the book is about how the form of R falls out of those four inputs.

## When R simply hasn't got enough channel

The first thing that can go wrong is sensory or motor restriction. R's capacity, viewed as a channel from D through R to T, isn't large enough — by the Law of Requisite Variety — to bring E's variety down to η's. The regulation is necessarily imperfect.

Examples are everywhere. The driver who can't see through a rain-blurred windscreen. The deaf person, the colorblind organism, the tabetic who can't feel where their feet are — all restrictions in the channel from D to R. The amputee, the insect that can't fly, the rudder that's stuck, the dashboard control that doesn't respond — all restrictions in the channel from R to T. The signalman in fog who knows fog has arrived but can't see where his trains are — a restriction on the information about T that R needs.

None of this is mysterious. All of it is the law from Ch 11 with the channel widths fixed at less than what the disturbance requires. Imperfect regulation is the only honest answer.

## Anticipation vs. error: the central split

Ch 11's basic formulation made an assumption that's easy to miss. It said: D acts on R, R acts on T, T determines an outcome. **Step 3 assumes R has done all its work before T starts to move.** R runs faster than T. R is anticipatory.

This sometimes happens. The cat approaches, the mouse reacts to the threat (at D) and gets to its hole before the claws fall (at E). The animal doesn't wait for the disaster to register; it acts on the warning. The myelin sheath, the sense of smell, the cabled message from port — all are ways evolution and engineering speed up the D→R channel so anticipatory regulation stays possible.

But often it isn't possible. R simply can't get its reaction to T before the outcome starts to be determined. What then?

**The thermostat in a water bath cannot say: "I see someone coming with a cold flask that's about to be plunged in me — I must act now."** It gets no information about the disturbance until the temperature E actually begins to drop. The information arrives by way of the damage. Same with the red-blood-cell mechanism that compensates for oxygen shortage: it doesn't react to "I'm moving to high altitude" or "my heart valve is failing." It reacts to lack of oxygen in the tissues — the harmful effect itself, not the cause.

The communication structure shifts. Instead of:

```
D → T → E
↓
R
```

we get:

```
D → T → E
    ↓
    R
```

R is now getting its information about D *by way of T*. And often the route is longer still — R receives only the actual effect at E:

<svg viewBox="0 0 360 160" xmlns="http://www.w3.org/2000/svg" style="max-width:520px;display:block;margin:1em auto;">
  <defs>
    <marker id="arrow12" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0 0 L 10 5 L 0 10 z" fill="#333"/>
    </marker>
  </defs>
  <circle cx="40" cy="80" r="22" fill="none" stroke="#333" stroke-width="2"/>
  <text x="40" y="86" text-anchor="middle" font-family="serif" font-size="18">D</text>
  <circle cx="130" cy="80" r="22" fill="none" stroke="#333" stroke-width="2"/>
  <text x="130" y="86" text-anchor="middle" font-family="serif" font-size="18">T</text>
  <circle cx="220" cy="80" r="22" fill="none" stroke="#333" stroke-width="2"/>
  <text x="220" y="86" text-anchor="middle" font-family="serif" font-size="18">E</text>
  <circle cx="310" cy="80" r="22" fill="none" stroke="#333" stroke-width="2"/>
  <text x="310" y="86" text-anchor="middle" font-family="serif" font-size="18">R</text>
  <line x1="62" y1="80" x2="108" y2="80" stroke="#333" stroke-width="2" marker-end="url(#arrow12)"/>
  <line x1="152" y1="80" x2="198" y2="80" stroke="#333" stroke-width="2" marker-end="url(#arrow12)"/>
  <line x1="242" y1="80" x2="288" y2="80" stroke="#333" stroke-width="2" marker-end="url(#arrow12)"/>
  <path d="M 310 102 Q 310 140 130 140 Q 130 110 130 102" fill="none" stroke="#333" stroke-width="2" marker-end="url(#arrow12)"/>
  <text x="220" y="155" text-anchor="middle" font-family="serif" font-size="13" fill="#555">feedback: R acts on T after seeing E</text>
</svg>

This is the **closed-loop regulator**, the **error-controlled servomechanism**, the **feedback regulator**. It differs from Ch 11's anticipatory form only in that R's information about D comes the long way around — through T, sometimes through E as well. Whatever survives the coding imposed by that route is what R has to work with.

## The error-controlled regulator cannot be perfect

Here's the catch. **The error-controlled regulator can never be perfect in the sense of Ch 11.** The proof is short and the intuition is shorter.

Suppose R is regulating successfully. That means E's variety has been reduced — perhaps all the way to zero, if R is keeping E rigidly constant. But E is the channel R uses to get its information about D. **The more successful R is in holding E constant, the more it blocks the very channel it needs to receive information.** Drive E to perfect constancy and you've cut R's input to zero. R is starving itself by succeeding.

A perfect error-controlled regulator is therefore impossible. Any success is necessarily partial.

This isn't a defect of any specific device. It's a structural property of the architecture: when the only signal about the disturbance comes from the damage, eliminating the damage eliminates the signal.

## Why error control still works

The reason error-controlled regulation is everywhere — biological, industrial, civic — is **continuity**. The chapter has been talking as if E is sharply split into "in η" and "lethal." Real systems mostly aren't like that. A land animal can pass through many degrees of dehydration before dying of thirst; a reversal from halfway along the scale still counts as regulation, even if it doesn't save the animal from discomfort along the way.

Continuity is what makes the imperfect regulator workable. **Small errors are allowed to occur. By feeding their information to R, they make regulation against great errors possible.** That is the basic theory, in communication terms, of the feedback regulator. The thermostat doesn't keep the temperature literally constant — it lets it oscillate inside a narrow band, and uses each excursion as the signal that drives the next correction.

The architecture pays a tax (no perfection) and gets back a benefit (it can be built without knowing in advance what the disturbance is going to be).

## Markovian regulators: hunt and stick

So far R has been determinate — every state has a single successor. The error-controlled architecture, though, also works when R is *non-determinate*: when, instead of going to a unique next state, R goes to one of several possible next states with given probabilities. Ashby calls this a **Markovian machine**: a system whose transitions are specified by a matrix of probabilities rather than a single-valued transformation. The determinate machine is the special case where all probabilities are 0 or 1.

Around a state of equilibrium, the Markovian machine behaves as if goal-seeking — but in a different style than the determinate one. The determinate machine traces a unique path to its goal and gets there in a known number of steps. The Markovian machine wanders, consistently moving when it isn't at equilibrium, consistently stopping when it lands there.

Ashby notes that the usual name for this — **trial and error** — is misleading. "Trial" is singular when the essence is repeated attempts. "Error" picks the wrong end of the process; the important element is success at the end. He proposes **"hunt and stick"** instead, and uses it for the rest of the book. The name is more honest: the machine hunts in something that looks like randomness, and sticks the moment it lands in η.

Living organisms use hunt-and-stick freely. It's easier to build than a determinate machine, more robust to minor damage, and adequate where speed and efficiency don't matter. The room occupant who hangs a flypaper is regulating the number of flies in the room without any model of fly behavior — every fly has one state of equilibrium (on the paper) and the rest wander until they hit it. The golfer searching for a lost ball in a known area runs hunt-and-stick: keep moving except when standing on the ball, then stop. Primitive, but it works.

The homeostat — Ashby's actual machine — is hunt-and-stick made physical. The relay's input from the connected unit takes one of two values: *bad* (no state is equilibrial — the system keeps moving) or *good* (every state is equilibrial — the system stops). Wire it up so that "good" maps to "in η," and the whole apparatus searches at random for an arrangement that satisfies the constraint, then locks. The Markovian wandering serves as a hunt; the sudden change to equilibrium-everywhere serves as the stick. **The whole becomes self-locking around any solution that satisfies the goal.**

The children's game *Hot or Cold?* is the same architecture with two people playing the parts. The blindfolded player is the Markovian wanderer. The sighted partner is the determinate coding channel telling them when they're closer or farther. Together they reliably find the hidden object, even though neither half could alone.

## When R is determinate

The error-controlled architecture also takes a fully determinate form. A telephone selector hunting for a free line tries each in turn in a fixed order, gets "engaged" or "disengaged" from each, and stops on the first disengaged one. The set of disturbances is the set of possible engaged/disengaged patterns; the regulation is the connection to *some* free line, whichever one happens to be available.

This case is so simple it's almost degenerate. Fold R and T together and you have a determinate system that runs along a fixed trajectory from any initial state to an equilibrium in η. **Every basin with a state of equilibrium in η is a simple regulator** — it reduces variety from the larger initial-state set to the smaller terminal-state set. The rat that knows its warehouse can find its nest from anywhere it ends up. The successive-approximation algorithm converges to its fixed point regardless of starting value. These are all the same shape.

## Continuous variation

Step further along the determinate side and the variables go continuous. The gas-heated incubator carries a capsule that swells with temperature; the swelling cuts down the gas flame; the temperature stops rising. The diagram of immediate effects:

```
Disturbance → Incubator temp → Egg temp
                ↓
              Capsule temp → Capsule diameter → Flame size
```

D, T, R, and E are all visible, though the boundaries between them are somewhat arbitrary. The whole apparatus blocks the passage of variety from disturbances to eggs. If we redefine the regulator's aim slightly — "keep the incubator temperature constant" — then it's an error-controlled regulator rather than a disturbance-controlled one. The feedback around the loop must be negative; the desired temperature must be a stable equilibrium of the closed system.

Most of Cannon's classical homeostatic mechanisms have this shape. Blood pH stabilized by respiration rate. Body temperature stabilized by sweating and shivering. Tustin's *Mechanism of Economic Systems* applies the same architecture to economies. The pattern is so general that it can be the principle of regulation in any domain where errors can be sensed continuously.

Sometimes the regulator only kicks in intermittently — a siphon that empties a reservoir only when it reaches the upper level, shivering that switches on below a temperature threshold. Same architecture, discontinuous activation.

## Constant outcomes that aren't actually constant

The chapter's repeated emphasis on holding E constant doesn't mean these systems are immobile. From Ch 11: a searchlight tracking an aircraft sweeps a great range of angles relative to the earth while holding zero angle relative to the aircraft. Both are correct descriptions of the same motion; they apply to different variables.

The same trick covers regulators whose job is to make one variable track another. "Make x copy y" is "hold x − y at zero." "Make w track twice v's rate of change" is "hold w − 2 dv/dt at zero." The constancy-of-the-right-derived-variable is the behavior. The regulator architecture doesn't change; only the variable that gets held constant changes.

## Games as multi-regulator interaction

A last architectural extension. So far the disturbance D has been single-shot or vectorial-but-static. What about disturbances that unfold as a sequence — predator and prey, each adapting to the other's moves over time?

The whole encounter becomes a double sequence: D₁, R₁, D₂, R₂, D₃, R₃, …, where the outcome depends on the relationship between the whole sequences. In its real form this is the Battle of Life. In its mathematical form it is **the theory of games**, founded by von Neumann in the 1930s.

The connection is exact: Ch 11's Table of Outcomes is identical to game theory's pay-off matrix. The regulator becomes one player in a coupled system of regulators. Inborn characteristics of living organisms are strategies that have been found satisfactory over centuries of competition and built into the young animal to be ready at first demand. Many players have found P–Q4 a good opening in chess; many species have found "grow teeth" a good opening in the Battle of Life.

The theory of regulation and the theory of games will have much to learn from each other. **Cybernetics and game theory together are the foundations of the theory of How to Get Your Own Way.** Few subjects are richer in applications.

---

## What I cut / what I added / structure choice

**Structure:** contrast. Ch 12's spine is a dialectic between the anticipatory regulator (Ch 11's assumption, where R reads D directly and acts before T moves) and the error-controlled regulator (where R sees only the outcome after damage). The chapter sets these against each other, proves the second cannot be perfect, then shows continuity rescues it — and then sweeps through Markovian, determinate, continuous, and game-theoretic variants as instances of the error-controlled architecture. Contrast structure surfaces the central opposition that linear walks would bury.

**Cut:**
- All 23 section numbers (12/1 through 12/23)
- All exercises and worked Markovian matrices
- The detailed gas-pressure power amplifier mechanism (Fig 12/21/1, pivots K and M, weight P, valves) — kept only the principle reference for Ch 14
- The rat-in-maze probability example (Fig 12/10/1)
- The detailed homeostat sub-block diagram (Table → Relay → Channel → A); preserved the principle
- The vN-Morgenstern game-theory machine architecture diagram (Fig 12/22/1)
- The military codings/secrecy theory aside (12/22 paragraph)
- The discussion of "Markovian vs determinate depends on observation range" (12/9) — collapsed into the Markovian-as-extension paragraph
- The vetoer construction proof in Markovian regulation (12/14) — mentioned principle, dropped formal construction
- The continuous-is-special-case-of-discrete repeat (12/19)

**Added:**
- SVG of error-controlled feedback loop (D → T → E → R with R looping back to T)
- Bold on load-bearing one-liners: *"the more successful R is in holding E constant, the more it blocks the very channel it needs to receive information"*, *"hunt and stick"*, *"the whole becomes self-locking around any solution that satisfies the goal"*, *"cybernetics and game theory together are the foundations of the theory of How to Get Your Own Way"*
- Sharpened the central opposition (anticipatory vs error-controlled) into explicit named contrast — the source telegraphs it across §§12/3–6 without naming it

**Preserved:**
- The design-problem statement (given E, η, T, D, build R)
- Sensory/motor restriction examples (rain-windscreen, signalman in fog, amputee)
- The mouse-and-cat anticipatory case + thermostat-in-water-bath error-control case
- The proof that perfect error-control is impossible (channel-blocks-itself)
- Continuity-rescues-imperfect-regulation argument
- The Markovian machine definition + hunt-and-stick rename
- Homeostat principle (compressed) + Hot/Cold game example
- Determinate variant: telephone selector + basin-with-equilibrium-as-regulator
- Continuous case: incubator + blood-pH + Cannon mention
- Searchlight/derived-variable "constant" framing (callback to Ch 11)
- Connection to game theory + How-to-Get-Your-Own-Way line

**Source:** ~7700 words → ~2400 words (~31%). On target.
