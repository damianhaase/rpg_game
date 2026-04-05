# Game Rulebook — Section 5: Damage, Wounds, and Conditions

## Preamble: Injuries as Probability Modifiers

The wound system is not a separate subsystem bolted onto combat — it is a feedback loop inside the probability engine. When a character is injured, the wound applies a penalty to their relevant target numbers, which directly shifts the 3d6 success curve. A Heavy Wound (–1 to physical actions) does not just say "you feel bad"; it means that actions which previously had a 74% success rate now have roughly 63%, and actions near the edge of feasibility may become unlikely or impossible.

Similarly, status conditions like Stunned, Suppressed, or Broken do not introduce new mechanics — they modify the existing values of RS, RB, EW, and action targets. The result is a death spiral that is gradual and visible rather than sudden and opaque: characters become weaker over the course of an encounter, players can see the probability shifts happening, and the tension escalates organically.

Pressure functions the same way: it accumulates as a separate track, crosses thresholds that impose modifiers, and eventually restricts the available action set. Because all of these effects feed into the same target-number calculation, the system remains coherent no matter how many conditions are active at once.

---

## Damage Resolution

### Step 1 — Roll Damage

When an attack hits, roll the weapon's damage dice, add the attacker's Damage Bonus (DB), then subtract the defender's Damage Reduction (DR):

```
Final Damage = max(0, Base Damage + DB − Armor DR)
```

Minimum damage of 1 if the attack connected (not a glancing force hit, which may deal 0).

### Step 2 — Apply to HP

Subtract Final Damage from the target's current HP. Track each significant wound separately rather than lumping all damage; this allows different wounds to produce different effects and enables targeted healing.

### Step 3 — Check Wound Category

Assess each wound based on damage relative to the victim's maximum HP. See the table below.

---

## Wound Categories and Effects

| Wound Category | Single-Hit Damage | State Effect |
|---|---|---|
| **Light Wound** | ≤ 10% of max HP | No immediate penalty. Contributes to Pressure gain. |
| **Heavy Wound** | 10%–25% of max HP | –1 to all physical actions; may lose 1 SPD until treated; Pressure gain increased. |
| **Severe Wound** | 25%–50% of max HP | –2 to actions; cannot Sprint; must test (CON or WIL) to take any major action; EW +1 on all physical actions. |
| **Critical Wound** | > 50% of max HP | –3 to actions; immediate Pressure test or become Shaken; cannot Commit or Counter; risk of incapacitation. |

**Wound Buffer (WB):** Reduce any numeric wound penalty by WB (from CON). State restrictions such as "cannot Sprint" or "cannot Counter" are not removed by WB — only the numeric penalty is reduced.

### Accumulated Wounds

Multiple Light Wounds can accumulate to a Heavy Wound at the GM's discretion (typically after 3 or more Light Wounds). Tracking separate injuries encourages narrative consequences: a wounded arm imposes an extra –1 or –2 when using that limb specifically.

### Stagger

A stagger occurs when a single hit meets or exceeds 25% of max HP. A staggered character suffers –2 to attack, –1 to defense, and may take only a limited action on their next turn. Stagger clears at the end of the following round unless a Severe or Critical Wound also applies.

---

## Critical Results

| Roll | Result |
|---|---|
| Natural 3 or 4 | Critical success: +50% damage or apply a special effect (disarm, knockdown, knockback). |
| Natural 17 | Near-miss failure: attacker fails but no self-harm. |
| Natural 18 | Critical failure: weapon jams, attacker falls Prone, or a nearby ally is inadvertently threatened. |

---

## Death and Incapacitation

When HP drops to 0 or below, the character must make a **Constitution check** (3d6 ≤ CON):
- **Success:** The character remains conscious but enters a Critical Wound state with all associated restrictions.
- **Failure:** The character is incapacitated and cannot act.

Additional failed checks at the GM's discretion may result in death. This ties mortality to character toughness without requiring separate death tables.

---

## Healing and Recovery

### Field Treatment (During Combat)

A character may use a **First Aid** action (Standard EW) to stabilize a wound. On a successful WIL + Medicine roll:
- One Light Wound is stabilized (bleeding stops).
- Serious or Critical Wounds cannot be healed in battle without magic.

### Rest Recovery

- **Light Wounds:** Heal after a short rest (~1 hour).
- **Heavy Wounds:** Require a long rest (~1 day) or medical care.
- **Severe / Critical Wounds:** Require extended rest or magical intervention.

Stamina (FP) recovers at 1 FP per minute of complete rest, or 1 FP per round of light activity.

### Magic Healing

Healing spells are governed by Section 7 (Magic). Minor healing closes Light Wounds; major healing closes one Heavy Wound. Critical healing spells require higher tiers and significant instability costs. All healing spells add Instability Cost to the caster's pool.

---

## Pressure System

Pressure is a separate morale and stress track. It accumulates when a character is aggressively attacked, flanked, suffers repeated damage, or faces overwhelming odds.

### Pressure Resistance (PR)

```
PR = WIL + ⌊ CON / 2 ⌋
```

Pressure is tracked as current PR remaining. As it depletes, the character crosses thresholds:

| Threshold | Condition | Effect |
|---|---|---|
| Above ¾ PR | **Calm** | No penalty. |
| Between ½ and ¾ PR | **Uneasy** | –1 to attack and defense checks. |
| Between ¼ and ½ PR | **Shaken** | –2 to checks; may not use Commit action. |
| Below ¼ PR | **Broken** | –4 to checks; may only Retreat, Defend, or Flee. |

### Pressure Gain

Pressure accumulates when:
- The character is hit (especially by a Heavy or Critical Wound)
- The character is flanked or surrounded
- The character witnesses devastating events nearby
- Near misses from suppressive ranged fire apply

Each failed Pressure roll reduces current PR by the margin of failure. Each successful morale check restores 1 PR. Resting outside combat restores PR at 1 per minute.

### Pressure Release

- Successful morale checks
- Rally actions from allied characters
- Elimination of the source of threat
- Magic or leadership abilities

---

## Status Effects

Conditions modify actions, RS, RB, and available reactions. Use these standardized terms consistently throughout all rules:

| Condition | Effect |
|---|---|
| **Stunned** | Cannot take complex actions. RB becomes 0. May only take the most basic defensive response if a rule explicitly allows it. |
| **Prone** | Easier to hit in melee (+2 to attackers), harder to hit at range (–1 to attackers). Reduced SPD and restricted movement. Recovery costs +2 EW. |
| **Grappled** | Limited movement; may not Dodge normally; may attempt to break free as a Slow action. |
| **Frightened** | Pressure penalties apply; aggressive reactions may become unavailable. |
| **Off-Balance** | –2 to physical action targets; may not Counter. |
| **Suppressed** | Cannot advance aggressively; must succeed on a Pressure check to leave cover or close distance. |
| **Broken** | Severe pressure collapse; may only Retreat, Defend, or Flee unless a special ability overrides this. |

---

## Design Notes

**State over subtraction:** Wound categories change the characters' options (reduced SPD, restricted reactions) rather than just lowering HP. This makes injury meaningful without requiring a hit-point death at every threshold.

**Discrete injuries:** Tracking each wound separately allows for targeted healing and narrative consequences. An arm wound does not affect footwork; a leg wound does not affect a shield block.

**Simple thresholds:** Using relative thresholds (percentages of max HP) scales naturally across species and character builds. Adjust the percentage ranges if playtesting shows the game is too lethal or too forgiving.

**Wound Buffer:** CON's role as a durability stat is expressed through Wound Buffer rather than HP inflation. This keeps HP totals modest and readable while still rewarding high-CON builds.
