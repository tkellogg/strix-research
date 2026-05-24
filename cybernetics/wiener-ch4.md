---
layout: default
title: Wiener Cybernetics Ch 4 — Feedback and Oscillation
date: 2026-05-24
source: Norbert Wiener, *Cybernetics; or, Control and Communication in the Animal and the Machine* (MIT Press, 1948), Chapter IV, "Feed-back and Oscillation," pp. 113–136.
mode: chiasm
permalink: /cybernetics/wiener-ch4/
---

# Wiener Ch 4 — Feedback and Oscillation

[← Cybernetics index](/cybernetics/)

## Two patients

A man walks into a neurological clinic. He isn't paralyzed; ask him to move his legs and he can. But his gait is wrong — he watches the ground, throws each leg in front of him with a kick, and if you blindfold him he falls over.

A second man sits quietly. Nothing visibly wrong. Offer him a cigarette and his hand sweeps past it; the correcting swing overshoots; the next swing overshoots again; he ends up oscillating violently in the air with no cigarette in hand. Hand him a glass of water and it'll be empty before it reaches his mouth.

Both are *ataxic*. Their muscles are fine. They can't organize their actions.

The first has **tabes dorsalis** — syphilis has eaten the part of his spinal cord that carries sensation back from joints, tendons, muscles, soles. The receptors still work but the messages don't get through. He's lost his *proprioceptive sense* — the body's reading of where its parts are. So he steers by vision and the inner ear, badly.

The second has a cerebellar lesion. His proprioception is fine; the part that proportions muscular response *to* that proprioception is broken. He gets the data, can't tune the gain.

**Both diseases are failures of feedback.** Effective action on the world isn't just about having effectors; the effectors must be *monitored back* to the central control, and their readings combined with the input to produce a properly proportioned output. Cut the proprioceptive line, and the loop is open. Damage the proportioning, and the loop is unstable.

## Feedback in the machine

The same problem shows up in mechanical systems. A signalman on a railroad pulls levers that throw switches and turn semaphores. He cannot assume the orders were obeyed — switches freeze, signal arms bend under snow. So every effector is wired to report its actual state back, like the Navy practice of repeating an order back to the officer who gave it. The signalman acts on the *repeated* order, not the one he sent. **This loop — order out, state back — is feedback.**

Sometimes the loop has no human in it. A thermostat: you set the desired room temperature; if the room is colder, the damper opens or the fuel-oil flow increases; if it's warmer, they cut back. A badly designed thermostat sends the room into temperature oscillations not unlike the cerebellar tremor — same mechanism, different substrate.

Watt's steam-engine governor is older. Two balls swing out on pendulum rods as the shaft spins faster; centrifugal action raises them; the linkage closes the intake valves; the engine slows; the balls fall; the valves reopen.

**The feedback opposes what the system is already doing. That makes it negative.**

Position can be stabilized the same way — the steering engine of a ship is driven by the angular difference between the wheel and the rudder, always acting to bring them into agreement. So is voluntary movement. We don't will individual muscles, and we mostly don't even know which ones we're using. We will a goal — *pick up the cigarette* — and the motion is regulated by some measure of how far short of the goal we still are.

## Stability lives in the complex plane

Wiener now wants a precise theory of when a feedback works and when it breaks into oscillation. The simplest case is linear: the effector's output is a linear function of its input, the reading is read linearly, and the reading is subtracted from the input. He's going to use frequency-domain calculus, with verbal commentary.

Take a quantity \\(f(t)\\) that runs from \\(-\infty\\) to \\(\infty\\). A *delay operator* turns \\(f(t)\\) into \\(f(t-\tau)\\). Combine several delays with weights and you get an output of the form

$$\sum_n a_n f(t-\tau_n),$$

and in the limit, a linear time-invariant operator on the past of \\(f(t)\\) is essentially

$$\int_0^{\infty} a(\tau)\,f(t-\tau)\,d\tau.$$

The integral runs from \\(0\\) to \\(\infty\\), not from \\(-\infty\\) to \\(\infty\\). That asymmetry is essential — we don't get to read the future. **Any operator that doesn't respect the past-future arrow isn't a real physical operator on a signal.**

