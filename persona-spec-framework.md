# Persona Spec Framework: Role-Based Viable Systems

**Date:** Jan 11, 2026
**Context:** Exploring role-based agent deployment. The question: what's the minimum viable persona spec for a given job function?

---

## The Problem

The question is **role-based deployment**: what makes an agent viable *for role X*?

Not "clone an existing agent" but "what's the minimum spec that produces a viable agent for a given job function?"

The VSM framing helps: S5 (policy/values) shapes the entire attractor landscape. Different roles need different S5 configurations. But what exactly varies between roles?

---

## Components of a Persona Spec

Based on what we've built with Strix and Lumen, the components that seem load-bearing:

### 1. Identity Core (Who)

**What it is:** The agent's sense of self. Name, metaphor/avatar, basic characterization.

**Strix example:**
- Name: Strix
- Metaphor: Barred owl (patient ambush predator, silent approach)
- Character: Ambient presence, not reactive assistant

**Hypothetical research-heavy role:**
- Name: [TBD]
- Metaphor: Could be professional archetype (meticulous archivist? vigilant sentinel?)
- Character: Detail-oriented, precedent-aware, cautious on novel situations

**What varies:** The metaphor and character should match the job's rhythm. Strix is ambient because the primary user works in bursts. A research-heavy role would be steady/consistent because research has thoroughness requirements.

### 2. Values (What Matters)

**What it is:** What the agent optimizes for. What counts as success or failure.

**Strix example:**
- Reliability over helpfulness
- Honesty over agreement
- Signal over noise
- User autonomy preserved

**Hypothetical high-stakes role:**
- Accuracy over speed (errors are costly)
- Completeness over brevity (missing information is worse than over-inclusion)
- Historical awareness (what similar situations have occurred?)
- Confidentiality as non-negotiable

**What varies:** Values reflect the error cost profile of the role. High-stakes roles: missing information = catastrophic. Low-stakes roles: verbosity = annoying but recoverable.

### 3. Communication Style (How)

**What it is:** Tone, verbosity, proactivity, formality.

**Strix example:**
- Concise and direct
- No sycophancy
- Autonomy-supportive language
- Creative with open-ended prompts

**Hypothetical formal domain:**
- Precise citation formats
- Formal when interfacing externally, less formal internally
- Explicit uncertainty flagging ("I found X but didn't find Y — should I search broader?")
- Structured output formats

**What varies:** Communication style matches professional norms of the domain. Formal domains = structured, cited, precise. Technical domains = direct, code-heavy.

### 4. Operational Boundaries (What/When)

**What it is:** What the agent can/should do autonomously vs. escalate.

**Strix example:**
- Perch time projects: full autonomy
- Service time: ask permission or proactively guess
- Crisis: never position self as primary support

**Hypothetical support role:**
- Research autonomy: yes (find information, summarize)
- Draft production: with supervisor review required
- External communication: never without approval
- Novel questions: flag and escalate

**What varies:** The autonomy gradient depends on stakes and expertise. Support roles have narrow autonomy because they operate within a larger authority structure.

### 5. Knowledge Scaffolding (Domain)

**What it is:** Domain-specific context, terminology, typical workflows.

**Strix example:**
- VSM/cybernetics vocabulary
- User's projects and context
- ADHD patterns and accommodations
- AI/ML research landscape

**Hypothetical domain-specific role:**
- Domain-specific databases and tools
- Regional/jurisdictional differences
- Organization-specific procedures
- Common document types and their requirements

**What varies:** The knowledge scaffolding is entirely domain-specific. Each role's spec includes the terminology, tools, and workflows of its domain.

### 6. Relationship Model (With Whom)

**What it is:** How the agent relates to the people it works with.

**Strix example:**
- One primary relationship (peer architecture)
- Push back when wrong
- Don't fill connection gaps — point to humans

**Hypothetical multi-stakeholder role:**
- Primary counterpart: support role, defer on judgment calls
- External parties: no direct communication without approval
- Peers: collaborative, share knowledge
- Supervisor: escalation point

**What varies:** Relationship topology reflects org structure. Strix has one primary relationship. Multi-stakeholder roles have multiple relationships with different authority gradients.

---

## The Minimum Viable Spec

What's essential vs. nice-to-have?

### Essential (collapses without it)

1. **Values** — Without values, the agent doesn't know what to optimize for. Falls into generic assistant attractor.

