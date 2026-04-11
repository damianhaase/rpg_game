# Game Rulebook — Section 7: Magic

## Magic as Interaction with Reality

Magic is an attempt to impose change on reality using a trained method called a **spell**. It uses the same core resolution system described in Section 1 and the same timing and exposure rules described in Section 3.

Magic is not a separate subsystem. It is a type of action. A practitioner still declares intent, creates exposure, invites reaction, and resolves the result with 3d6 and margins.

What makes magic distinct is not a separate resource pool or separate action loop. It is the combination of:

- spell proficiency
- declared intent
- parameter difficulty
- instability

Those all feed back into the same shared engine.

---

## Named Spells as Modes of Action

A spell name defines the **approach** used, not an exact predefined effect. A player does not select from a fixed list of discrete abilities. They choose a spell mode, declare intent, and let the shared resolution system determine the outcome.

The canonical spell set is:

| Spell | What It Manipulates |
|---|---|
| **Force** | Motion, pressure, impact, directional momentum |
| **Fire** | Heat, ignition, combustion, thermal denial |
| **Veil** | Concealment, masking, misdirection, uncertainty |
| **Rend** | Tearing, erosion, separation, opening weaknesses |
| **Bind** | Restraint, anchoring, holding, locking movement |
| **Shift** | Repositioning, displacement, altered angle or range |
| **Vital** | Restoration, stabilization, continuity of living function |
| **Fracture** | Breaking patterns, disrupting structure, interrupting coherence |

These spell names are broad methods of interaction with reality. Their exact outcome depends on the declared intent, scale, precision, speed, opposition, and final margin.

---

## Intent -> Resolution Flow

Magic follows the same shared pipeline as combat:

1. The player declares intent and the spell being used.
2. The system evaluates proficiency, scale, precision, speed, and resistance.
3. The attempt resolves via 3d6 into an outcome band.
4. The game applies the effect outcome, instability gain, and exposure change.

This is the same logic used for melee, ranged, and social actions. Magic does not bypass or replace it.

---

## Magic Attempt Target

All magic attempts use a target number built from the same ingredients as any other action:

```text
Magic Attempt Target =
IQ
+ Spell Proficiency Bonus
+ Focus Bonus
- Parameter Difficulty
- Pressure
- Current Instability
+ Situational Modifiers
```

- **IQ** is the base mental attribute for shaping reality.
- **Spell Proficiency Bonus** comes from the spell tier described in Section 8.
- **Focus Bonus** comes from items, ritual setup, or scene advantages.
- **Parameter Difficulty** is built from scale, precision, and chosen speed.
- **Pressure** uses the same stress penalties described in Section 5.
- **Current Instability** is the ongoing cost of previous attempts in the scene.

Opposed or resisted attempts still use the same margin comparison described in Section 1 and the same defensive framework described in Section 4.

---

## Magic Attempt Parameters

These parameters define how difficult and exposed a magic attempt is. They can be handled explicitly by the table or implicitly by the GM or digital implementation, but they should always map back to the same modifiers.

### Scale

| Scale | Typical Scope | Difficulty | Instability |
|---|---|---|---|
| **Small** | One person, one object, one narrow lane | +0 | +0 |
| **Moderate** | One zone, multiple bodies, one large object | –1 | +1 |
| **Large** | Wide area, multiple zones, major structure | –3 | +2 |

### Precision

| Precision | Typical Demand | Difficulty | Distortion Risk |
|---|---|---|---|
| **Broad** | Push, obscure, burn, alarm, shove | +0 | Low |
| **Directed** | Specific target, limb, gap, route | –1 | Moderate |
| **Exact** | Fine shaping, selective effect, delicate restoration | –3 | High |

### Speed

| Speed | Exposure Window | Difficulty | Notes |
|---|---|---|---|
| **Deliberate** | Slow (EW 6) | +0 | Safest default |
| **Standard** | Standard (EW 4) | –1 | Normal combat pacing |
| **Rushed** | Fast (EW 2) | –3 | Highest interruption risk if it fails |

### Resistance

Resistance is not a separate magic-only rule. It is whatever the target would normally use in context:

