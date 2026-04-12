# Game Rulebook — Section 8: Skills, Character Creation, and Progression

## Skills as Reliability, Not Permission

Attributes define raw capability. Skills define how reliably that capability becomes action. In this system, progression is primarily about becoming more consistent under pressure, not about unlocking whole new action categories.

That principle applies to mundane action and magic equally. A practiced swordsman hits more reliably than an untrained brawler. A practiced Force user shapes motion more reliably than someone making a desperate first attempt. The core loop does not change.

Magic uses the same resolution system described in Section 1. Spell proficiency changes instability, exposure cost, and outcome consistency, not whether the player is allowed to try.

---

## General Skill Ratings

Most mundane skills use the standard bonus ladder below.

| Rating | Label | Bonus |
| --- | --- | --- |
| Untrained | No skill | Attribute – 4 (default) |
| Novice | Basic competence | +0 |
| Competent | Practiced fighter | +2 |
| Proficient | Reliable specialist | +4 |
| Expert | Exceptional technique | +6 |
| Master | Peak human craft | +8 |

### Effective Skill = Relevant Attribute + Skill Bonus + Equipment Bonus + Circumstance Modifiers

If a character attempts to use a skill for which they have no training, they default to:

```text
Effective Target = Relevant Attribute − 4
```

For example, a hero with **ST 12** picking up a great axe but lacking Axes skill would treat their effective heavy-melee attack target as **8**.

---

## Spell Proficiency Tiers

Spell modes do not use the mundane +0/+2/+4 ladder. They use tiers that explicitly change reliability, instability, and exposure.

Any spell can be attempted at any time. Proficiency affects how dangerous and consistent that attempt is.

| Tier | Magic Attempt Modifier | Instability | Exposure / Outcome Effect |
| --- | --- | --- | --- |
| **Untrained** | –4 | +2 instability | +1 EW and downgrade the result by one band |
| **Practiced** | –1 | +1 instability | Clean success requires margin 4+; lower successes become success with distortion |
| **Reliable** | +0 | baseline instability | Use the normal outcome bands from Section 7 |
| **Mastered** | +1 | –1 instability | May reduce EW by 1 or improve the result by one band on a success by 2+ |

This is the main answer to magic progression. Characters do not unlock new spells as discrete abilities. They become more reliable, less exposed, and less distortion-prone when using them.

---

## Skill Categories

### Combat Skills

| Skill | Relevant Attribute | Notes |
| --- | --- | --- |
| Small Blades | DX | Daggers, shortswords, rapiers |
| Swords | DX | Broadswords, longswords, sabers |
| Axes | ST | Hatchets, battle axes, great axes |
| Polearms | ST | Spears, halberds, glaives |
| Bludgeons | ST | Clubs, maces, hammers |
| Bows | DX | Short and longbows |
| Crossbows | DX | Light and heavy crossbows |
| Thrown | DX | Daggers, javelins, rocks |
| Shield | ST | Shield Block reactions |
| Dodge | DX | Dodge reactions |
| Unarmed | ST or DX | Punching, grappling, wrestling |

### Physical Skills

| Skill | Relevant Attribute | Notes |
| --- | --- | --- |
| Athletics | DX | Running, jumping, climbing |
| Stealth | DX | Sneaking, hiding |
| Acrobatics | DX | Balance, tumbling, recovering from Prone |
| Endurance | CON | Extended exertion, forced march resistance |

### Mental Skills

| Skill | Relevant Attribute | Notes |
| --- | --- | --- |
| Arcane Lore | IQ | Understanding magic attempts, instability, and strange effects |
| Tactics | IQ | Planning, ambush, terrain awareness |
| Medicine | IQ | First aid, field treatment, diagnosis |
| Perception | IQ | Noticing hidden threats, traps, and details |

### Social Skills

| Skill | Relevant Attribute | Notes |
| --- | --- | --- |
| Persuasion | WIL | Convincing, negotiating |
| Intimidation | ST or WIL | Threatening, pressuring |
| Leadership | WIL | Rally, morale support |
| Deception | IQ | Lying, disguise, misdirection |

