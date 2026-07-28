# LINK-VISUAL-CONTRACT-001

**Status:** Ratified
**Date:** 2026-07-28
**Source:** LINK-Exact-+-Ephemeral-+-Emotions.html (POC), LINK.svg (source geometry)
**Validation:** Verified against rendered output — invariant checks pass in current implementation.

---

## 1. Purpose

Define the visual contract for LINK as a governed projection of platform state.
This is a constraint artifact — future implementations (SwiftUI, WebView, Metal,
WebGPU) may vary technically but must preserve these invariants.

LINK consists of two channels:

| Channel | Function | Properties |
|---------|----------|------------|
| **Identity Channel** | Communicates *what* LINK is | Exact owl geometry — invariant |
| **Presence Channel** | Communicates *what* LINK is doing | Ephemeral field — expressive |

---

## 2. Identity Geometry Invariant

LINK identity is encoded through relational geometry, not individual feature shapes.
The perceived identity (owl) emerges from the relationships between primitives.

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
| Face, cheeks, chin | `#164450` | Primary fill |
| Horns, widow's peak | `#0b2228` | Contour / separator (same color — continuous brow silhouette) |
| Eye sclera | `#53676c` | Eye bed |
| Pupils | `#dbe2e3` | Gaze |
| Default glow | `#00E5FF` | Presence field (variable by state) |

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

## 3. Allowed Identity Transformations

Identity geometry may move as a **rigid facial system**. Internal relationships
must remain invariant.

### Permitted

| Transformation | Application | Example |
|---------------|-------------|---------|
| Uniform scale | Breathing animation | `scale(0.98–1.02)` from center |
| Uniform compression | Expression accent | `scaleY(0.4–1.2)` on eye groups — eyelids close toward eye center |
| Rigid group translation | Brow movement (alert, curious) | `translateY(-6px)` on upper contour — moves as a block, preserving face edge |
| Rigid system translation | Fly-in / fly-out | `translateY(0–300px)` on entire owl group |
| Coordinated pupil shift | Gaze direction | `translateY(8px)` for sleepy droop |
| Whole-owl rotation | Head tilt (curious) | `rotate(3deg)` on owl group |

### Forbidden

| Forbidden | Why |
|-----------|-----|
| Bend upper contour tip independently | Would break face-edge continuity — the shape would detach and revert to "horn" reading |
| Deform eye/widow's-peak independently | Would break eye-separation and beak illusion |
| Scale individual cheek independently | Would break bilateral symmetry |
| Move pupil without eye group | Would detach gaze from eye frame |

### Transform Parameter Bounds

| Parameter | Min | Max | Step | Notes |
|-----------|-----|-----|------|-------|
| Eye scaleY (expression) | 0.05 | 1.2 | continuous | Blink = 0.05, sleepy = 0.4, alert = 1.2 |
| Upper contour translateY | -8px | 4px | continuous | Negative = lift (alert), positive = lower |
| Pupil translateY | -4px | 10px | continuous | Down = sleepy droop |
| Owl group scale | 0.3 | 1.05 | continuous | Uniform from center — breathing + fly |
| Owl group translateY | 0px | 300px | continuous | Fly-in/out |
| Owl group rotate | -5° | 5° | continuous | Head tilt (curious) |

---

## 4. Presence Field

The presence field is intentionally **unconstrained** relative to identity
geometry. It is the expressive layer.

### Allowed Expression

| Dimension | Methods |
|-----------|---------|
| Activity | Particle motion, field ring rotation, turbulence |
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

## 5. State Vocabulary

LINK does not determine state. LINK receives qualified state and renders it.

### Valid States

| State | Description | Identity | Field |
|-------|-------------|----------|-------|
| Idle | Waiting, no active work | Neutral, breathing | Low-amplitude, stable cyan glow |
| Listening | Attending to input | Neutral, open | Expanded field, outward attention motion |
| Processing | Thinking / computing | Neutral, still | Internal constrained turbulence |
| Tool execution | Running a tool | Alert posture | Directional pulses, activity path |
| Speaking | Audio output | Neutral | Audio-reactive modulation |
| Complete | Task resolved | Happy squint | Settle animation, return to idle |
| Alert | Attention-required condition | Raised brows, tilted | High-intensity field |

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

## 6. Runtime Contract

### Interface

```javascript
window.LinkAvatar.setState({
    state: "listening"     // from §5 Valid States
})
```

The runtime declares the state. The renderer owns the expression mechanics.
The renderer does not know why the state happened, who caused it, or whether
it is correct.

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
- Animation timing
- Transition curves
- Field parameters per state

### What the Renderer Does Not Own

- State selection
- State duration
- State sequencing
- Semantic meaning of states

---

## 7. Visual Authority Rule

LINK presentation is **downstream** of canonical state.

LINK may communicate states explicitly supplied by the governance layer.
LINK must not introduce states, qualify states, or imply evaluation of states.

This is the governing invariant for the entire visual system:

**Presentation does not create state.**

---

## 8. Render Modes

| Mode | Function | Visual |
|------|----------|--------|
| Solid | Identity inspection, documentation, navigation, low distraction | Owl at opacity 1.0, standard glow |
| Ephemeral | Active workflow, voice interaction, runtime feedback, state visualization | Owl at reduced opacity, expanded glow envelope |

These are two representations of the same identity — not two characters
and not two skins.

---

## 9. Validation

A LINK implementation passes validation when:

1. All SVG paths match `LINK.svg` coordinates exactly (±0.01 px)
2. All hex colors match the canonical palette (§2)
3. Identity transformations preserve the invariant rules (§2)
4. Presence field does not alter identity recognition (§4)
5. Runtime interface matches `LinkAvatar.setState()` signature (§6)
6. No state outside the valid vocabulary (§5) can be rendered
7. Forbidden transformations (§3) are structurally impossible
