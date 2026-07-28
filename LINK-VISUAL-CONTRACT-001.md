# LINK-VISUAL-CONTRACT-001

**Status:** Ratified
**Date:** 2026-07-28
**Revision:** 2 — Three-plane model, collaboration states, event-driven choreography
**Source:** LINK.svg (canonical geometry), LINK-Exact-+-Ephemeral-+-Emotions.html (POC)
**Validation:** Verified against rendered output — invariant checks pass in current implementation.

---

## 1. Purpose

Define the visual contract for LINK as a governed projection of platform state.
This is a constraint artifact — future implementations (SwiftUI, WebView, Metal,
WebGPU) may vary technically but must preserve these invariants.

**LINK does not have emotions. LINK has collaboration states.**

A collaboration state describes the relationship between LINK, the Owner, and
the current work context. The visual system expresses this relationship across
three coordinated planes — it does not simulate an internal emotional life.

---

## 2. Three-Plane Visual Model

LINK communicates across three coordinated planes:

```
                         LINK
                            |
              +-------------+-------------+
              |             |             |
          Identity       Presence      Context
              |             |             |
          "Who"         "Doing"       "Relating"
              |             |             |
          Geometry       Field        Modulation
```

| Plane | Question Answered | Source | Visual Mechanism |
|-------|------------------|--------|------------------|
| **Identity** | What is LINK? | LINK.svg | Owl geometry — invariant |
| **Presence** | What is LINK doing? | Runtime state | Field behavior, motion, glow |
| **Context** | What is happening between LINK and Owner? | Interaction state | Expression + field modulation |

### Precedence Rules

| Rule | Expression |
|------|------------|
| **Identity defines existence.** | Owl geometry never changes. |
| **Presence defines operation.** | Field communicates system state. |
| **Context defines relationship.** | Expression and field modulation communicate collaboration state. |
| **Context may influence Presence.** | Field widens/tightens/colors based on relationship. |
| **Context may influence expression.** | Face geometry shifts (brow, eye, cheek) per state. |
| **Context may never alter Identity topology.** | No feature deformation, no topology change, no detached movement. |

### Two-State Sharing Rule

Two states may share the same Presence but have different Context.

**Example:**

| | Presence | Context |
|---|---|---|
| Scenario A | Thinking | Exploring idea |
| Scenario B | Thinking | Boundary clarification |

Same operation. Different relationship. The field should not look identical —
Context modulates the field even when Presence is the same.

---

## 3. Identity Geometry Invariant

LINK identity is encoded through **relational geometry**, not individual feature
shapes. The perceived identity (owl) emerges from the relationships between
primitives.

### Source Geometry

The canonical geometry is `LINK.svg` — an Inkscape-authored vector at 400×400 px,
viewBox `0 0 400 400`. All implementations must use these exact path coordinates.

| Primitive | Role | SVG Element |
|-----------|------|-------------|
| Face | Primary facial disk | `ellipse cx=207.81 cy=207.07 rx=174.09 ry=120.15` |
| Left cheek | Lower-left facial contour | `ellipse cx=82.18 cy=233.71 rx=58.59 ry=60.89` |
| Right cheek | Lower-right facial contour | `ellipse cx=330.18 cy=235.68 rx=58.59 ry=60.89` |
| Chin | Lower contour — produces beak illusion | `path` (complex bezier) |
| Left upper contour | Brow / facial disk extension | `path` (complex bezier) — historically "left horn" |
| Right upper contour | Brow / facial disk extension | `path` (complex bezier) — historically "right horn" |
| Widow's peak | Central divider — eye separation, brow continuity | `path` (complex bezier) |
| Left eye | Fixed owl-recognition anchor | `ellipse cx=140.77 cy=204.36 rx=60.85 ry=59.80` |
| Right eye | Fixed owl-recognition anchor | `ellipse cx=270.84 cy=208.43 rx=60.85 ry=59.80` |
| Left pupil | Gaze indicator | `ellipse cx=143.02 cy=214.69 rx=22.54 ry=19.03` |
| Right pupil | Gaze indicator | `ellipse cx=270.70 cy=217.89 rx=21.41 ry=20.12` |

### Color Palette

| Element | Hex | Role |
|---------|-----|------|
| Face, cheeks, chin | `#164450` | Primary fill — never changes |
| Horns, widow's peak | `#0b2228` | Contour / separator (same color — continuous brow silhouette) |
| Eye sclera | `#53676c` | Eye bed — never changes |
| Pupils | `#dbe2e3` | Gaze — never changes |
| Default glow | `#00E5FF` | Presence field — variable by state |

### Perceptual Construction

The following geometries have no independent interpretation. They function only
through their relationships:

- **Beak:** Does not exist as a path. The brain constructs it from the
  relationship between widow's peak, eye spacing, and chin alignment.
