# Game Rulebook — Section 8: Skills and Progression

## Preamble: Skills as Probability Amplifiers

Attributes define the raw floor of a character's capability. Skills define how much of that capability is trained and reliable. In the 3d6 system, each point of effective skill raises the success probability by a meaningful amount — roughly 5–10% in the middle of the curve where most characters operate. A character who has trained extensively is not just "better in flavour"; they have a statistically distinct success profile on every relevant roll.

The design intentionally weights skill at least as highly as raw attributes, following the GURPS and TFT principle that a focused practitioner outperforms a raw talent. A character with DX 10 and Sword skill +6 has an effective attack target of 16, which is near the ceiling of the achievable range. That same character with DX 14 and no training has a target of 10 — barely competent. This gap makes character creation choices meaningful and makes progression feel substantial.

Skills also function as the primary lever for long-term character growth. Attribute increases are rare and expensive; skill increases are the normal reward for play and experience. This means the probability improvements from advancement are legible: going from Sword +4 to Sword +6 is a concrete, calculable change in success rate that players can see and value.

---

## Skill Ratings

Characters have skill ratings corresponding to broad categories. A skill rating represents training and familiarity and is expressed as a bonus added to the relevant attribute to form an Effective Target Number.

| Rating | Label | Bonus |
|---|---|---|
| Untrained | No skill | Attribute – 4 (default) |
| Novice | Basic competence | +0 |
| Competent | Practiced fighter | +2 |
| Proficient | Reliable specialist | +4 |
| Expert | Exceptional technique | +6 |
| Master | Peak human craft | +8 |

**Effective Skill = Relevant Attribute + Skill Bonus + Equipment Bonus + Circumstance Modifiers**

---

## Defaulting When Untrained

If a character attempts to use a skill for which they have no training, they default to:

```
Effective Target = Relevant Attribute − 4
```

For example, a hero with DX 12 picking up a great axe but lacking Heavy Weapons skill would treat their effective attack target as 8. The action remains possible; it is simply much harder.

Some skills (Arcane Magic, Surgery) have no useful default and cannot be attempted without at least Novice training.

---

## Skill Categories

Skills are grouped into five broad categories. Within each category, specific skills share the same relevant attribute and default.

### Combat Skills

| Skill | Relevant Attribute | Notes |
|---|---|---|
| Small Blades | DX | Daggers, shortswords, rapiers |
| Swords | DX | Broadswords, longswords, sabers |
| Axes | ST | Hatchets, battle axes, great axes |
| Polearms | ST | Spears, halberds, glaives |
| Bludgeons | ST | Clubs, maces, hammers |
| Bows | DX | Short and longbows |
| Crossbows | DX | Light and heavy crossbows |
| Thrown | DX | Daggers, javelins, rocks |
| Shield | ST | Shield Block reactions |
| Dodge | DX | Dodge reactions (may be trained separately) |
| Unarmed | ST or DX | Punching, grappling, wrestling |

### Physical Skills

| Skill | Relevant Attribute | Notes |
|---|---|---|
| Athletics | DX | Running, jumping, climbing |
| Stealth | DX | Sneaking, hiding |
| Acrobatics | DX | Balance, tumbling, recovering from Prone |
| Endurance | CON | Extended exertion, forced march resistance |

### Mental Skills

| Skill | Relevant Attribute | Notes |
|---|---|---|
| Arcane Lore | IQ | Understanding spells and magical phenomena |
| Tactics | IQ | Planning, ambush, terrain awareness |
| Medicine | IQ | First aid, field treatment, diagnosis |
| Perception | IQ | Noticing hidden threats, traps, and details |

### Social Skills

| Skill | Relevant Attribute | Notes |
|---|---|---|
| Persuasion | WIL | Convincing, negotiating |
| Intimidation | ST or WIL | Threatening, pressuring |
| Leadership | WIL | Rally, morale support |
| Deception | IQ | Lying, disguise, misdirection |

### Arcane Skills (Magic Disciplines)

| Skill | Relevant Attribute | Notes |
|---|---|---|
| Elementalism | IQ | Fire, air, earth, water spells |
| Necromancy | IQ | Death, undead, life-force spells |
| Warding | IQ | Protective and barrier spells |
| Divination | IQ | Sight, detection, knowledge spells |
| Healing | IQ | Restorative and curative spells |
| Binding | IQ | Restraint, control, compulsion spells |

---

## Social Resolution

Social interactions use the same 3d6 ≤ target mechanic as combat:

```
Social Action Target = Relevant Attribute + Social Skill + Situational Modifiers
```

Opposed social checks use the same margin-comparison model as combat. The "defender" rolls against their own WIL or IQ to resist.

Pressure and wound states can affect social actions: a character who is Shaken or Broken suffers the same penalties to social skills as to combat skills.

---

## Assigning Skills at Character Creation

Starting characters receive a limited pool of skill points to distribute. A suggested starting allocation:

- **Novice characters:** 4 skill points total. One skill at Competent (+2), two at Novice (+0).
- **Experienced characters:** 6–8 skill points. Two skills at Proficient (+4), one at Competent (+2).
- **Veterans:** 10+ skill points. One skill at Expert (+6), others distributed.

Each rank increase costs 1 point (Novice → Competent → Proficient → Expert → Master). Some high-tier skill ranks may require minimum attribute levels or training from a teacher.

---

## Skill Advancement

Characters improve skills through play. The recommended advancement model:

1. After a session in which a skill was used and challenged (a roll under pressure, not just a routine task), mark that skill.
2. During downtime, roll 3d6 against the skill's current Effective Target. If the roll **exceeds** the target (i.e., fails the check), the skill increases by one rank. Success means the character is performing within their current ability; failure means they encountered their limits and learned from them.
3. Attribute increases are rare — awarded for major milestones, powerful blessings, or extended training sequences.

---

## Provisional Nature

These rules are intentionally lightweight for the first implementation. As the full character-creation system matures, skills will be expanded beyond combat to include more social, environmental, and investigative options. The principle of using the same 3d6 ≤ target resolution for every skill check is fixed; the specific skill list and advancement costs are subject to playtesting refinement.

---

## Skill Proficiency Summary

| Effective Target (Attr + Skill) | Success Probability (3d6) |
|---|---|
| 6 | ~9% |
| 8 | ~26% |
| 10 | ~50% |
| 12 | ~74% |
| 14 | ~91% |
| 16 | ~98% |
| 17 | ~99%+ |

These probabilities illustrate why skill matters. The difference between a Novice fighter (effective target ~10, 50% success) and an Expert fighter (effective target ~16, 98% success) is decisive over the course of a combat encounter. Players who invest in a focused skill have a statistical reason to feel the difference.