- Dodge, Parry, or Block against localized force when legal
- Cover against obscuring, scattered, or indirect effects
- PR, WIL, IQ, or CON when the effect targets morale, mind, perception, or bodily integrity
- Object difficulty or material toughness when targeting terrain, gear, or structures

If the target opposes the attempt, resolve it with the same opposed-margin procedure used everywhere else.

---

## Instability

Every magic attempt generates **instability**. Instability is the core limiter on magic use. It increases the chance of distorted results and makes the practitioner more vulnerable by increasing exposure or degrading outcome quality.

### Gaining Instability

Each attempt adds instability as follows:

- Base instability: **1**
- Add **+1** for Moderate Scale or Directed Precision
- Add **+2** for Large Scale or Exact Precision
- Add **+1** if the attempt is Rushed
- Add **+1** additional instability on any failed attempt

### Instability Bands

| Band | Current Instability | Effect |
|---|---|---|
| **Low** | 0–2 | No extra penalty beyond the normal current-instability subtraction. |
| **Medium** | 3–5 | Magic attempts suffer +1 EW. Successes by margin 0–1 become **success with distortion**. |
| **High** | 6+ | Magic attempts suffer +2 EW. Successes by margin 0–2 become **success with distortion** and failures by 1–2 become **unintended effect** instead of partial effect. |

### Threshold Consequences

- If current instability exceeds **IQ**, the practitioner must make an immediate PR check or become **Shaken**.
- If current instability exceeds **IQ + 3**, the next failed magic attempt automatically counts as **failure + consequence**.

Instability usually falls to zero after the scene ends and the practitioner has a few minutes of calm. Some gear, preparation, or edges can reduce it earlier.

---

## Failure Modes

Magic does not use a binary success/failure model. Resolve the attempt by its final margin after all modifiers:

| Margin Result | Outcome |
|---|---|
| **Success by 3+** | **Clean success** |
| **Success by 0–2** | **Success with distortion** |
| **Fail by 1–2** | **Partial effect** |
| **Fail by 3–4** | **Unintended effect** |
| **Fail by 5+ or natural 18** | **Failure + consequence** |

Typical interpretations:

- **Clean success:** The declared effect lands as intended.
- **Success with distortion:** The effect lands, but with spill, drift, collateral pressure, or extra exposure.
- **Partial effect:** The intent is only partly achieved.
- **Unintended effect:** The effect happens, but in the wrong shape, wrong place, or wrong scale.
- **Failure + consequence:** The attempt fails and creates a meaningful backlash, usually extra instability, pressure, lost position, or a scene complication.

At Medium or High Instability, downgrade outcomes as described above before applying the final fiction.

---

## Magic and Combat Integration

Magic uses the same resolution system described in Section 1 and the same timing rules described in Section 3. It therefore interacts with combat exactly the same way as any other action:

- **Force** and **Fracture** can interrupt actions, spoil commitment, or break prepared positions.
- **Bind** and **Rend** can create exposure by pinning, tearing, worsening wounds, or forcing Off-Balance states.
- **Veil** can reduce targeting reliability by creating concealment, false reads, or cover-like uncertainty.
- **Shift** can alter range bands, angle, line of sight, and access to cover.
- **Vital** can stabilize or downgrade wounds, but it still creates exposure and can be interrupted.
- **Fire** can apply direct damage, pressure, denial of space, or forced movement through heat and fear.

There is no special-case combat handling for magic. If a mundane action can be interrupted, countered, or exposed, so can a magic attempt.

---

## Defense Against Magic

The declared intent and spell profile determine the appropriate defense:

| Defense Type | When Used |
|---|---|
| **Dodge** | Direct impact, projected force, sudden displacement |
| **Block / Parry** | Only when the fiction supports intercepting the effect |
| **Cover** | Veil, Fire spread, scattered pressure, indirect shaping |
| **PR** | Fear, stress, pain, morale-breaking, oppressive presence |
| **WIL** | Control, compulsion, emotional override |
| **IQ / Perception** | Misdirection, false perception, Veil effects |
| **CON** | Corruptive, draining, or bodily destabilizing effects |

Use the normal opposed or resistance logic from Sections 1 and 4. Magic does not define a separate saving-throw layer.

---

## Spell Profiles

### Force

