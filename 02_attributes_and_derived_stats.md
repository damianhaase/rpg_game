# Game Rulebook — Section 2: Attributes and Derived Statistics

## Preamble: How Attributes Feed the Probability Engine

Every number on a character sheet eventually becomes part of a target number that is compared to a 3d6 roll. Attributes are the raw inputs; derived statistics are the intermediate results; target numbers and modifiers are the outputs that enter the probability curve.

The attribute design deliberately distributes combat roles so that no single stat dominates every phase. A character with high Dexterity is agile and precise, but a character with high Strength hits harder and tanks more, and a character with high Intelligence reacts faster and casts more reliably. Each attribute owns a distinct region of the probability calculation. This means that raising any one attribute meaningfully shifts probabilities in one area without making every other area trivial.

Derived statistics translate raw attributes into bounded, gameplay-facing values. Small increments (+1, +2) at the attribute level produce meaningful but not runaway changes in success probability, which is the intended behaviour of the 3d6 bell curve.

---

## Attributes

These attributes are defined so that no single stat dominates all phases of combat. Each attribute owns a distinct tactical role.

- **Strength (ST):** Force, leverage, and committed physical power. ST governs heavy weapon use, shield blocking, damage bonus, carrying capacity, and other force-based actions.
- **Dexterity (DX):** Precision, footwork, and bodily execution speed. DX governs finesse attacks, dodging, fine motor actions, and movement-based reactions.
- **Constitution/Endurance (CON):** Toughness, stamina, pain tolerance, and physical resilience. CON governs hit points, fatigue, natural damage resistance, and reduction of wound penalties.
- **Intelligence (IQ):** Awareness, processing speed, magical control, and tactical bandwidth. IQ governs spellcasting, response speed, reaction budget, and perception-driven combat awareness.
- **Will/Morale (WIL):** Resistance to fear, intimidation, panic, and mental pressure.

---

## Secondary Stats and Derived Values

The system uses derived values to turn the core attributes into consistent gameplay outcomes. These formulas are defaults for balancing and implementation.

- **Health Points (HP):** Based on Constitution.
- **Fatigue Points (FP):** Based on Constitution.
- **Magic Points (MP):** Based on Intelligence.
- **Pressure Resistance (PR):** Based on Will and Constitution.
- **Speed (SPD):** Based on Dexterity and Constitution.
- **Load:** Based on Strength.
- **Damage Bonus (DB):** Based on Strength.
- **Response Speed (RS):** Based on Dexterity and Intelligence.
- **Reaction Budget (RB):** Based on Intelligence.
- **Wound Buffer (WB):** Based on Constitution.

---

## Derived Statistics: Calculations and Examples

Combat does not use a visible turn order or initiative roll. Instead, actions expose a character for some amount of time, and other characters may react if their Response Speed is high enough to act within that window. The statistics below define the physical and cognitive capacity that determines who can react, how much, and how effectively.

### Speed (SPD)

Speed governs movement per combat round and contributes to positioning actions.

```
SPD = ⌊ (DX + CON) / 4 ⌋
```

A typical human with DX 10 and CON 10 has SPD 5. Encumbrance and armor may reduce SPD. A character with SPD 0 can no longer move under their own power.

---

### Carrying Capacity (Load)

```
Comfortable Load (kg) = ST × 5
Maximum Load (kg)     = ST × 15
```

Carrying up to Comfortable Load imposes no penalty. For every 25% of Comfortable Load beyond that, reduce SPD by 1. At loads above Comfortable Load, some reactions become unavailable at the GM's discretion or by implementation rule. A character cannot move or act if they exceed Maximum Load.

---

### Damage Bonus (DB)

```
DB = ⌊ (ST − 10) / 2 ⌋
```

ST 10–11 gives DB 0. ST 14 gives DB +2. ST 8 gives DB –1, to a minimum of –2. Unarmed attacks use 1d6 + DB. Most melee weapons add their own damage dice and modifiers on top of DB.

---

### Hit Points (HP)

```
HP = CON × 2
```

This is the default health model. Some variants may average ST and CON, but the CON-based model is the standard baseline. Traits, species templates, or magic can modify HP up or down. When HP drops to zero, the character is *downed*; further damage may cause death.

---

### Fatigue Points (FP)

```
FP = CON × 2
```

Fatigue measures physical and mental exertion. Sprinting, all-out defense, wrestling, and spellcasting may cost FP. Fatigue recovers at 1 FP per minute of complete rest.

---

### Magic Points (MP)

```
MP = IQ × 2
```

Magic remains primarily an Intelligence-based system. Will, talents, or traits may modify MP.

---

### Pressure Resistance (PR)

```
PR = WIL + ⌊ CON / 2 ⌋
```

Pressure tracks fear, stress, pain, and morale collapse. Pressure thresholds are defined in Section 5 (Damage, Wounds, and Conditions). When forced to resist a pressure effect, roll 3d6 ≤ PR to resist.

---

### Response Speed (RS)

Response Speed determines whether a character is fast and aware enough to act during another character's exposure window.

```
RS = DX + ⌊ IQ / 2 ⌋ + situational modifiers
```