- **Upper contours (horns):** Not horns. They are facial-contour extensions
  that serve as brows when the eyes move. They define the face shape, not
  an independent feature. The devil-horns reading is a failure mode that
  occurs when they are interpreted as detached objects.
- **Widow's peak:** Separates the eyes and bridges the upper contour.
  If moved independently from the contours, the face geometry fragments.

### Invariant Rules

**Preserved under all allowed transformations:**

- Eye-to-eye symmetry (bilateral)
- Widow's peak as central separator between eyes
- Upper contour continuity (left + right form a continuous brow line)
- Chin-to-eye alignment (produces beak reading)
- Upper contour base anchored to face edge (not floating)

### Forbidden Transformations

| Forbidden | Why |
|-----------|-----|
| Independent feature deformation | Breaks the relational construction — individual primitives interpreted as detached objects |
| Topology changes | Replaces relational geometry with generic rounded forms — brain defaults to "mammal/mascot" |
| Feature detachment | Upper contour moving independently from face edge — breaks the owl silhouette |
| Eye/chin/widow's-peak relationship destroyed | Collapses the beak illusion |

---

## 4. Presence Field

The presence field communicates **what LINK is doing**. It is the operational
signal layer.

### Allowed Expression

| Dimension | Methods |
|-----------|---------|
| Activity | Particle motion, field ring rotation, turbulence intensity |
| Attention | Glow intensity, ring expansion |
| Processing | Internal flow, constrained displacement (fluid mode) |
| Communication | Audio-reactive modulation (future), speech rhythm |
| Completion | Settle animation, return to identity stillness |

### State Colors

| State | Color | Hex |
|-------|-------|-----|
| Idle | Cyan | `#00E5FF` |
| Listening | Mint | `#00FF9D` |
| Thinking | Amber | `#FFB800` |
| Tool execution | Coral | `#FF5A5A` |
| Speaking | Violet | `#A78BFA` |
| Complete | Green | `#4ADE80` |

### Constraint

The presence field must not alter identity recognition.
The owl must remain readable as the owl regardless of field state.

---

## 5. Context Modulation

Context is not a third rendering layer. It is a **modulation layer** over Presence.

Context lives in two places:

| Channel | What It Modulates | Examples |
|---------|-------------------|----------|
| **Expression** | Face geometry | Brow lift, eye squint, cheek raise, head tilt |
| **Field bias** | Field behavior | Orbit radius, particle distribution, oscillation speed |

### Modulation by State

| State | Expression | Field Bias |
|-------|------------|------------|
| Neutral | Default geometry | Default field behavior |
| Curious / Exploring | 7° head tilt, asymmetric brow (left up 8px, right down 3px) | Wider orbits, outward particle movement, distributed |
| Sleepy / Waiting | Horns + peak push down 8px/6px, eyes 25% height, pupils 35% | Slow drift, reduced amplitude, contained |
| Alert | Brows + peak lift 12px/4px, eyes 125% | Higher field intensity, faster rotation |
| Blocked / Boundary | Squint 45%, pupils contracted to rx=9/10, horns + peak down 3px/5px | Tighter orbit radius, slower oscillation, particles held in stable orbit, no outward expansion |
| Complete / Alignment | Cheeks out 10px + up 6px, chin up 8px, horns up 8px, pupils enlarged to rx=28/25 | Expanding rings, slower broader motion, particles settling outward |

### Field Modulation Parameters (per state)

| Parameter | Curious | Blocked | Complete |
|-----------|---------|---------|----------|
| Orbit radius | Wide | Tight | Expanding |
| Particle distribution | Outward, sparse | Held, dense | Settling, dispersing |
| Oscillation speed | Moderate | Slow | Decelerating |

---

## 6. Collaboration State Vocabulary

LINK does not have emotions. LINK has **collaboration states**.

A collaboration state describes the relationship between LINK, the Owner, and
the current work context — not an internal emotional state.

### Valid States

| State | Description | Identity | Presence | Context |
|-------|-------------|----------|----------|---------|
| Idle | Waiting, no active work | Neutral, breathing | Low-amplitude, stable cyan glow | Default |
| Listening | Attending to input / awaiting Owner | Neutral, open | Expanded field, outward attention motion | Receptive |
| Thinking / Processing | Computing, gathering context | Neutral, still | Internal constrained turbulence, amber | Curious tilt if exploring; blocked posture if boundary conflict |
| Tool execution | Running a tool | Alert posture | Directional pulses, activity path, coral | Alert engagement |
| Speaking | Audio output | Neutral | Audio-reactive modulation, violet | — |
| Complete | Shared objective reached | Soft squint, lifted contour | Settling, expanding rings, green | Alignment (cheeks up, pupils large) |
| Blocked | Contract boundary requires clarification | Narrowed aperture, downward brow | Tight orbits, slow, contained | Guarded posture |
| Curious | Context expansion, information gathering | 7° tilt, asymmetric brow | Wide orbits, outward movement | Exploratory |