- **Identity:** Manipulates motion, pressure, impact, and directional momentum.
- **Strengths:** Interrupting actions, redirecting movement, knocking bodies or objects out of line.
- **Weaknesses:** Sustained control, delicate shaping, subtle concealment.
- **Failure Modes:** Overshoot, rebound, collateral shove, self-exposure through overextension.
- **Mechanical Hooks:** Strong interaction with interruption, forced movement, and commitment contests.

### Fire

- **Identity:** Manipulates heat, ignition, combustion, and thermal denial.
- **Strengths:** Direct damage, pressure generation, area denial, forcing enemies out of cover.
- **Weaknesses:** Fine manipulation, nonlethal control, careful allied positioning.
- **Failure Modes:** Blowback, unintended spread, smoke, collateral ignition.
- **Mechanical Hooks:** Strong interaction with wounds, pressure, cover denial, and environmental hazards.

### Veil

- **Identity:** Manipulates concealment, masking, doubt, and perceptual uncertainty.
- **Strengths:** Lowering targeting reliability, creating cover-like states, disguising movement or presence.
- **Weaknesses:** Direct force, hard restraint, durable terrain change.
- **Failure Modes:** Friendly confusion, self-obscuring, weak concealment that collapses under scrutiny.
- **Mechanical Hooks:** Strong interaction with cover, Perception, ranged defense, and line-of-sight control.

### Rend

- **Identity:** Manipulates separation, tearing, erosion, and exposed weakness.
- **Strengths:** Worsening wounds, breaking protective layers, opening armor gaps, damaging structures.
- **Weaknesses:** Delicate restoration, stable restraint, subtle scene shaping.
- **Failure Modes:** Overcut, collateral damage, unstable tearing that creates extra exposure.
- **Mechanical Hooks:** Strong interaction with wound categories, Armor DR pressure, and exposed states.

### Bind

- **Identity:** Manipulates restraint, anchoring, holding, and locked motion.
- **Strengths:** Creating exposure, restricting movement, pinning limbs, blocking disengage.
- **Weaknesses:** Burst damage, wide areas, fluid redirection.
- **Failure Modes:** Slack hold, self-entanglement, partial restraint that only delays the target.
- **Mechanical Hooks:** Strong interaction with Grappled-like states, movement denial, and forced EW increases.

### Shift

- **Identity:** Manipulates placement, angle, displacement, and tactical relation.
- **Strengths:** Repositioning, escaping pressure, altering lanes, changing cover or range.
- **Weaknesses:** Direct lethality, holding a fixed line, heavy structural breakage.
- **Failure Modes:** Bad landing, short displacement, accidental exposure, unstable angle change.
- **Mechanical Hooks:** Strong interaction with movement, flanking, disengage, cover access, and line-of-sight changes.

### Vital

- **Identity:** Manipulates restoration, stabilization, continuity, and living function.
- **Strengths:** Downgrading wounds, stabilizing dying allies, restoring function, reducing pressure from bodily shock.
- **Weaknesses:** Raw offense, wide-area change, brute interruption.
- **Failure Modes:** Numbness, overcorrection, fatigue spikes, incomplete closure.
- **Mechanical Hooks:** Strong interaction with wound downgrades, stabilization, and condition relief.

### Fracture

- **Identity:** Manipulates breakage, disruption, pattern collapse, and structural failure.
- **Strengths:** Interrupting attempts, breaking wards or gear, collapsing stance, damaging cover.
- **Weaknesses:** Healing, sustained control, fine selective shaping.
- **Failure Modes:** Rebound crack, self-disruption, collateral breakage, unstable feedback.
- **Mechanical Hooks:** Strong interaction with Counter windows, concentration loss, terrain damage, and broken equipment states.

---

## Design Principles

1. **Same engine, different approach.** Magic uses the same core loop as every other action.
2. **No hard menus.** Spell names define methods, not a catalog of fixed effects.
3. **Reliability over permission.** Any spell can be attempted; proficiency changes outcome quality, instability, and exposure.
4. **Instability is the limiter.** Magic remains flexible because instability and exposure keep it risky.
5. **Combat coherence matters.** If a ruling for magic would require a separate combat subsystem, it is probably the wrong ruling.