### Spell Proficiencies

| Spell | Relevant Attribute | Notes |
| --- | --- | --- |
| Force | IQ | Motion, pressure, impact |
| Fire | IQ | Heat, ignition, denial |
| Veil | IQ | Concealment, masking, uncertainty |
| Rend | IQ | Tearing, weakening, exposed flaws |
| Bind | IQ | Restraint, anchoring, holding |
| Shift | IQ | Repositioning, displacement, changed angle |
| Vital | IQ | Stabilization, restoration, bodily continuity |
| Fracture | IQ | Disruption, breakage, interruption |

---

## Social Resolution

Social interactions use the same 3d6 ≤ target mechanic as combat:

```text
Social Action Target = Relevant Attribute + Social Skill + Situational Modifiers
```

Opposed social checks use the same margin-comparison model as combat. Pressure and wound states affect social actions just as they affect combat and magic attempts.

---

## Character Creation as Profile Shaping

Character creation is not primarily a point-buy for raw stats. It is the process of shaping a behavioral profile under constraints.

Recommended baseline:

1. Start from the campaign baseline attributes.
2. Allocate **6 profile points** across the four dimensions below.
3. No dimension may start above **3**.
4. Use the chosen dimension ratings to guide starting skills, spell proficiencies, edges, and weaknesses.

### Character Profile Dimensions

| Dimension | What It Shapes | Practical Starting Effect |
| --- | --- | --- |
| **Physical Execution** | Bodily force, weapon control, movement confidence | Supports combat and physical skills, heavy weapon use, and decisive movement |
| **Magical Control** | Stability and clarity when shaping reality | Supports Reliable spells, techniques, and lower-distortion attempts |
| **Cognitive Control** | Timing, awareness, reaction discipline | Supports RS, perception, tactical reads, and interruption play |
| **Risk Tolerance** | Willingness to operate while exposed or unstable | Supports Committed actions, reactive play, and accepting downside for tempo |

The player is not selecting a class or rigid archetype. They are defining where the character is reliable and where the character is risky.

Recommended conversion rules:

- Each **Physical Execution** point grants one pick: `+1 ST`, `+1 DX`, or raise one Combat/Physical skill by one step.
- Each **Magical Control** point grants one pick: raise one spell proficiency by one tier, gain one extra technique, or reduce instability by 1 on the first attempt of a chosen Reliable spell each scene.
- Each **Cognitive Control** point grants one pick: `+1 IQ`, `+1` to Perception or Tactics, or `+1 RS` in the first round of each encounter.
- Each **Risk Tolerance** point grants one pick: `+1` on Committed or Extended actions, ignore the first point of pressure on a risky action each scene, or qualify for one extra Edge slot.

If a campaign wants tighter numbers, keep the same structure and reduce the total profile points from 6 to 4.

---

## Linked Tradeoffs

Profile shaping works only if emphasis creates real constraints. Use the following linked trade rules during character creation:

| Emphasis | Typical Gain | Required Tradeoff |
| --- | --- | --- |
| **High commitment / output** | +1 damage or stronger force on a chosen action pattern | That pattern takes **+1 EW** |
| **High magical control** | –1 instability on one chosen Reliable spell | Large-scale or exact attempts with that spell count one speed category slower |
| **High cognitive control** | +1 RS or +1 to Perception/Tactics reads | Direct output from Force, Fire, or Rend is reduced by 1 when using that timing focus |
| **High risk tolerance** | Ignore the first point of instability or pressure on a chosen attempt each scene | Defense targets are **–1** while Committed or Extended |

These are not optional flavor tags. They are the main mechanism that prevents optimized builds from becoming flatly better in every dimension.

---

## Reliable vs. Unstable Zones

At character creation, choose **1 or 2 spells** as **Reliable**.

- **Reliable spells** start at the Reliable tier.
- All other spells start **Untrained**, which is the character's unstable zone.

Reliable spells resolve with normal instability and outcome bands. Untrained spells remain attemptable, but they gain extra instability, create extra exposure, and produce less consistent outcomes.

