# Game Rulebook — Section 7: Magic

## Preamble: Magic as a High-EW, High-Risk Action

Magic runs through the same probability engine as every other action in the system. A spell is an action. It creates an Exposure Window. It has an attack target (Casting Target) that feeds into the 3d6 roll. It produces margins of success or failure that determine effect severity. If the caster fails, there are consequences — not a blank miss, but escalating instability that makes subsequent spells riskier and which interacts with the Pressure system.

The central insight of this magic design is that the cost of powerful magic is *time* and *instability*, not just spell points. A complex spell has a large EW, which means enemies with sufficient RS can potentially react before it resolves. Instability builds with every cast and reduces the effective Casting Target of future spells, compressing the probability space toward failure. This creates organic pacing: a mage who opens with a powerful spell creates enormous exposure and exhausts their margin of error for the rest of the encounter.

Magic also has a larger narrative footprint than most physical actions. The Drift Event mechanic — triggered by critical failure — introduces unpredictable consequences that can shift the entire scene. This asymmetry between high potential effect and high potential risk is intentional; it is what makes magic feel genuinely dangerous rather than just "a different kind of damage."

---

## World Assumption

The world assumes that reality is malleable but resists manipulation. Magic is powerful, but it incurs **instability** — a metaphysical strain that grows with each spell cast. Spells are defined by clear costs and limitations. Interesting magic stems from weaknesses and trade-offs; high-tier spells should be rare and risky.

---

## Spell Components

Each spell has the following descriptive elements:

- **Intent:** The broad purpose of the magic — *damage*, *bind*, *reveal*, *alter*, *protect*, *communicate*, etc. This informs narrative effects and helps adjudicate unusual interactions.
- **Tier:** A rough measure of power (1–5). Higher tiers require more skill and introduce greater instability.
- **Instability Cost (IC):** A number (1–10) representing how much casting the spell strains reality. Low-tier utility spells cost 1–2; a Tier 5 portal may cost 8 or more.
- **Exposure Window:** Casting is generally Standard (EW 4) for Tier 1–2 spells and Slow to Extended (EW 6–8) for Tier 3–5 spells. Instability surges may increase EW further.

---

## Casting Roll

Roll 3d6 and compare it to the **Casting Target**:

```
Casting Target = IQ + Spell Skill + Focus Item Bonus − Pressure − Current Instability
```

- **IQ + Spell Skill** reflects mental fortitude and training in a magical discipline (Elementalism, Necromancy, Warding, Divination, etc.).
- **Focus Item** (wand, staff, sacred text, rune-carved weapon) grants +1 to +3.
- **Pressure** is the combat stress tracked in Section 5; high pressure makes spellcasting harder.
- **Current Instability** is the cumulative instability accrued from previous spells this scene. Each spell cast — success or failure — adds to the instability pool.

### Outcomes

| Result | Effect |
|---|---|
| **Success** (roll ≤ target) | Spell takes effect. Add Instability Cost to pool. |
| **Failure** (roll > target) | Spell fizzles or partially succeeds. Add *twice* the Instability Cost to pool. GM introduces a minor side effect (sparks, echoes, partial misdirection). |
| **Critical Failure** (natural 18, or failure by 5+) | **Drift Event.** Instability pool resets to zero as backlash discharges, but reality briefly warps (see Drift Events below). |

---

## Drift Events

A Drift Event occurs on critical casting failure. Effects are narrative and should be tailored to the scene:

- Time distorts in the local area (one combatant acts twice; another is skipped)
- A random spell from the caster's pool triggers uncontrolled
- A minor entity or effect from another plane slips through momentarily
- All characters in Near range gain 1d6 Pressure from the burst of chaotic energy
- An already-cast spell persists beyond its intended duration
- The caster's magical focus item is permanently attuned to the moment and gains an unintended minor property

The instability pool resets to zero after a Drift Event — the backlash has discharged — but narrative consequences may persist for the scene or beyond.

---

## Managing Instability

Instability accumulates across a scene and decays between scenes.

