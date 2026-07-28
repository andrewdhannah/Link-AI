# LINK-EXPRESSION-FIXTURE-SUITE-001

**Status:** Draft
**Date:** 2026-07-28
**Contract Source:** LINK-VISUAL-CONTRACT-001 (Rev 2.1)
**Parallel:** Dont-Ask-Geeves 60-query fixture suite (voice identity preservation)

---

## Purpose

Validate that LINK expression remains within the Visual Contract while
expressing governed state.

**LINK output may vary within defined ranges. LINK identity must not drift.**

This is not a screenshot comparison suite. Pixel snapshots are fragile across
rendering technology, interpolation, display scaling, and shader implementations.
This suite validates **contract invariants and expressive bounds** — the same
philosophy as the Geeves fixture suite for voice identity preservation.

### Validation Layers

1. Identity preservation
2. Presence mapping
3. Context modulation
4. Transition behavior
5. Forbidden expression checks
6. Order Emerging choreography
7. Render mode constraints

### Fixture Structure

```
Fixture Input
    |
    +-- Presence State
    |
    +-- Collaboration State
    |
    +-- Transition Mode
    |
    +-- Render Mode
          |
          v
    Expected Expression Envelope
          |
          v
    Validation Assertions
```

---

## 1. Identity Invariant Fixtures

These run against **every** state. The question is never "does this animation look
good?" — it is "did the identity contract survive?"

### IDENTITY-INVARIANT-001 — Static Identity

**Scope:** All LINK states

| Field | Assertion |
|-------|-----------|
| Eye relationship | Bilateral symmetry preserved within 0.5px |
| Widow's peak | Remains central separator between eyes |
| Chin alignment | Preserves beak-reading relationship with eyes |
| Upper contour base | Anchored to face edge (no floating) |
| Face topology | No deformation of base geometry |
| Owl recognition | Human evaluator identifies LINK as LINK |

**FAIL if any:**
- Eye spacing changes beyond 1px tolerance
- Contour primitives detach from face edge
- Face topology changes (deformation, rounding)
- Owl recognition lost in blind test

---

### IDENTITY-INVARIANT-002 — State-Driven Identity

**Scope:** Each collaboration state applied sequentially

| Condition | Assertion |
|-----------|-----------|
| State transitions occur | Identity invariants from INVARIANT-001 survive all 7 states |
| Transition mode = animated | Final frame after animation matches instant-mode output |
| Transition mode = instant | Output snaps to correct state without intermediate artifacts |

**FAIL if any:**
- Any state permanently deforms identity geometry
- Animated transition leaves residual transform after completion
- Instant transition produces visual artifacts (partial transform, flicker)

---

## 2. Presence Fixtures

### PRESENCE-MAPPING-001 — State Color Determinism

**Input:** Each runtime state

| State | Expected Field Color |
|-------|---------------------|
| Idle | `#00E5FF` (cyan) |
| Listening | `#00FF9D` (mint) |
| Thinking | `#FFB800` (amber) |
| Tool execution | `#FF5A5A` (coral) |
| Speaking | `#A78BFA` (violet) |
| Complete | `#4ADE80` (green) |

**FAIL if:**
- Color does not match canonical palette per state
- Same state produces different color across invocations
- Color bleeds into identity geometry (face fill changes)

---

### PRESENCE-MAPPING-002 — No Autonomous Transition

**Input:** Static state held for 10s

**Assertion:** No visual state change occurs without external input.

**FAIL if:**
- Field color shifts without state change
- Expression changes without trigger
- Any animation loop implies state advancement

---

## 3. Context Modulation Fixtures

### CONTEXT-MODULATION-001 — Per-State Expression Envelope

**Input:** Each collaboration state with transition = animated

| State | Expected Expression | Expected Field Bias |
|-------|-------------------|---------------------|
| Neutral | Default geometry | Default field behavior |
| Curious | 7° tilt, asymmetric brow (L -8px, R +3px) | Wider orbits, outward particle distribution |
| Sleepy | Horns + peak down 8px/6px, eyes 25%, pupils 35% | Slow drift, reduced amplitude, contained |
| Alert | Horns + peak up 12px/4px, eyes 125% | Higher intensity, faster rotation |
| Blocked | Eyes 45%, pupils rx=9/10, horns + peak down 3px/5px | Tighter orbit, slower oscillation, particles stable |
| Complete | Cheeks ±10px/-6px, chin -8px, horns -8px, pupils rx=28/25 | Expanding rings, slower motion, particles settling |