This is the key distinction at the start of play: what the character can attempt is broad; what the character can do cleanly is narrow.

---

## Starting Techniques

For each Reliable spell, select **1 or 2 techniques**.

A technique is a common, practiced pattern that reduces difficulty under specific conditions. It does not define a fixed outcome.

Default rule:

- A technique grants **–1 Parameter Difficulty** when used in its practiced situation.
- A technique does not bypass resistance, remove instability, or change the core resolution loop.

Suggested starting techniques:

| Spell | Techniques |
| --- | --- |
| **Force** | **Push** (moderate scale, low precision), **Deflect** (reactive timing) |
| **Fire** | **Flash** (short, bright burst), **Line Burn** (direct pressure across a lane) |
| **Veil** | **Blur** (personal concealment), **Mask** (disguise or false read) |
| **Rend** | **Shear** (open a weak point), **Expose** (worsen an existing wound or armor gap) |
| **Bind** | **Snare** (hold feet or space), **Hold** (lock a limb or route) |
| **Shift** | **Step** (short reposition), **Exchange Angle** (change line, cover, or flank) |
| **Vital** | **Seal** (close a wound), **Rouse** (stabilize and restore basic function) |
| **Fracture** | **Jolt** (interrupt concentration), **Break Ward** (disrupt structure or protection) |

Techniques exist to create recognizable habits, not to build a long skill tree.

---

## Edges

Each starting character chooses **1 to 3 Edges**.

Edges are small rule modifications tied to system interactions. They are not classes and they are not permission gates.

Examples:

- **Reactive Hand:** –1 instability on reaction-based magic attempts.
- **Clean Entry:** –1 EW on the first action taken in an encounter.
- **Early Read:** +1 RS when reacting to an Extended opponent.
- **Quiet Shape:** Ignore the first point of precision penalty on Veil or Bind techniques.
- **Hard Finish:** +1 margin when targeting an already wounded or pressured opponent.
- **Stable Focus:** Once per scene, treat a success with distortion as a clean success.

Edges should stay small. If an Edge starts reading like a separate subsystem, it is too large.

---

## Weakness Selection

Every starting character must select at least **one weakness**.

Core weaknesses:

- **High Instability Gain:** Gain +1 instability on every failed magic attempt.
- **Slow Execution:** The first magic attempt each round counts one speed category slower.
- **High Exposure Cost:** Committed or Extended actions impose an additional –1 to the next defense target.

Additional weaknesses can be invented if they fit the same pattern: narrow, coherent, and mechanically meaningful.

---

## Narrative Justification

Each player should define, in one or two sentences, how the character acquired magic:

- exposure
- partial training
- practical use
- cross-training

This has no default mechanical effect. Its purpose is coherence. The profile should make sense in the fiction.

---

## Progression

### Skill Progression

Mundane skills improve through use, pressure, and reflection just as before. Spell progression uses tiers:

```text
Untrained -> Practiced -> Reliable -> Mastered
```

Each improvement increases reliability rather than unlocking new capability.

### Learning Model

Progression occurs through:

- use under pressure
- failure followed by correction
- exposure to higher-difficulty situations

Optional formal training can reduce variance and speed learning, but it is not required. A character can learn from field use, not only from teachers.

### No Hard Unlocks

Any spell can be attempted at any time.

Proficiency affects:

- instability gain
- exposure cost
- outcome consistency

It does **not** affect basic permission to try.

### Advancement Procedure

Recommended procedure:

1. Mark a mundane skill or spell whenever it is used under real pressure.
2. If the use involved failure, distortion, or meaningful resistance, mark it again.
3. During downtime, advance one marked item if the character spent time reflecting, practicing, or correcting mistakes.

This keeps progression tied to behavior and consequence instead of to abstract unlock trees.

---

## Provisional Scope

These rules aim to keep player-facing concepts minimal:

- what the character can attempt
- what the character is reliable with
- what the character risks when pushing harder

If future expansion adds more detail, it should still preserve that structure.
