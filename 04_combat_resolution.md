# Game Rulebook — Section 4: Combat Resolution

## Preamble: One Engine for All Attack Types

Melee, ranged, and magical attacks are not separate subsystems. They are different *payloads* moving through the same timing-and-resolution engine. What changes between them is not the dice mechanic or the success formula — it is the modifiers that enter the target number, the reactions that are legally available, and the cover and positioning considerations that apply.

Every combat action follows the same six-step pipeline:

1. Build the action target number.
2. Determine the Exposure Window.
3. Check legal reactions using Response Speed and Reaction Budget.
4. Roll action and defense (3d6 vs. target).
5. Compare margins.
6. Apply damage, pressure, wounds, and state changes.

This means that a player who understands how to resolve a sword attack already understands how to resolve an arrow or a fireball. The numbers differ; the structure does not.

---

## Unified Resolution Model

Combat resolves in this order:

1. Determine whether the acting character's action creates an exploitable Exposure Window.
2. Determine whether any opponent can legally react using RS and RB.
3. Apply the chosen defense or interruption.
4. Roll the actual action and defense checks (3d6 ≤ target = success).
5. Compare margins and apply damage, pressure, and state changes.

### Opposed Resolution Formula

```
P(hit) = P_attacker × (1 − P_defender)
```

Where `P_attacker` and `P_defender` are derived from the 3d6 cumulative distribution function for each character's effective target number. Clamp all target values to the range 3–17 before looking up probabilities.

```python
def compute_hit_chance(attacker_target, defender_target):
    T_a = clamp(3, 17, attacker_target)
    T_d = clamp(3, 17, defender_target)
    P_a = CDF_3d6[T_a]
    P_d = CDF_3d6[T_d]
    return P_a * (1 - P_d)
```

---

## Attack Targets by Weapon Class

### Finesse Melee

```
Attack Target = DX + Weapon Skill + weapon accuracy modifiers + state modifiers
```

Light, precise weapons (rapiers, daggers) rely on DX. These characters hit more often but deal less force.

### Heavy Melee

```
Attack Target = ST + Weapon Skill + weapon accuracy modifiers + state modifiers
```

A heavy weapon may impose a penalty when used by a character with low DX, but ST is the primary attribute. This creates a distinct tank/berserker path separate from the agile fighter path.

### Ranged

```
Attack Target = DX + Missile Skill + Weapon Accuracy + Range Modifier + Aim Bonus + State Modifiers
```

Ranged attacks use Dexterity and missile skills. They apply range band modifiers and may gain aim bonuses. Cover bonuses apply to the defender, and dodge against ranged is weaker than dodge against melee.

### Magic

```
Casting Target = IQ + Spell Skill + Focus Bonus + State Modifiers − Instability Penalties
```

See Section 7 (Magic) for the full spell resolution model.

---

## Situational Attack Modifiers

| Situation | Modifier |
|---|---|
| Target is Evading (Guarded) | –1 to attacker |
| Target is Committed (Engaged, open) | +1 to +2 |
| Target is Prone (melee) | +2 |
| Target is Prone (ranged) | –1 |
| Attacker is Committed | +1 to hit, –1 to defensive targets |
| Attacker is Prone | –4 (unless thrust attack) |
| Target is Shaken or Pressured | +1 or more |
| Attacker is Wounded (after WB) | See wound table |
| Partial cover | –1 to –2 |
| Heavy cover | –3 to –4 |
| Full cover | Cannot target directly |
| Darkness / Concealment | –1 to –4 |

---

## Defense Targets by Context

Against **melee**, the defender may choose Dodge, Parry, or Block if legally available (see Section 3 for legality rules and RB costs).

Against **ranged**, Dodge is weaker (–2 default) and cover is usually more important than parry or block. Parry is generally not legal against ordinary projectiles unless a special ability, weapon property, or explicit rule allows it. Block may apply against large slow missiles, thrown weapons, or very favorable shield angles.

Against **magic**, the spell description determines whether the defense is Dodge, cover, PR, WIL, IQ, or another listed resistance.

---

## Margin Comparison

Both attacker and defender roll 3d6. Outcomes:

| Scenario | Result |
|---|---|
| Attacker succeeds, defender fails | Full hit |
| Both succeed | Compare margins; higher margin wins |
| Attacker succeeds, defender succeeds by equal margin | Partial hit or graze at GM/implementation discretion |
| Attacker fails | Miss |
| Defender succeeds by large margin and has paid Counter RB | Defender may answer with a Counter |

---

## Heavy Weapons and Glancing Force

Heavy weapons gain a reliability mechanic. If a heavy melee attack misses by only 1 or 2, it may still deal **glancing force damage** equal to the attacker's DB, reduced by DR as normal, if the defender did not Dodge cleanly out of reach and the fiction supports partial contact.

This makes ST-based fighters feel forceful without giving them the same precision profile as DX fighters.

---

## Ranged Combat

Missile and thrown weapons use the same 3d6 engine as melee, but they interact with the timing system differently. Ranged combat emphasizes preparation, exposure, lines of sight, and cover.

### Range Bands and Modifiers

| Range Band | Modifier |
|---|---|
| Point-blank | +2 |
| Near | +1 |
| Medium | 0 |
| Far | –2 |
| Extreme | –4 or impossible |