### Invalid Implications

LINK must not visually imply:

| Invalid Implication | Why |
|--------------------|-----|
| Authority | LINK is a projection, not a decision-maker |
| Approval / correctness | LINK renders state, does not evaluate it |
| Trust | Trust is a governance property, not a visual one |
| Internal emotional state | Mood-descriptive labels ("angry") create ambiguous signals |
| Independent judgment | Any expression that suggests LINK evaluated something itself |

---

## 7. Allowed Identity Transformations

Identity geometry may move as a **rigid facial system**. Internal relationships
must remain invariant.

### Permitted

| Transformation | Application | Example |
|---------------|-------------|---------|
| Uniform scale | Breathing animation | `scale(0.98–1.02)` from center |
| Uniform compression | Expression accent | `scaleY(0.05–1.25)` on eye groups |
| Rigid group translation | Brow movement | `translateY(-12–8px)` on upper contour |
| Coordinated pupil shift | Gaze direction | `translateY(2px) scale(0.35)` |
| Coordinated cheek shift | Smile / lift | `translate(±10px, -14px)` |
| Whole-system translation | Fly-in / fly-out | `translate(-300px, 280px)` on root group |
| Whole-system rotation | Head tilt (curious) | `rotate(7deg)` on root group |

### Forbidden

| Forbidden | Why |
|-----------|-----|
| Bend upper contour tip independently | Would break face-edge continuity — shape detaches, reverts to "horn" reading |
| Deform eye/widow's-peak independently | Would break eye-separation and beak illusion |
| Scale individual cheek independently | Would break bilateral symmetry |
| Move pupil without eye group | Would detach gaze from eye frame |

### Transform Parameter Bounds

| Parameter | Min | Max | Step | Notes |
|-----------|-----|-----|------|-------|
| Eye scaleY (expression) | 0.05 | 1.25 | continuous | Blink = 0.05, sleepy = 0.25, alert = 1.25 |
| Upper contour translateY | -12px | 8px | continuous | Negative = lift (alert/complete), positive = lower (sleepy/blocked) |
| Cheek translateX | -10px | 10px | continuous | Outward = smile |
| Cheek translateY | -14px | 3px | continuous | Negative = lift (complete), positive = dip (blink) |
| Chin translateY | -12px | 0px | continuous | Negative = lift (complete) |
| Peak translateY | -6px | 6px | continuous | Negative = lift, positive = lower |
| Pupil scale | 0.35 | 1.0 | continuous | Smaller = sleepy/blocked, normal = neutral |
| Pupil rx | 9px | 28px | continuous | Larger = brighter (complete) |
| Link root scale | 0.3 | 1.05 | continuous | Uniform from center — breathing + fly |
| Link root translate | -300px | 0px | continuous | X: fly from bottom-left |
| Link root translate | 0px | 280px | continuous | Y: fly from bottom-left |
| Link root rotate | -7° | 7° | continuous | Head tilt (curious) |

---

## 8. State Transitions

Transitions between collaboration states may be:

| Mode | Behavior | When Used |
|------|----------|-----------|
| **Animated** | Expression parameters transition over a duration (100–300ms) | Default — smooth state changes during active use |
| **Instant** | Expression parameters snap immediately with no transition | On state initialization, during choreographed sequences (Order Emerging), or when the runtime requires immediate clarity |

Both modes must preserve the same final visual state for a given collaboration
state. The transition mode affects only the intermediate frames.

### Per-Element Transition Defaults

| Element | Default Duration | Easing |
|---------|-----------------|--------|
| Eye groups | 120ms | ease |
| Pupil groups | 120ms | ease |
| Horn groups | 250ms | ease |
| Cheek groups | 250ms | ease |
| Link root (fly, tilt) | 400–500ms | cubic-bezier(0.34, 1.56, 0.64, 1) |
| Opacity (fade) | 300–700ms | ease |

---

## 9. Order Emerging Choreography

Order Emerging is the signature LINK appearance sequence. It communicates:
context arriving, information organizing, identity becoming available.

### Lifecycle

```
LINK invoked (Owner action / system event)
        |
        v
Phase 1 — Presence field initializes
   (minimum perceptual duration: 600ms)
        |
        v
Phase 2 — Context assembly (event-driven)
   +-- Context already available? --> skip to Phase 3
   +-- Context unavailable? --------> field remains in gathering state
   |                                    until context arrives
   v
Phase 3 — Identity resolution begins
        |
        v
   Eyes appear (400ms fade)
        |
   Blink (120ms)
        |
   Horns / brows fade in (500ms)
        |
   Face, cheeks, chin, peak fade in (600ms)
        |
        v
Phase 4 — Owl geometry fully resolved
        |
        v
Phase 5 — Transition to active state (fluid or solid)
```