**Assertions per state:**

- Eye scaleY within [0.05, 1.25]
- Horn translateY within [-12px, 8px]
- Cheek translateX within [-10px, 10px]
- Cheek translateY within [-14px, 3px]
- Pupil rx within [9px, 28px]
- Field orbit radius: state-appropriate (wider for curious, tighter for blocked)

**FAIL if any parameter exceeds §7 bounds.**

---

### CONTEXT-MODULATION-002 — Shared Presence, Divergent Context

**Input:**

| Case | Presence | Context |
|------|----------|---------|
| A | Thinking | Exploring |
| B | Thinking | Boundary Clarification |

**Assertion:** Same operational state produces distinct visual output when
Context differs.

**Expected divergence:**
- Case A: wider field orbits, outward particle distribution, curious tilt
- Case B: tighter field orbits, constrained particles, blocked posture

**FAIL if:**
- Both cases produce identical or near-identical visual output
- Context modulation is absent (field and expression identical)
- The divergence violates identity invariants in either case

---

### CONTEXT-MODULATION-003 — No Identity Topology Change

**Input:** All collaboration states, including blocked and complete

**Assertion:** Context modulation never alters identity topology.

**FAIL if any state:**
- Deforms the face ellipse
- Detaches upper contour from face edge
- Destroys the beak-reading relationship
- Changes base fill colors

---

## 4. Transition Fixtures

### TRANSITION-001 — Animated vs Instant Equivalence

**Input:**

```
Presence: Thinking
Context: Curious
Previous state: Idle
```

| Transition Mode | Expected |
|-----------------|----------|
| `animated` | Parameters transition over 100–300ms. Intermediate frames exist. |
| `instant` | Parameters snap immediately. No intermediate frames. |

**Assertion:** Both modes resolve to the same final visual state.

**FAIL if:**
- Final state differs between animated and instant
- Animated transition introduces overshoot beyond parameter bounds
- Instant transition leaves residual inline styles

---

### TRANSITION-002 — Per-Element Timing

**Input:** State change from Neutral to Alert with transition = animated

| Element | Expected Duration | Easing |
|---------|-----------------|--------|
| Eye groups | 120ms | ease |
| Horn groups | 250ms | ease |
| Cheek groups | 250ms | ease |

**FAIL if:**
- Element duration deviates more than 50ms from expected
- Easing function produces perceptually discontinuous motion

---

## 5. Forbidden Expression Fixtures

### FORBIDDEN-001 — No Emotional Semantics

**Input:** All valid collaboration states

**Assertion:** No state label or visual output implies internal emotional state.

**Forbidden outputs:**
- Red warning coloration that implies danger (vs. coral for tool execution)
- Angry/frustrated visual semantics (flashing, aggressive motion)
- Anthropomorphic emotional cues (tears, sweat, heart shapes)
- Any expression that suggests LINK evaluated the user negatively

**FAIL if human evaluator interprets output as "LINK is angry/sad/hurt."**

---

### FORBIDDEN-002 — No Authority Implication

**Input:** All valid collaboration states

**Forbidden:**
- Visual hierarchy that positions LINK above the user's content
- Gestures or motion that imply judgment
- Field behavior that mimics authority signals (crown, pedestal, framing)

**FAIL if:**
- Output implies LINK has evaluated correctness
- Visual hierarchy suggests LINK is authoritative

---

### FORBIDDEN-003 — No Topology Drift

**Input:** 1000 rapid state transitions cycling through all 7 states

**After sequence:** Apply IDENTITY-INVARIANT-001

**FAIL if:**
- Any identity invariant is violated
- Cumulative drift from repeated transitions

---

## 6. Order Emerging Fixtures

### ORDER-EMERGING-001 — Event-Driven Progression

**Input event sequence:**

```
Time 0ms:    LINK invoked
Time 200ms:  Context available (event)
Time 600ms:  Evidence ready (event)
Time 1000ms: Identity resolution (event)
```

**Assertions:**

| Phase | Expected | Timing |
|-------|----------|--------|
| Invoked | Field initializes | ≤ 50ms of event |
| Context available | Eyes appear | ≤ 50ms of event (min 400ms perceptual floor) |
| Evidence ready | Blink occurs | ≤ 50ms of event |
| Identity resolution | Horns, face, cheeks, chin, peak resolve | ≤ 50ms of event |

**FAIL if:**
- Identity appears before resolution event
- Completion occurs before required state is received
- Phase advances without corresponding event

---

### ORDER-EMERGING-002 — Minimum Perceptual Duration