Sub in \\(f(t) = e^{zt}\\) and the operator becomes a multiplication: \\(A(z) = \int_0^{\infty} a(\tau)\,e^{-z\tau}\,d\tau\\). This is the *frequency-domain representation* of the operator. Set \\(u + iv = A(iy)\\) with \\(y\\) real, and let \\(y\\) run from \\(-\infty\\) to \\(\infty\\). You get a curve in the complex \\((u,v)\\)-plane.

That curve, in general, divides the plane into two regions — call them *interior* and *exterior*. The wiring diagram of a feedback system is:

```
input  ─→ (subtractor) ──→ [ motor, operator A ] ──→ output
              ↑                                     │
              └─────────── [ multiplier α ] ←───────┘
```

The motor's input \\(Y\\) is the original input \\(X\\) minus \\(\alpha\\) times the motor output. Work the algebra and the operator produced by the feedback loop is \\(A/(1+\alpha A)\\). It blows up exactly when \\(A = -1/\alpha\\) — when the loop equation has no finite solution.

So the loop is unstable when, and only when, **the point \\(-1/\alpha\\) lies inside the curve traced by \\(A(iy)\\).**

If \\(-1/\alpha\\) is *exterior*, the feedback is stable, any amplification is admissible, and the closed-loop system inherits \\(A\\)'s good properties without its quirks. If \\(-1/\alpha\\) is *interior*, the system goes into unrestrained oscillation that builds up to infinity. If it sits on the boundary, you get a borderline oscillation of fixed amplitude — discuss carefully.

**The whole stability question reduces to a geometry problem: where does a single point sit relative to a curve drawn by the open-loop transfer function?**

<svg viewBox="0 0 480 320" xmlns="http://www.w3.org/2000/svg" style="background:#fff; max-width:100%; height:auto;">
  <defs>
    <marker id="arr" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="6" markerHeight="6" orient="auto">
      <path d="M0,0 L10,5 L0,10 z" fill="#333"/>
    </marker>
  </defs>
  <line x1="40" y1="160" x2="460" y2="160" stroke="#888" stroke-width="1"/>
  <line x1="240" y1="20" x2="240" y2="300" stroke="#888" stroke-width="1"/>
  <text x="455" y="155" font-size="11" font-family="Georgia, serif" fill="#666">u</text>
  <text x="245" y="22" font-size="11" font-family="Georgia, serif" fill="#666">iv</text>
  <path d="M 240,160 C 280,90 360,90 380,160 C 360,230 280,230 240,160 Z" fill="#e6f0fa" stroke="#1a4d7a" stroke-width="2.5" marker-end="url(#arr)"/>
  <text x="385" y="155" font-size="12" font-family="Georgia, serif" fill="#1a4d7a">interior</text>
  <circle cx="160" cy="160" r="4" fill="#c0392b"/>
  <text x="100" y="148" font-size="13" font-family="Georgia, serif" fill="#c0392b">−1/α</text>
  <text x="120" y="180" font-size="11" font-family="Georgia, serif" fill="#666">(exterior: stable)</text>
  <circle cx="320" cy="160" r="4" fill="#c0392b"/>
  <text x="305" y="148" font-size="13" font-family="Georgia, serif" fill="#c0392b">−1/α</text>
  <text x="280" y="180" font-size="11" font-family="Georgia, serif" fill="#666">(interior: catastrophe)</text>
  <text x="240" y="290" font-size="11" font-family="Georgia, serif" fill="#333" text-anchor="middle">curve: u + iv = A(iy), y from −∞ to ∞</text>
</svg>

## What can and can't be stabilized

Wiener runs the test against a series of operators. Pure differentiation \\(A(z) = z\\) traces the imaginary axis, with interior the whole right half-plane — \\(-1/\alpha\\) is always exterior, any feedback works. The integrator \\(A(z) = 1/(1+kz)\\) traces a circle of radius \\(1/2\\) centered at \\((1/2, 0)\\), gone clockwise; \\(-1/\alpha\\) sits outside for any \\(\alpha\\); any feedback works. A double-pole \\(1/(1+kz)^2\\) traces a cardioid; any feedback works again. The triple-pole \\(1/(1+kz)^3\\) traces something that blocks feedback above \\(\alpha = 1/2\\). A pure delay \\(e^{-Tz}\\) traces the unit circle and the feedback is capped at \\(\alpha = 1\\).

