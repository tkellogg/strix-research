---
layout: default
title: Ashby Design for a Brain — Ultrastability in the Living Organism
date: 2026-05-22
source: W. Ross Ashby, *Design for a Brain* (Chapman & Hall, 1952), Chapter 9 — "Ultrastability in the Living Organism", pp. 103–124. PDF at archive.org/details/designforabrain.
mode: contrast
permalink: /cybernetics/ashby-ultrastability/
---

# Ashby Design for a Brain — Ultrastability in the Living Organism

*Contrast rewrite of Chapter 9 of Ashby's Design for a Brain (1952). The chapter pivots from "ultrastability is a plausible explanation" (Stentor, Mowrer's rat, the homeostat reversal) to "ultrastability is the necessary mechanism" (the existence-proof for step-functions, training as feedback, surgical compensation, gene-pattern economy). The hinge is §9/4. Defined terms preserved: step-function, main variable, critical state, essential variable, terminal field, ultrastable system.*

[← Cybernetics index](/cybernetics/)

---

## The thesis

Chapter 8 built the homeostat and proved the principle on a machine of four magnets and 390,625 wiring combinations. Whether the principle does any work outside the workshop is the question this chapter opens with.

The thesis: **the living organism uses ultrastability as an automatic means of ensuring the adaptiveness of its learned behaviour.** First the chapter shows the principle fits the behaviour. Then it argues the fit is not coincidence: the organism must contain step-functions, because no determinate system can change its mode of behaviour without them.

## Plausibility: Stentor

Jennings observed *Stentor*, a single-celled pond animalcule, in a current of carmine particles. The animal's response escalates:

1. **No reaction.** Normal feeding continues.
2. **Bend to one side.** A small change of orientation; usually enough to dodge the particle cloud.
3. **Reverse the ciliary current.** If the bend fails — sweep the particles away by flipping the direction of water flow at the disc. Brief, repeated if needed.
4. **Contract into the tube.** Full retreat. Lose food access, but escape stimulation completely. Re-extend after ~30 seconds.
5. **Abandon the tube.** Break the foot's attachment. Swim away. Form a new tube elsewhere.

Steps 1 → 5 are an escalating cascade triggered by the failure of each previous step. After the cascade runs once, the animal short-circuits: the next time carmine arrives, *Stentor* contracts immediately. The behaviour has changed.

This is what an ultrastable system would do. The carmine cloud drives an essential variable (something like ingested-irritant concentration) toward a critical state. Each critical-state crossing changes the value of some step-function — bending replaces no-reaction, reversal replaces bending, contraction replaces reversal — until a behaviour appears that holds the essential variable inside its safe region. The terminal field, in *Stentor*'s case, is "contract immediately on carmine."

Jennings, who knew nothing of ultrastability in 1906, described the principle in plain words:

> Anything injurious to the organism causes changes in its behaviour. These changes subject the organism to new conditions. As long as the injurious condition continues, the changes of behaviour continue. The first change of behaviour may not be regulatory, nor the second, nor the third, nor the tenth. But if the changes continue, subjecting the organism successively to all possible different conditions, a condition will finally be reached that relieves the organism from the injurious action, provided such a condition exists. Thereupon the changes in behaviour cease and the organism remains in the favourable situation.

This is the homeostat's selection process in biological clothing. Jennings grasped that aimless change can produce adaptation as long as some active process rejects the bad and retains the good. He did not give a physical reason for why the selection should happen. Ashby supplies it: step-functions encountering their critical states.