- **In combat:** Instability does not naturally decay. Each spell cast raises the pool.
- **After combat:** A few minutes of calm reduces the instability pool to zero.
- **Focus Items and Rituals:** Certain items or brief rituals (one minute) may reduce instability by 1–3 mid-scene.
- **High instability and Pressure:** High instability raises the difficulty of resisting Pressure effects. A reckless caster risks becoming Shaken or Broken from the feedback loop of failing spells while already stressed.

Track instability as a simple running total:

```python
CasterState = {
    "instability": 0,
    "max_safe_instability": IQ,  # designer-adjustable threshold
    "focus_item_bonus": 0
}
```

---

## Magic and the Exposure Window

Casting uses EW in the same way as physical actions. This means:

- A character with sufficient RS may act *during* the caster's preparation phase — before the spell resolves.
- Counter reactions (costing 2 RB) may interrupt a caster in Extended EW, preventing the spell from firing.
- An IQ-heavy mage with high RS can react faster than a slow physical fighter, but still takes time to cast powerful spells.

Instability surges from prior failures may increase the current spell's EW by +1 or more, making the caster progressively easier to interrupt.

---

## Defense Against Magic

The spell description determines which defense type applies:

| Defense Type | When Used |
|---|---|
| Dodge | Localized physical effect (fireball, lightning bolt) |
| Cover | Area denial spells or scattered effects |
| PR check (3d6 ≤ PR) | Fear, intimidation, morale collapse spells |
| WIL check (3d6 ≤ WIL) | Mental domination, charm, suggestion |
| IQ check (3d6 ≤ IQ) | Illusions, deception, false perception spells |
| Listed resistance (CON, etc.) | Poison-type spells, debilitation, transformation |

---

## Spell Tier Reference

| Tier | Example Spells | Typical IC | Typical EW | Casting Target Range |
|---|---|---|---|---|
| 1 | Spark, Minor Bind, Detect, Ward Sign | 1–2 | Standard (4) | Accessible to IQ 10+ |
| 2 | Flame Bolt, Slow, Silence, Minor Heal | 2–3 | Standard–Slow (4–6) | Requires Spell Skill 2+ |
| 3 | Fireball, Binding Chain, Illusion, Heal | 4–5 | Slow (6) | Requires Spell Skill 4+ |
| 4 | Teleport, Major Illusion, Storm Call | 6–7 | Extended (8) | Requires Spell Skill 6+ |
| 5 | Portal, Reality Bend, Mass Domination | 8–10 | Extended (8+) | Requires Spell Skill 8+ |

---

## Magic Design Principles

1. **Limits and costs over raw power.** Spells with low instability can be cast freely; high-tier spells should be rare and risky.
2. **Subsystem synergy.** Use existing mechanics (Pressure, EW, RB, RS, wound states) rather than adding new dice systems. This keeps the game lean and transparent.
3. **Transparency with risk.** Show players the Casting Target, current instability, and Instability Cost before they commit. They should understand the odds and potential consequences.
4. **Narrative consequences.** Magic can alter the story in unpredictable ways. Drift Events are intentionally open-ended.
5. **IQ as the magic attribute.** IQ governs both spellcasting accuracy and Reaction Budget, which means a high-IQ mage is both a better caster and more tactically aware. This is intentional — magic is cognitively expensive.

---

## Healing Magic

Healing spells function like other spells: they have an Instability Cost, target IQ + Healing Skill, and create an EW during which the caster is vulnerable.

| Healing Tier | Effect | IC |
|---|---|---|
| Minor Heal (Tier 1) | Closes 1 Light Wound; restores ~5 HP | 1 |
| Moderate Heal (Tier 2) | Closes 1 Heavy Wound; restores ~10 HP | 3 |
| Major Heal (Tier 3) | Closes 1 Severe Wound; restores ~15 HP; removes 1 status effect | 5 |
| Critical Heal (Tier 4) | Closes 1 Critical Wound; stabilizes incapacitated character | 7 |

Healing in combat still requires EW exposure. A character who casts a major heal in the middle of a fight is committing to an Extended EW and may need RB support from allies to avoid interruption.