The take-home: **three first-order lags in cascade can each be compensated individually, but the cascade as a whole cannot be stabilized by a single feedback.** Adding stages is not free.

The ship-steering case shows what to do about it. Quartermaster sets a course; the gyrocompass reads angular difference between the set course and the actual; the steering engine turns the rudder; rudder angle determines turning moment, which is the angular acceleration of the ship.

So the operation feedback has to stabilize is *kz³* — third derivative of the deviation. The Nyquist curve is the negative imaginary axis cubed, the interior is the entire left half-plane, **and no single feedback whatsoever will stabilize it.** Adding friction to the model doesn't save it.

The fix is to introduce a second feedback. Make the rudder angle (not its rate of change) proportional to the course error — so feed back the rudder angle against itself with high gain, opening the steering-engine valves wide. The outer loop now sees an effector whose rudder *position* tracks the course error, not its derivative. Now the operator to stabilize is \\(k_2 z^2 + k_1 z\\), which traces a curve whose interior is on the wrong side for catastrophe — unlimited feedback admissible. **This is the cascade feedback architecture used in actual gyrocompass autopilots.**

## Why limb motion needs postural feedback

Bring the math back to the patient. A finger moving through space is the additive vectorial output of many joints. A complex additive cascade cannot, in general, be stabilized by a single feedback — that's the lesson of the gyrocompass.

So the voluntary feedback (the one we use to direct motion against the goal) needs *another* feedback under it — the postural feedback that maintains baseline tone in the muscular system. The voluntary loop is what breaks when the cerebellum is damaged; the patient's tremor only appears when he tries to *do* something, because at rest the postural layer is doing the work and the voluntary layer isn't engaged.

This is structurally different from Parkinsonian tremor, which appears at rest and often quiets during a voluntary task. Parkinsonianism originates in the brainstem, not the cerebellum; it's a failure of a postural feedback, not a voluntary one. **One of the great tasks of physiological cybernetics is to disentangle which feedback breaks in which disease.**

## Linear oscillation isn't all there is

A linear oscillating system oscillates in the form \\(A \sin(\beta t + C)\,e^{\alpha t}\\). Its amplitude is undetermined; the system has no preferred energy level. Any non-sinusoidal periodic oscillation tells you the system isn't really linear.

The deeper difference: in a linear oscillator, amplitude is independent of frequency, and the system can in principle oscillate at any amplitude. In a non-linear oscillator, **there's typically one amplitude (or a discrete set) at which the system will oscillate at a given frequency.** Energy input and energy dissipation grow with amplitude on different curves; the steady state is the point where they cross. Amplitude is as determinate as frequency.

This is the *relaxation oscillation* — translation-invariant equations, periodic solution, determinate amplitude and frequency, undetermined phase. The organ pipe is one example: steady air flow across the lip is unstable; the slightest perturbation feeds into a mode of the pipe; the coupling between flow and oscillation grows; thermal dissipation grows differently; they meet at a fixed amplitude. Another example: gas leaking into a chamber with a pilot light. When the mixture hits explosive concentration, it ignites. The frequency depends on the gas flow rate and the seepage of air and combustion products, not on any natural frequency of any part of the system. **Relaxation oscillations don't need a near-linear part to oscillate near.**

For non-linear systems that differ only slightly from linear ones, and where the non-linear terms vary slowly compared to the oscillation period, you can treat the system as linear with slowly-varying parameters — *secularly perturbed*. This is the same trick used in gravitational astronomy. Some physiological tremors may yield to this treatment: an amplifier whose gain falls as the long-time-average of its input rises will hit a stable amplitude where gain compensates loss. The non-linear theory of integral-equation relaxation oscillations is still mostly unwritten (writing as of 1948).

## Compensation, anticipation, information