Situational modifiers may include:
- armor penalty
- encumbrance penalty
- wound penalty
- being surprised
- aiming or observing beforehand
- cover or concealment effects

**Response Speed is not a separate action roll.** It is a deterministic combat value used to decide whether a reaction window can be exploited. See Section 3 for how RS interacts with Exposure Windows.

---

### Reaction Budget (RB)

Reaction Budget measures how much tactical bandwidth a character has in one combat round.

```
RB = 1 + ⌊ IQ / 4 ⌋
```

Minimum RB is 1 unless a condition reduces it to 0. A typical IQ 10 character has RB 3. Stunned, overloaded, or severely wounded characters may have RB reduced.

Reaction costs:
- Dodge: 1 RB
- Parry: 1 RB
- Block: 1 RB
- Shift / Step / minor reposition: 1 RB
- Counter: 2 RB
- Complex magical interrupt: usually 2 RB or more

A character may not spend more RB in a round than they possess.

---

### Natural Damage Resistance (Natural DR)

Constitution provides a small built-in toughness that stacks with armor.

```
Natural DR = ⌊ (CON − 10) / 2 ⌋   (minimum 0)
```

For every two full points of CON above 10, gain +1 Natural DR. For every two points of CON below 10, Natural DR decreases by 1, to a minimum of 0. Humans and similar creatures have little natural resilience: a CON 12 character has Natural DR 1; a CON 14 character has Natural DR 2; a CON 8 character has Natural DR 0.

Natural DR stacks with armor DR. When damage is inflicted, subtract total DR (natural + armor) from the incoming damage roll, to a minimum of 1. Magic or piercing attacks may ignore some or all DR, as specified by the attack.

---

### Movement (Basic Move)

Movement speed during a combat round depends on Speed:

```
Move (metres per round) = SPD × 2
Move (hexes per round)  = SPD ÷ 1.5  (round up)
```

A character with SPD 5 can move 10 metres or 4 hexes in one round if they spend their action on movement. Armor, encumbrance, rough terrain, Prone recovery, or being Shaken can reduce movement.

**Sprint:** A character may Sprint as their primary action instead of attacking. Sprinting adds +50% to their Move distance for that round but costs **1 FP**. A character cannot Sprint while Prone, Grappled, carrying Heavy Load, or wearing armor that restricts Sprint (see Section 6). Characters reduced to SPD 0 cannot Sprint.

---

### Wound Buffer (WB)

Constitution reduces the severity of the death spiral without removing it.

```
WB = ⌊ CON / 4 ⌋
```

When wound penalties are applied, reduce the total penalty by WB, to a minimum penalty of 0. This does not remove state restrictions such as "cannot Sprint" or "cannot Counter"; it only reduces numeric penalties.

Examples:
- CON 8 gives WB 2.
- CON 12 gives WB 3.
- CON 16 gives WB 4.

This makes CON valuable without turning injury into a binary "fine until dead" state.

---

## Defense Targets

Defense is no longer treated as a single generic formula. Instead, the defender chooses a legal reaction, and that reaction defines the defense target.

### Dodge Target

```
Dodge Target = 9 + DX + Dodge Skill + state modifiers − armor penalty
```

### Parry Target

```
Parry Target = 9 + DX + Weapon Skill + weapon parry bonus + state modifiers
```

### Block Target

```
Block Target = 9 + ST + Shield Skill + shield bonus + state modifiers
```

Block is limited by facing, available shield coverage, and whether the attack could plausibly be intercepted. Block is weaker against attacks from the flank or rear. Shields are not a full substitute for cover against missile fire.

---

## Heavy Armor and Strength Requirements

Heavy armor requires Strength to use effectively. For each armor type, define:
- Damage Reduction (DR)
- Armor penalty
- Minimum ST

If the wearer's ST is below minimum ST:
- Apply the armor penalty twice
- Reduce SPD by 1
- Reduce RS by 1
- The wearer may not use Sprint or Counter unless a trait overrides this

This creates a meaningful tank path instead of making armor universally optimal.

---

## Encumbrance Levels

| Encumbrance Level | Maximum Load | SPD Effect | Notes |
|---|---|---|---|
| **Light** | ST × 5 kg | None | No penalty. |
| **Medium** | ST × 10 kg | –1 SPD | –1 to defense checks. |
| **Heavy** | ST × 15 kg | –2 SPD | –2 to defense checks; some reactions unavailable. |
| **Overloaded** | Above ST × 15 kg | Cannot move | –4 to checks; cannot act meaningfully. |

---

## Resistances (Saving Throws)

| Resistance | Formula | Usage |
|---|---|---|
| **Poison/Disease** | 3d6 ≤ CON + WIL | Resist toxins, illness, and drugs. |
| **Magic/Enchantment** | 3d6 ≤ IQ + WIL | Resist spells that charm, control, or alter the mind. |
| **Fear/Terror** | 3d6 ≤ WIL + ⌊CON/2⌋ | Resist fear effects; equals PR check. |
| **Illusion/Deception** | 3d6 ≤ IQ + Perception | See through disguises and illusions. |

If a resistance roll succeeds by 5 or more, the character is unaffected. A failure by 5 or more may impose an extra penalty or condition at the GM's discretion.