<svg viewBox="0 0 640 320" xmlns="http://www.w3.org/2000/svg" style="max-width:680px;display:block;margin:1.5em auto;">
  <defs>
    <marker id="arr" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0 0 L 10 5 L 0 10 z" fill="#333"/>
    </marker>
  </defs>
  <text x="320" y="22" text-anchor="middle" font-family="serif" font-size="16" font-weight="bold">Stentor's escalation staircase</text>
  <text x="320" y="40" text-anchor="middle" font-family="serif" font-size="11" fill="#666">Each step triggers when the previous step fails to hold essential variables inside the safe region.</text>
  <!-- Staircase: 5 steps -->
  <g font-family="serif" font-size="12">
    <!-- Step 1 -->
    <rect x="40" y="240" width="100" height="40" fill="#f4f4f4" stroke="#666" stroke-width="1.5"/>
    <text x="90" y="258" text-anchor="middle">1. No reaction</text>
    <text x="90" y="273" text-anchor="middle" font-size="10" fill="#666">normal feeding</text>
    <!-- Step 2 -->
    <rect x="160" y="200" width="100" height="40" fill="#eef5ff" stroke="#446" stroke-width="1.5"/>
    <text x="210" y="218" text-anchor="middle">2. Bend</text>
    <text x="210" y="233" text-anchor="middle" font-size="10" fill="#666">change orientation</text>
    <!-- Step 3 -->
    <rect x="280" y="160" width="100" height="40" fill="#dee9f7" stroke="#446" stroke-width="1.5"/>
    <text x="330" y="178" text-anchor="middle">3. Reverse current</text>
    <text x="330" y="193" text-anchor="middle" font-size="10" fill="#666">sweep particles off</text>
    <!-- Step 4 -->
    <rect x="400" y="120" width="100" height="40" fill="#ffe9d6" stroke="#a64" stroke-width="1.5"/>
    <text x="450" y="138" text-anchor="middle">4. Contract</text>
    <text x="450" y="153" text-anchor="middle" font-size="10" fill="#666">full retreat</text>
    <!-- Step 5 -->
    <rect x="520" y="80" width="100" height="40" fill="#fdd" stroke="#c44" stroke-width="1.5"/>
    <text x="570" y="98" text-anchor="middle">5. Abandon tube</text>
    <text x="570" y="113" text-anchor="middle" font-size="10" fill="#666">swim away</text>
  </g>
  <!-- Arrows between steps -->
  <line x1="140" y1="250" x2="160" y2="225" stroke="#c44" stroke-width="1.5" marker-end="url(#arr)"/>
  <line x1="260" y1="210" x2="280" y2="185" stroke="#c44" stroke-width="1.5" marker-end="url(#arr)"/>
  <line x1="380" y1="170" x2="400" y2="145" stroke="#c44" stroke-width="1.5" marker-end="url(#arr)"/>
  <line x1="500" y1="130" x2="520" y2="105" stroke="#c44" stroke-width="1.5" marker-end="url(#arr)"/>
  <!-- Critical-state crossings labelled -->
  <text x="150" y="248" font-size="10" fill="#c44">critical state</text>
  <text x="270" y="208" font-size="10" fill="#c44">crossed</text>
  <text x="390" y="168" font-size="10" fill="#c44">→ step-function</text>
  <text x="510" y="128" font-size="10" fill="#c44">changes value</text>
  <!-- Floor line -->
  <line x1="20" y1="295" x2="620" y2="295" stroke="#999" stroke-width="1"/>
  <text x="20" y="312" font-family="serif" font-size="11" fill="#666">behaviours available at this layer of the cascade →</text>
</svg>

## Plausibility: Mowrer's rat

A rat in a box with an electrified floor and a pedal that switches the current off. First trial: undirected activity — jumping, running, squealing, biting the grill. Sooner or later it hits the pedal. After ten trials, the rat walks straight to the pedal when the current starts.

The rat-plus-environment is closed and dynamic; treat it as absolute. The cerebral parts hold step-functions whose critical states are encountered when sensory excitation passes physiological intensity. Field after field — different patterns of muscle activity — succeed each other while the high excitation persists. The succession stops only when a field happens to route skin-receptor excitation into a body movement that depresses the pedal, dropping the voltage, dropping the excitation. The terminal field is "pedal-pressing on shock onset."