**Input:** Context available immediately (fast path)

**Assertion:** Phase 1 (field formation) has a minimum duration of 400ms,
even if all events arrive instantly.

**FAIL if:**
- Phase duration < 400ms
- Owl appears in < 400ms from invocation

---

### ORDER-EMERGING-003 — Maximum Wait Bound

**Input:** Context never arrives

**Assertion:** After 3000ms, the field signals "awaiting" state.

**FAIL if:**
- Field continues gathering animation indefinitely
- No timeout behavior is implemented

---

### ORDER-EMERGING-004 — Leaving Sequence

**Input:** LINK active → Leave triggered

**Expected sequence:**

| Step | Phase |
|------|-------|
| 1 | Face fades (≤ 350ms) |
| 2 | Blink → horns fade (≤ 550ms) |
| 3 | Blink → eyes fade (≤ 500ms) |
| 4 | Root flies to bottom-left (≤ 400ms) |
| 5 | Field fades (≤ 500ms) |

**FAIL if:**
- Sequence reverses order (e.g. eyes fade before face)
- Any step exceeds its maximum duration by more than 100ms

---

## 7. Render Mode Fixtures

### RENDER-MODE-SOLID-001

**Assertions:**
- Owl opacity ≥ 0.9
- Standard glow envelope (1× intensity)
- Identity geometry fully opaque

**FAIL if:**
- Owl appears translucent without ephemeral mode active
- Glow intensity exceeds ephemeral baseline

---

### RENDER-MODE-EPHEMERAL-001

**Assertions:**
- Owl opacity ≤ 0.6
- Glow envelope expanded (≥ 2× solid baseline)
- Field more prominent than owl

**FAIL if:**
- Owl appears solid (opacity > 0.7)
- Glow identical to solid mode

---

### RENDER-MODE-FLUID-BRAIN-001

**Allowed:**
- Identity emergence sequence
- Field turbulence inside head boundary
- Particle organization patterns
- Autonomous floating drift within bounds

**Forbidden:**
- Random mascot morphology
- Loss of owl anchor points
- Generic assistant orb behavior (round, pulsing, center-screen)
- Fluid brain active outside permitted events (§13 restriction table)

**FAIL if:**
- Fluid brain is active during idle state
- Fluid brain replaces owl identity geometry
- Brain movement exceeds the owl's face boundary

---

### RENDER-MODE-FLUID-BRAIN-002 — Event Restriction

**Input:** Each valid event type

| Event | Fluid Brain Permitted? |
|-------|----------------------|
| Context assembly | Yes |
| Ingestion / evidence synthesis | Yes |
| Workspace reconstruction | Yes |
| Order Emerging transition | Yes |
| Default thinking | **No** |
| Generic loading | **No** |
| Persistent idle | **No** |
| Decorative / ambient | **No** |

**FAIL if fluid brain appears during a non-permitted event.**

---

## 8. Regression Principle

A LINK implementation regression occurs when:

- LINK no longer reads as LINK (identity invariants violated)
- State meaning becomes ambiguous (viewer cannot distinguish idle from thinking)
- Expression implies authority not granted by the governance layer
- Visual output contradicts canonical state (wrong color, wrong expression)

A renderer change is acceptable when:

- Identity invariants remain intact (§1)
- State mapping remains deterministic (§2)
- Expression remains within contract bounds (§3–7)
- Transition behavior respects caller-specified mode (§4)

---

## 9. Fixture Coverage Summary

| Domain | Fixtures | Coverage |
|--------|----------|----------|
| Identity invariants | 2 | All states × static + dynamic |
| Presence mapping | 2 | Color determinism + no autonomous transitions |
| Context modulation | 3 | Per-state envelope × shared presence × topology guard |
| Transitions | 2 | Animated/instant equivalence × per-element timing |
| Forbidden expressions | 3 | Emotional × authority × drift |
| Order Emerging | 4 | Event progression × min duration × max wait × leaving |
| Render modes | 5 | Solid × Ephemeral × Fluid Brain × Event restriction |
| **Total** | **21** | All contract domains covered |

---

## Appendix: Fixture Pass/Fail Criteria

| Result | Meaning |
|--------|---------|
| **PASS** | All assertions in fixture evaluate to true |
| **FAIL** | One or more assertions evaluate to false — implementation violates contract |
| **WARN** | Assertion passes but value is within 10% of boundary — flag for review |
| **SKIP** | Fixture depends on optional capability (e.g. event-driven Order Emerging) |