### Timing Rules

| Rule | Value |
|------|-------|
| Minimum phase duration | 400ms (prevents instant flash) |
| Maximum wait for context | 3000ms (after which field signals "awaiting" state) |
| Event arrival | Advances choreography immediately to next phase |
| Renderer responsibility | Never invents completion — phases are event-advanced |

### Leaving (reverse sequence)

```
Active state
        |
Phase 1 — Face fades (350ms)
Phase 2 — Blink → horns fade (550ms)
Phase 3 — Blink → eyes fade (500ms)
Phase 4 — Fly out to bottom-left (400ms)
Phase 5 — Presence field fades (500ms)
        |
LINK dismissed
```

---

## 10. Invocation and Spatial Behavior

### Entrance

LINK enters from the **bottom-left corner** of its container:

```
+--------------------------------+
|                                |
|                                |
|                                |
|                                |
|                                |
| LINK ← enters from here       |
+--------------------------------+
```

This communicates: LINK is a tool summoned from the workspace edge, not a
character walking onto a stage. It occupies a defined region and retreats
when dismissed.

### Dismissal

LINK exits to the bottom-left corner — reverse of entrance.

### Spatial Semantics

| Behavior | Meaning |
|----------|---------|
| Corner entrance | Tool summoned, not character appearing |
| Defined region | Occupies workspace, does not obscure center |
| Retreat to corner | Returns when finished — tool behavior |
| No center emergence | Avoids "AI character walking on stage" feeling |

---

## 11. Runtime Contract

### Interface

```javascript
window.LinkAvatar.setState({
    state: "listening",     // from §6 Valid States
    transition: "animated"  // "animated" | "instant" (default: "animated")
})
```

The runtime declares the state AND the transition mode. The renderer owns the
expression mechanics. The renderer does not know why the state happened, who
caused it, or whether it is correct.

### Rendering Pipeline

```
Platform event (governance layer)
        |
        v
State adapter (maps platform → LINK state)
        |
        v
LINK expression function (e.g. LINK-Thinking())
        |
        v
Renderer (SVG / WebGL / SwiftUI)
```

### What the Renderer Owns

- Expression mechanics (how a state looks)
- Animation timing and transition curves
- State-specific field parameters
- Choreography pacing (within minimum/maximum bounds)

### What the Renderer Does Not Own

- State selection
- State duration
- State sequencing
- Semantic meaning of states
- Whether a transition is animated or instant (runtime declares this)

---

## 12. Visual Authority Rule

LINK presentation is **downstream** of canonical state.

LINK may communicate states explicitly supplied by the governance layer.
LINK must not introduce states, qualify states, or imply evaluation of states.

This is the governing invariant for the entire visual system:

**Presentation does not create state.**

### Additional Constraints

| Constraint | Rationale |
|------------|-----------|
| The visual layer follows state; it does not manufacture state. | Prevents the renderer from simulating autonomous behavior. |
| The animation duration is determined by system readiness, not by a script. | Order Emerging should checkpoint on real events (context available, evidence ready). |
| The visual layer may never invent completion of an event that has not occurred. | Prevents false "ready" signals. |

---

## 13. Render Modes

| Mode | Function | Visual |
|------|----------|--------|
| Solid | Identity inspection, documentation, navigation, low distraction | Owl at opacity ~1.0, standard glow, field visible |
| Ephemeral | Active workflow, voice interaction, runtime feedback, state visualization | Owl at reduced opacity (~0.55), expanded glow (3.5×), field dominant |
| Fluid (brain) | Processing state, internal activity visualization | Small ellipse inside head (rx=76, ry=50, cy=168), 0.3 opacity, independent floating drift, turbulence animation |

These are three representations of the same identity — not three characters
and not three skins. Fluid mode renders a brain-like signal element inside
the Identity geometry.

---

## 14. Validation

A LINK implementation passes validation when:

1. All SVG paths match `LINK.svg` coordinates exactly (±0.01 px)
2. All hex colors match the canonical palette (§3)
3. Identity transformations preserve the invariant rules (§3)
4. Presence field does not alter identity recognition (§4)
5. Context modulation respects the precedence rules (§2, §5)
6. Allowed transformation bounds are respected (§7)
7. Runtime interface matches `LinkAvatar.setState()` signature (§11)
8. No state outside the valid vocabulary (§6) can be rendered
9. Forbidden transformations (§3, §7) are structurally impossible
10. State transitions respect the transition mode (animated vs instant) (§8)
11. Order Emerging has no hardcoded completion — event-driven advancement (§9)
12. The corner-entrance spatial model is preserved (§10)