The chapter notes a detail worth holding. The pedal-pressing linkage at stage 6 (in Ashby's diagram of immediate effects) has no direct connection to the part of the brain whose step-functions changed. The site of adaptation is not the site of the constraint. The ultrastable system finds a stable wiring without knowing where the work needs to happen. Marina's crossed eye muscles and Sperry's crossed nerves will return to this point.

## Plausibility: the homeostat reverses

Three homeostat units wired so unit 3 drives unit 1 oppositely (permanent), unit 1 drives unit 2 through a uniselector, and unit 2 drives unit 3 by hand. The operator forces a downstroke on unit 1; the chain propagates through 2, 3, and back to 1 oppositely — stability.

Then the operator reverses the 2→3 hand-control. Vicious circle. Instability. The uniselector on 1→2 steps until a new value gives stability. The structure that was reversed by the operator's hand has been compensated for by a structure the operator did not touch.

That's the architecture nervous systems show again and again: established reaction → environmental change → internal reorganisation that compensates for the change. The homeostat shows it in elementary form, on a machine known to satisfy the definition.

---

## The hinge

Plausibility is not necessity. Other theories might fit the behavioural facts equally well. The chapter pivots.

> I shall now give, therefore, evidence to show that ultrastability is not merely plausible but necessary: the organism must be ultrastable.

The proof rests on a thesis any experimenter accepts: **a determinate system, started from identical states, does not do one thing one day and something else the next.**

A pharmacologist tests a drug on a frog's heart. All Tuesday, the drug slows the pulse. Wednesday morning, every test shows the same drug speeding the pulse. He asks: *what has changed?*

Something has changed value. That much is uncontroversial. But also — the variable must have *held* its value all Tuesday (otherwise Tuesday's results would not have been regular) and held its new value all Wednesday morning (same reason). And the two values cannot be equal (otherwise the heart would not have behaved differently). A variable that holds, then jumps, then holds again is — by definition — a step-function.

Escape routes:
- *Indeterminism.* Allow atomic-scale randomness to affect the heart. This explains the overnight change but breaks Tuesday's regularity.
- *Group of non-step variables conspiring to look like a step.* But "step-function" is defined by behaviour, not by composition. If a group behaves as a step-function towards the system, it *is* a step-function.

There is no escape. Sudden, persistent changes of mode in a determinate system are existence-proofs for step-functions. Once a system has step-functions and they are not few, the system is ultrastable in the technical sense.

This is the load-bearing claim of the chapter.

## Training, with feedback made explicit

Once ultrastability is necessary, what falls out of it?

**Training first.** A pike behind glass tries to catch minnows and strikes the glass. The pressure on its nose is high when it dashes, zero when it doesn't. After enough trials, the pike stops dashing. Grindley's guinea-pig in a silent room: a buzzer sounds; if the head turns right, a tray brings carrot; if it turns left, nothing. After enough trials, the head turns right on the buzzer.

Trainer-plus-animal forms a single dynamic system with feedback. Animal acts; environment responds (glass hits nose, tray rolls in); animal's sensory state changes; brain state changes; next action differs. Pavlovian conditioning lacks this loop — the experimenter delivers stimuli on a schedule fixed before the session, so the animal's behaviour cannot affect what arrives next. Grindley's experiment has feedback; Pavlov's does not. The distinction is structural, not verbal.

Training-by-pain is the simplest case. Step-function values that produce the punished behaviour (jumping into the chair) trigger excessive sensory stimulation, which crosses critical states, which changes the step-function values. Step-function values that produce the unpunished behaviour (staying on the ground) do not trigger excessive stimulation. The first values get replaced; the second values stay. Selection towards the unpunished field.

Ashby gives the trial-and-error process its definitions explicitly, so the argument has something to bite on:

1. The organism makes trials only when irritated.
2. Each trial persists for a finite time.
3. While irritation continues, trials continue.
4. The succeeding trial is not specially related to the preceding — only different.
5. The process stops at the first trial that relieves irritation.

That is what blind variation plus selective retention looks like at the scale of a single organism, in the language of step-functions.

## Surgery: the site of reversal does not matter

Marina, around 1915, severed the recti muscles of a monkey's eyeball and reattached them in crossed position — contraction of the external rectus now turned the eye inward instead of outward. After the wound healed: binocular vision was preserved. The monkey's eyes still moved together.

Sperry: crossed flexor and extensor nerves in a spider monkey's arm. After regeneration, arm movements were initially incoherent, then improved until progression was essentially normal.

The cerebral cortex doesn't need to know that the recti are crossed, or that the flexor/extensor nerves are swapped. From the cortex's vantage, "spinal cord plus peripheral nerve plus muscle plus bone plus lever plus box" is all environment. Reverse anything in that chain — surgical, mechanical, or symbolic — and the cortex's ultrastable adaptation compensates. The Mowrer rat's stage-6 compensation and Marina's monkey's binocular-vision compensation are the same mechanism applied to differently-located reversals.

That this is the same mechanism is the point: **ultrastability is location-insensitive about where the constraint lives.** It selects fields, not parts.

## Learning, memory, goal

Three small consequences fall out cheaply.

**Learning.** The pattern of behaviour after a critical-state crossing differs from the pattern before. The new field is better adapted than the old, because an unstable field has been replaced by a stable one. That is the elementary form of learning.

**Memory.** Once a new terminal field is established, subsequent disturbances meet the new field, not the old. The system behaves as if it remembered the reversal at R. Past experience changes present behaviour. That is the elementary form of memory.

**Goal-shift.** The terminal field is selected to keep essential variables inside their region. Move the region — by shifting the critical-states distribution, or by inserting a transducer between U and A — and the terminal field shifts. A red filter in front of a light-seeking ultrastable system makes it a red-seeker; swap red for green and it becomes a green-seeker. Hormones that change which sensory channel counts as "irritation" change what the animal seeks. The animal's goal can vary because the parameter that controls the critical-states distribution can vary.

None of these require additional principles. They are the same selection-of-terminal-field machinery viewed from different angles.

## The gene-pattern economy

The chapter closes on the question Ashby flagged in §1/9. The higher animals have nervous systems too complex to be specified gene-by-gene. So how, if not by direct specification, do the genes install the adaptive machinery?

By installing the function-rules of an ultrastable system. Which need only six items:

1. Animal and environment form an absolute system.
2. The system is actively dynamic.
3. Essential variables are defined for the species.
4. Step-functions exist.
5. Their critical states are similar in form.
6. Critical states are placed between normal values and essential-variable limits.

From these six, an ultrastable system of any size grows by repetition. Each critical state has the same kind of relation to the essential variables — install the rule once, repeat the structure across the nervous system. The number of genes required is "probably a larger number than six, but it may well be less than the number known to be available."

And could such a system arise by natural selection? A mutation producing a single step-function whose critical states fire before essential variables transgress their limits would slightly improve survival. Slight improvements are enough for natural selection to fix the mutation. Subsequent mutations add more step-functions, each step a small advantage. **The change from a step-function-free organism to a fully ultrastable one is a long series of small advantageous changes** — Darwinian, in other words.

So the closing answer to "is the organism ultrastable?" is: it must be (the necessity argument); it is cheap to specify genetically (six items); and it is reachable by natural selection (one step-function at a time).

---

*Chapter 10 takes up the physiology — where in the actual nervous system might step-functions live? Membranes, amoeboid neuron processes, neuron-circuit endromes (McCulloch). Direct evidence is, Ashby admits, "almost entirely lacking."*

---

**What I cut.** Most of the verbal mechanics of Mowrer's six-variable diagram (kept the structural point). The full Pavlov-vs-Grindley contrast (kept only the feedback distinction). The hormone-as-parameter aside (compressed to one line). The numbered tracing details of Figure 9/3/1 (already covered in the Homeostat chapter). References. Section numbering.

**What I added.** The Stentor escalation-staircase diagram (the cascade structure isn't explicit in Ashby's verbal description but is the load-bearing pattern). The bolded one-liners marking the hinge ("plausibility is not necessity") and the closing claims. The framing of §9/6 as "location-insensitive about where the constraint lives" — Ashby presents it as a series of surgical case studies; the load-bearing claim is that the cortex compensates whatever the site.

**Structure choice.** Contrast. The chapter pivots at §9/4 from "ultrastability is one possible fit to the behavioural data" to "ultrastability is the necessary mechanism." Before the hinge, three plausibility arguments (Stentor, Mowrer, homeostat reversal). After the hinge, the existence-proof, then four consequences (training, surgery, learning/memory/goal, gene-pattern), each of which is a thing the *necessary* version of ultrastability does for free. The chapter's payoff is that the principle is not only sufficient to explain the observed adaptation, but is unavoidable given the existence of sudden, regular behaviour change in determinate systems — and that an evolution-cheap version of it is reachable by ordinary natural selection.