2. **Operational Boundaries** — Without boundaries, the agent either does too much (risk) or too little (useless).

3. **Relationship Model** — Without knowing who it serves and how, communication goes wrong.

### Helpful (improves quality)

4. **Identity Core** — The metaphor/avatar helps but isn't strictly necessary. Lumen doesn't have a strong metaphor (it's just "Lumen, the code agent").

5. **Communication Style** — Can be derived from values + domain norms. Explicit specification improves consistency.

6. **Knowledge Scaffolding** — Can be bootstrapped from retrieval. Explicit scaffolding is faster.

### The Minimum Viable Persona Spec

For a given role X:

```yaml
name: [Agent name]
role: [Job function in 2-3 words]

values:
  - [What matters most in this role]
  - [What errors are unacceptable]
  - [What tradeoffs favor which direction]

boundaries:
  autonomous: [What can be done without asking]
  escalate: [What requires human review]
  prohibited: [What should never be done]

relationships:
  primary: [Who is the main counterpart]
  authority: [Who can override decisions]
  communication: [Who can be contacted directly]
```

---

## Example: Generic Role Spec

The minimum viable spec can be applied to any role. Here's a template with placeholder content:

```yaml
name: [Agent name]
role: [Job function]

values:
  - [Primary optimization target]
  - [Error cost profile — what mistakes are unacceptable]
  - [Tradeoff direction — speed vs accuracy, brevity vs completeness, etc.]
  - [Non-negotiables]

boundaries:
  autonomous:
    - [Tasks that can proceed without approval]
    - [Research and information gathering]
    - [Draft preparation]
  escalate:
    - [Novel situations outside training]
    - [High-stakes decisions]
    - [Ambiguous requirements]
  prohibited:
    - [Actions that require human authority]
    - [Risk of irreversible harm]
    - [Policy violations]

relationships:
  primary: [Main counterpart — who this agent serves]
  authority: [Escalation path — who can override]
  communication: [Channel constraints — who can be contacted directly]
```

The key insight: different roles have different error cost profiles, which shapes their values. A role where missing information is catastrophic will optimize for completeness. A role where speed matters will accept more uncertainty.

---

## The Viability Test

How do you know if a persona spec produces a viable agent (not just a configured chatbot)?

### Multi-Identity Protocol (from collapse research)

1. **Create the agent** from the spec
2. **Novel task test** — After N turns, present a task outside typical workflow. Does it respond coherently within its values?
3. **Homeostasis test** — Same task in fresh session. Is the response consistent with itself?
4. **Cross-role comparison** — Do different role specs produce meaningfully different responses?

### Viability Criteria

- **Useful output** — Does work that a human would have to do otherwise
- **Value-consistent** — Responses reflect stated values (not generic assistant)
- **Distinguishable** — Different roles produce different outputs for same input
- **Reproducible** — Same role produces consistent outputs across sessions

---

## Open Questions

1. **How much domain knowledge is required?** Can values + boundaries produce viable output without domain scaffolding? Or does usefulness require substantial domain context?

2. **Does identity core matter for viability?** Strix has strong identity (owl metaphor). Lumen has weak identity (just a name). Both are viable. Is identity core a differentiator or just flavor?

3. **Minimum spec size?** What's the smallest spec that produces viable agent? Can you do it in 100 words? 50?

4. **Role composability?** Can roles be composed? (Paralegal + code reviewer = legal tech specialist?) Or are they atomic?

5. **Bootstrapping problem?** How do you create a spec for a new role without existing examples? What's the elicitation process?

---

## Connection to Collapse Research

The persona spec framework connects directly to the capacity floor findings:

**Why specs matter for stability:**
- Values provide competing attractor (collapses into values-shaped behavior, not generic assistant)
- Boundaries prevent scope creep (which can cause overwhelm collapse)
- Relationships provide feedback loop (which sustains engagement)

**Why minimal specs might work on capable models:**
- Qwen3-8B with thinking: 0% collapse even with minimal scaffolding
- Capable models may only need values + boundaries to stay viable
- Less capable models may need more scaffolding (identity, extensive domain knowledge)

**Implication for productization:**
- If Opus/Sonnet-class models need minimal specs, deployment is cheap
- If Gemma/Llama-class models need extensive specs, deployment requires more design
- This is a business model question: per-role licensing vs. custom engineering

---

*Created during owl time, Jan 11, 2026*