Feedback isn't the only way to clean up an effector. *Compensation* — putting an inverse operator in front of the effector to cancel its lag — does some of the same work. The two are competitors. The feedback's specific advantage is **robustness to changes in the effector's characteristic**: a heavy negative feedback drops the system's dependence on its motor's properties roughly by the loop gain. Compensation, lacking that loop, fails when the motor changes.

You can combine them. Put a compensator in front of a feedback loop and the compensator only has to handle the *average* characteristic — the feedback cleans up the rest. Put the compensator inside the loop and it shifts the level of admissible feedback while improving steady-state tracking.

A particularly interesting variant: **anticipatory feedback.** When you shoot a duck, you don't minimize the gap between gun and current duck position — you minimize the gap between gun and *predicted* duck position. The compensator is a predictor. Anti-aircraft fire control runs on the same loop.

Another variant: **informative feedback.** Steering a car on an icy road, you don't wait for a skid to tell you the road is slick — you can't, the skid arrives too late. You give the wheel small fast impulses, too small to throw the car, and read the kinaesthetic response. You're injecting a probing signal and reading the effector's transfer function. The compensator adjusts its setting based on what comes back. The road has changed; you've measured the change before it cost you anything.

This is a feedback that **observes the system, not the error.** Modify the compensator from the outside; superimpose a small high-frequency probe on the input; pick the probe back off the output through a filter; read the amplitude-phase relation; update the compensator's settings. It works as long as the load changes secularly (slowly) compared to the inputs you're trying to track, and as long as the load can be characterized by a small number of parameters.

## Homeostasis — the slow loop underneath

Wiener has been talking about fast feedback — voluntary motion, ship steering, anti-aircraft control. He closes by widening the frame.

The human body holds an enormous number of variables inside narrow tolerances: temperature within half a degree, blood pH within strict bounds, osmotic pressure, heart rate, blood pressure, leucocyte counts, calcium balance, the timing of the sex cycle. **Our inner economy contains an assembly of thermostats, automatic pH controls, governors — adequate for a large chemical plant.** This is *homeostasis*.

Homeostatic feedbacks differ from voluntary and postural ones in one general way: **they're slow.** Almost nothing in the body's chemistry produces serious permanent damage in a fraction of a second (cerebral anemia is the rare exception). The fibres reserved for homeostasis — the sympathetic and parasympathetic — are often non-myelinated, transmitting more slowly than the myelinated fibres of voluntary control. The effectors — smooth muscle, glands — are slower than striped muscle. Many messages don't run on nerves at all: anastomosis in the heart, hormones in the blood, the carbon dioxide concentration itself. All slower than a motor nerve.

**So feedback is not one thing. It's a class — fast/slow, voluntary/involuntary, signal-based/chemical, position/temperature/concentration/rate. The cerebellar tremor at the opening was one species of broken loop. The homeostatic failures (fever, ketoacidosis, electrolyte collapse) are another species of the same genus, running at a different timescale on different substrate.**

That's the chiasm. The chapter opens with a man whose hand swings past the cigarette and closes with the recognition that the same kind of loop, much slower and largely invisible, is what's been keeping his cells alive while he sits there trying to grab it.

---

*Structure choice: chiasm. The chapter opens with motor pathology (ataxia from broken feedback) and closes with homeostasis (the slow vital feedback that the opening didn't yet name). The math in the middle is the explanatory bridge — it tells you why a single feedback can't stabilize a complex effector cascade, which is why limb motion needs postural feedbacks underneath voluntary ones, which is the same architecture homeostasis uses. The frame inversion: feedback as visible motor control → feedback as the slow invisible substrate of being alive.*

*What I cut: the per-operator algebra for the cardioid and other Nyquist plots (kept the structural takeaways and the diagram); the secular-perturbation infinite linear system in \\(\delta a_n\\); the friction correction to the ship-steering example (kept the main result); the second compensator+feedback diagram (kept the first); Cannon and Henderson footnote pointer; numbered equations except where the formula itself was load-bearing.*

*What I added: the load-bearing one-liners are bolded — Wiener has no italics there. The closing chiasm summary is mine. The Nyquist-style SVG diagram is generated from Wiener's prose description; he had only the cardioid plot inline.*