Weapons define the farthest band they can attack effectively.

### Ranged Attack Formula

```
Ranged Attack Target = DX + Missile Skill + Weapon Accuracy + Range Modifier + Aim Bonus + Situation Modifiers
```

Situation modifiers include:
- target in cover
- attacker moved this round
- target moved unpredictably
- attacker is Prone
- visibility issues
- wound penalties after Wound Buffer
- pressure penalties

### Exposure Windows for Ranged Attacks

Ranged combat is governed by the same exposure-window model as melee.

| Action | EW |
|---|---|
| Quick thrown weapon | Fast (EW 2) |
| Snap shot | Standard (EW 4) |
| Normal bow or firearm shot | Standard (EW 4) |
| Aimed shot | Slow (EW 6) |
| Brace, reload, or powerful aimed attack | Extended (EW 8) |

This means ranged attacks are often reactable **before release**, not after the projectile is in flight. A character with sufficient RS can act during the archer's draw and aim phase.

### Defense Versus Ranged Attacks

Ranged defense shifts emphasis from active weapon defense to movement and environment.

- **Dodge:** Remains legal, but suffers a default –2 penalty against ranged attacks unless a trait overrides it.
- **Parry:** Generally not legal against ordinary projectiles unless a special ability, weapon property, or cinematic rule explicitly allows it.
- **Block:** May apply against large slow missiles, thrown weapons, or very favorable shield angles. Not universally available against all missile attacks.
- **Cover:** The primary ranged defense. Cover adds directly to the defender's effective target.

Suggested cover bonuses to defender target:

| Cover Type | Bonus |
|---|---|
| Light Cover | +1 |
| Medium Cover | +2 |
| Heavy Cover | +3 |
| Full Cover | Cannot be targeted directly |

### Aim Mechanic

A character may Aim instead of firing.
- Each Aim action grants +1 Aim Bonus (stacks up to a default maximum of +2).
- Aim is lost if the attacker must Dodge, is struck, becomes Suppressed, or changes target significantly.
- Aiming increases EW, because the attacker is deliberately extending their preparation window.

Track aim state per attacker:

```python
AimState = {
    "stacks": 0,
    "target_id": None
}
```

### Suppression

Ranged attacks may apply pressure even on a miss if the shot was dangerous and close enough to matter.

On a near miss, the target may:
- gain Pressure
- lose an Aim stack
- become Suppressed (cannot advance aggressively)
- be forced to remain in cover

Suppression is especially useful for making ranged combat tactically meaningful without requiring constant damage output.

### Reload and Readiness

Some weapons must be reloaded after each shot:

```python
WeaponState = {
    "loaded": True,
    "ammo": None  # or integer if tracking ammunition
}
```

- Weapons flagged `reload: True` require a full action (Extended EW) to reload.
- Optional quick reload: reload as a minor action with –1 on the next attack.
- Attempting to fire an unloaded weapon fails automatically.

### Design Principles for Ranged Combat

1. Ranged combat uses the same success engine as melee.
2. The main difference is not special dice logic; it is exposure timing, cover, and the legality of defensive reactions.
3. The player should feel that ranged threats are beaten by anticipation, movement, and terrain — not by abstract "who acts first."
4. Cover is more important than Dodge in prolonged missile exchanges.

---

## Integrated Combat Loop Example

A swordsman declares a heavy Commit attack with a great axe.

1. That attack has a Slow or Extended EW (heavy weapon, Committed stance).
2. An archer with line of sight and enough RS may loose a prepared shot into that exposure window.
3. The swordsman may still react if RB and RS permit, but heavy armor, wounds, or low IQ may leave them unable to do so.
4. Both actions resolve through the normal target-number and margin system.
5. Damage, pressure, and wound-state updates feed back into SPD, RS, RB, and available options for subsequent rounds.

---

## UI Output Example

When presenting attack options, display intermediate calculations:

**Fire at Goblin (Medium Range)**
- Ranged Attack Target: 14 → P_A ≈ 91%
- Goblin's Dodge Target: 10 (with –2 ranged penalty) → P_D ≈ 50%
- Cover bonus (Medium): +2 → Adjusted P_D ≈ 74%
- **Final hit chance: 91% × (1 – 74%) ≈ 24%**

This style reinforces probability transparency and shows how cover and dodge interact.

---

## Design and Balance Rationale

**3d6 Distribution:** Small bonuses (±1 or ±2) meaningfully change success probability. An effective target of 10 yields ~50%, 12 yields ~75%, 14 yields ~90%. Incremental advantages from positioning, teamwork, and equipment have real impact.

**Skill vs. Attribute:** Skill matters at least as much as raw Dexterity. A DX 10 character with Sword 14 can outfight a DX 14 character with Sword 10. Situational modifiers are capped to prevent runaway stacking (rarely more than ±4 total).

**Reactions as Choice:** Players must choose whether to react. Reactions impose costs — usually to the next action or to momentum. This presents a risk-reward decision: accept a slightly higher chance to be hit now, or spend RB and potentially miss an opening?

**Weapon Differentiation:** Modest accuracy bonuses and parry values differentiate playstyles without exhaustive tables. Daggers and small blades are quick but do modest damage; axes hit hard but are slower. These bonuses mirror GURPS and TFT while remaining simple.
