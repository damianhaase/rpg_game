## Ranged Combat

Missile and thrown weapons introduce new tactical considerations into the core 3d6 resolution engine.  In contrast to melee, ranged attacks are more sensitive to distance and cover, and they encourage careful preparation rather than brute-force aggression.

### Range bands and modifiers

Divide distances into abstract range bands.  Each band applies a modifier to the attacker’s base to‑hit value:

| Range band     | Description                           | Modifier |
|---------------|----------------------------------------|---------|
| **Point‑blank** | Within a few metres; target is within arm’s reach (e.g., knife throw, pistol shot) | **+2** |
| **Near**        | Close but outside melee range; typical bow or short‑range spell distance | **+1** |
| **Medium**      | Standard engagement distance; the default if no range is declared | **0** |
| **Far**         | Long distance where aim and projectile drop matter | **–2** |
| **Extreme**     | Maximum distance; shots are difficult or impossible depending on weapon | **–4** (or disallowed) |

### Ranged attack roll

To resolve a ranged attack, roll 3d6 and compare it to the attacker’s **Effective Missile Skill**:

\[ \text{Effective Missile Skill} = \text{DX} + \text{Missile Skill} + \text{Weapon Accuracy} + \text{Range Modifier} + \text{Aim Bonus} + \text{Situation Modifiers} \]

* **DX + Missile Skill** reflects the character’s coordination and training.
* **Weapon Accuracy (Acc)** is a small bonus (typically +1 to +3) that represents a bow’s sights, a musket’s rifling, or a focus glyph on a wand.
* **Range Modifier** comes from the table above.
* **Aim Bonus** accrues when the attacker spends an action to aim.  Each full turn of aiming grants +1 (to a maximum equal to the weapon’s Acc).  If the attacker moves or is attacked, the aim bonus resets.
* **Situation Modifiers** include high ground, wind, poor visibility, and pressure effects.  Keep these modifiers within ±3 to maintain the smooth bell curve of 3d6 rolls【566123300269821†L74-L83】.

### Defensive adjustments against ranged attacks

Ranged attacks shift the emphasis from dodging to using cover.  In the core melee system, defenders roll against a situational **Defense Value (DV)**.  For missile fire:

* **Dodge** is less effective: subtract 2 from the defender’s usual DV against ranged attacks.  Dodging arrows is harder than dodging sword blows.
* **Cover** adds directly to DV.  Partial cover grants +1 to +3; total cover blocks the attack entirely.  Use narrative descriptors—standing behind a stone wall is better than behind a tree—and avoid granular modifiers to retain clarity.
* **Take Cover** replaces the melee guard action.  As a minor action, a character may deliberately seek cover, gaining +2 to +4 DV against the next ranged attack.

### Design principles for ranged combat

These guidelines ensure that adding missile weapons enhances tactical depth without overwhelming the core mechanic:

1. **Predictable, small modifiers** – Range and aim bonuses should remain within ±4 so that each point on the 3d6 curve has meaningful impact【566123300269821†L74-L83】.
2. **Preparation matters** – Characters must weigh the benefits of taking a full turn to aim against acting immediately; this decision creates tension.
3. **Exposure is punishing** – Characters caught in the open are easier to hit.  Encourage players to think about cover and positioning.
4. **Distinct from melee** – Ranged combat should not simply reuse melee rules; it prioritises accuracy over defence and emphasises the environment.

\*

## Magic System (Instability‑Based)

The world of this game assumes that reality is malleable but resists manipulation.  Magic is powerful, but it incurs **instability**—a metaphysical strain that grows with each spell cast.  Following Sanderson’s guidelines for compelling magic systems, spells are defined by clear costs and limitations【909350560901867†L36-L41】.

### Spell components

Each spell has the following descriptive elements:

* **Intent** – The broad purpose of the magic, such as *damage*, *bind*, *reveal*, or *alter*.  This informs narrative effects and helps adjudicate unusual interactions.
* **Tier** – A rough measure of power (1–5).  Higher tiers require more skill and introduce greater instability.
* **Instability Cost (IC)** – A number (1–10) representing how much casting the spell strains reality.  Low‑tier utility spells might cost 1 or 2; a tier‑5 portal might cost 8 or more.

### Casting roll

A spellcaster rolls 3d6 and compares it to their **Spellcasting Target**:

\[ \text{Spellcasting Target} = \text{WIL} + \text{Discipline Skill} + \text{Focus Item Bonus} - \text{Pressure} - \text{Current Instability} \]

* **WIL + Discipline Skill** reflects mental fortitude and training in a magical discipline (e.g., Elementalism, Necromancy).
* **Focus Item** (e.g., wand, staff, sacred text) grants a small bonus (+1 to +3).
* **Pressure** is the combat stress tracked in the core system; high pressure makes spellcasting harder.
* **Current Instability** is the cumulative instability accrued from previous spells in the current scene.  Each spell cast adds its Instability Cost to the caster’s instability pool.

**Outcomes**:

* **Success (roll ≤ target)** – The spell takes effect.  Add its Instability Cost to your instability pool.
* **Failure (roll > target)** – The spell partially succeeds or fizzles; you gain twice the spell’s Instability Cost, and the GM introduces a minor side effect (e.g., sparks, whispers).  The intended effect may be weakened or misdirected.
* **Critical Failure (natural 18 or failure by 5+)** – A **Drift Event** occurs.  Reality briefly warps: time distorts, a random spell triggers, or a creature from elsewhere slips through.  The caster’s instability pool resets to zero as the backlash discharges, but the narrative consequences can be severe.

### Managing instability

Instability dissipates slowly.  Outside of combat, a few minutes of rest reduce your instability pool to zero.  Certain rituals or focus items may accelerate this.  High instability also makes it harder to resist pressure effects, so reckless casters risk becoming Shaken or Panicked.

### Magic design principles

1. **Limits and costs over raw power** – Interesting magic stems from weaknesses and trade‑offs【909350560901867†L36-L41】.  Spells with low instability can be cast freely; high‑tier spells should be rare and risky.
2. **Subsystem synergy** – Use existing mechanics (pressure, states) rather than adding new dice systems【909350560901867†L34-L41】.  This keeps the game lean and transparent.
3. **Transparency with risk** – Show players the instability cost and casting target up front.  They should understand the odds and potential consequences before casting.
4. **Narrative consequences** – Magic can alter the story in unpredictable ways.  The Drift Event table is intentionally open‑ended; GMs should tailor outcomes to the scene.

\*

## Equipment Schema

Equipment adds flavour and strategic options.  To avoid unbalancing scenarios, gear must offer both benefits and drawbacks【927586306629711†L29-L39】【927586306629711†L59-L64】.  Items should influence the player’s decision space rather than simply improve numbers.

### Weapons

Define each weapon using a small set of properties:

* **Accuracy (Acc)** – A bonus applied to to‑hit rolls.  Most melee weapons grant +0; daggers or rapiers might grant +1; firearms or bows range from +1 to +3.
* **Damage** – The base damage die and modifiers (e.g., 1d6–1 for a dagger, 1d6+2 for a broadsword).  Add the attacker’s Damage Bonus (DB) as defined in the core system.
* **Parry Bonus** – A bonus to parry reactions.  Small, agile weapons might grant +1; large, unwieldy weapons grant 0 or –1.
* **Traits** – Keywords that describe special behaviour: *reach* (can attack from one band farther), *fast* (reduces penalty when evading), *heavy* (imposes –1 to initiative but deals +2 damage), *thrown* (can be used as a missile weapon), etc.  Traits open up tactical choices rather than simply adding modifiers.

#### Weapon example

| Weapon        | Acc | Damage  | Parry | Traits              |
|--------------|----|---------|------|---------------------|
| Dagger        | +1 | 1d6–1   | +1   | small, thrown       |
| Broadsword    | 0  | 1d6+2   | +2   | medium, balanced    |
| Longbow       | +2 | 1d6+1   | –    | ranged, two‑handed   |
| Great Axe     | –1 | 2d6+0   | 0    | heavy, cleaving     |

### Armor

Armor reduces incoming damage but makes you less agile.  Define armor with:

* **Damage Reduction (DR)** – Subtract this from incoming damage before applying it to HP (minimum damage of 1).
* **Dodge Penalty** – A negative modifier to DV when dodging.  Chainmail might offer DR 3 with a –1 penalty; plate armor could offer DR 5 with a –2 penalty.
* **Traits** – *flexible* (reduces penalty when prone), *bulky* (reduces SPD by 1), *unstable* (interferes with spellcasting; adds +1 to instability costs), etc.

#### Armor example

| Armor         | DR | Dodge Penalty | Traits         |
|--------------|----|--------------|---------------|
| Leather       | 1  | 0            | flexible       |
| Chainmail     | 3  | –1           | flexible       |
| Plate         | 5  | –2           | bulky          |
| Mage Robes    | 0  | 0            | light, unstable |

### Item design guidelines

1. **Balance bonuses with drawbacks** – For every advantage a piece of gear provides, incorporate a cost or limitation.  This keeps scenarios from being trivialised by single items【927586306629711†L59-L64】.
2. **Keep modifiers small** – Equipment bonuses should typically range from ±1 to ±3 so they fit comfortably within the 3d6 bell curve【566123300269821†L74-L83】.
3. **Emphasise traits** – Traits expand the tactical toolkit by granting new options or enabling creative play rather than just increasing numbers.
4. **Narrative consistency** – Gear should fit the game’s world and tone.  Discuss unusual items with players to ensure they enhance, rather than derail, the story【927586306629711†L29-L39】.

\*

## Damage and Injury Model

The current rules explain how to calculate Hit Points (HP) and apply damage and DR, but they don’t define how different wound severities affect play.  Inspired by optional GURPS wound rules【993098882415824†L88-L90】, this model divides wounds into categories that drive state changes rather than just subtracting HP.

### Damage resolution

1. **Deal damage** – When an attack hits, roll the weapon’s damage, add the attacker’s DB, and subtract the defender’s DR (minimum damage of 1).
2. **Apply to HP** – Subtract the result from the target’s HP.  Track each wound separately rather than lumping all damage into one pool; this allows different wounds to cause different effects.

### Wound categories and effects

Assess each wound based on the amount of damage from a single hit relative to the victim’s maximum HP:

| Wound category | Damage (relative to max HP) | State effect |
|---------------|-----------------------------|-------------|
| **Light Wound** | ≤10 % (or ≤3 points for average humans)【993098882415824†L88-L90】 | No immediate penalties; the wound is mostly superficial.  Marks, bruises, and shallow cuts may still contribute to Pressure gain. |
| **Serious Wound** | 10 %–25 % (≈4–8 points)【993098882415824†L88-L90】 | The victim takes a –1 penalty to attack and defence rolls and may lose 1 SPD until the wound is treated.  Serious wounds increase Pressure gain and may prevent the Commit manoeuvre. |
| **Critical Wound** | >25 % (≥9 points)【993098882415824†L88-L90】 | The character is staggered: –3 to checks, cannot Commit or Counter‑attack, and must immediately make a Pressure roll or become Shaken.  Critical wounds can lead to incapacitation or death if left untreated. |

Any number of simultaneous Light Wounds can accumulate to create a Serious Wound at the GM’s discretion.  Tracking separate injuries encourages narrative consequences (e.g., a wounded arm may impose a –2 penalty when using that arm).

### Healing and recovery

* **Field treatment** – During combat, a character may use a **First Aid** action to bandage a wound.  On a successful WIL + Medicine roll, one Light Wound is stabilised (preventing bleeding)【993098882415824†L92-L95】.  Serious or critical wounds cannot be healed in battle without magic.
* **Rest** – Light wounds heal after a short rest (about an hour); serious wounds require a long rest (a day or more) or medical care; critical wounds need extended rest or magic.
* **Magic healing** – Healing spells function like other spells: they have an Instability Cost and target WIL + Healing Skill.  Minor healing closes Light Wounds; major healing closes one Serious Wound (up to eight points)【993098882415824†L190-L199】.  Critical healing spells require higher tiers and significant instability costs.

### Design notes

1. **State over subtraction** – Wound categories change the characters’ options (e.g., reduced SPD, restricted reactions) rather than just lowering HP.  This makes injury meaningful.
2. **Discrete injuries** – Tracking each wound separately allows for targeted healing and narrative consequences, as suggested in the GURPS optional wound system【993098882415824†L88-L90】.
3. **Simple thresholds** – Using relative thresholds (percentages of max HP) scales naturally across species and character builds.  Adjust the ranges if testing shows the game is too lethal or too forgiving.

\*

## Suggested Next Steps

The systems above cover missile combat, a risk‑based magic system, a structured equipment schema, and a state‑driven damage model.  To further align the game with the completeness of a system like GURPS while preserving its clarity and transparency, consider the following future additions:

1. **Action economy** – Define one major action, one minor action, and a reaction per turn.  This prevents ambiguity and codifies how aim, movement, and spellcasting interact.
2. **Formalised status effects** – Expand the existing state system to include conditions such as Stunned, Bound, Frightened, and On Fire, each with tags (movement, attack, mental) and duration.
3. **Skill categories and defaults** – Group skills into Combat, Physical, Mental, Social, and Arcane.  Untrained attempts use the relevant attribute minus 2.  This mirrors GURPS’s exhaustive skill list in a simplified form.
4. **Character creation** – Introduce a point‑allocation system for attributes, starting skills, and traits.  Include optional advantages and disadvantages (e.g., *High Pain Threshold*, *Fragile*, *Lucky*) that grant small bonuses and narrative hooks.
5. **Social interactions** – Reuse the core mechanic for persuasion and intimidation: `3d6 ≤ CHA + Social Skill + Situational Modifiers`.  This completes the engine’s coverage of non‑combat actions.

These modules can be added incrementally.  Throughout development, keep the guiding principles of small modifiers, decision clarity, and transparent mechanics at the forefront【566123300269821†L74-L83】【909350560901867†L36-L41】.

\*

## Phase 1 Implementation Specification

The following specification fleshes out the Phase 1 systems—ranged combat, injury, and equipment—so they are ready to implement.  It expands on the earlier design notes with concrete rules, data structures and pseudocode.  All mechanics continue to use the 3d6 target‑based resolution mechanic, maintain small modifiers, and present probabilities clearly to the player【566123300269821†L74-L83】.

### 1 Ranged / Missile Combat (Detailed)

#### 1.1 Design intent

Missile and thrown combat should feel distinct from melee.  It emphasises positioning and preparation, offers fewer defensive options (dodging is harder), increases the importance of cover, and introduces pacing through reload or readiness mechanics.

#### 1.2 Range model

Reuse the **range bands** from the earlier table (Point‑blank, Near, Medium, Far, Extreme).  Each band is defined by an ID and modifier:

```json
RangeBand = {
  id: "NEAR",
  modifier: +1
}
```

#### 1.3 Ranged attack formula

An attacker’s target number for a missile attack is calculated as:

\[ \text{Ranged Target} = \text{DX} + \text{Missile Skill Rank} + \text{Weapon Accuracy} + \text{Range Modifier} + \text{Aim Bonus} + \text{Situation Modifiers} \]

Clamp this value to the 3–17 range before converting it to a probability via the 3d6 cumulative distribution function.  Pseudocode:

```python
def ranged_target(attacker):
    base = attacker.DX + attacker.missile_skill + attacker.weapon.acc
    base += attacker.current_range.modifier + attacker.aim_bonus + attacker.situation_mods
    return clamp(3, 17, base)

def probability(target):
    return CDF_3d6[target]

# Example: compute the probability to hit
T = ranged_target(attacker)
P = probability(T)
```

#### 1.4 Aim mechanic

An attacker may **Aim** instead of firing.  Each Aim action grants +1 to the next ranged attack (up to a default maximum of 2 stacks).  Aim stacks are lost if the attacker takes damage, is forced to move, or switches targets.  Track aim state per attacker:

```json
AimState = {
  stacks: 0,
  target_id: null
}
```

#### 1.5 Defense versus ranged attacks

Ranged defence shifts emphasis from active dodging to using the environment:

* **Dodge penalty** – Subtract 2 from the defender’s usual Dodge Target when resisting missile attacks; dodging arrows or bullets is harder than avoiding melee blows.
* **Cover system** – Apply cover bonuses directly to defence: **Light Cover** +1; **Medium Cover** +2; **Heavy Cover** +3; **Full Cover** makes the target untargetable.  Cover is relative and narrative; avoid overly granular modifiers to preserve decision clarity【566123300269821†L74-L83】.
* **Take Cover** – Replace the Guard reaction with a “Take Cover” minor action.  This action grants a +2 (or more, at GM discretion) defence bonus against ranged attacks and may enable counter‑fire (the character leans out and shoots while staying partially protected).

#### 1.6 Reload and readiness

Some weapons must be reloaded after each shot.  Represent the weapon’s loaded state explicitly:

```json
WeaponState = {
  loaded: true,
  ammo: null   # or integer if the weapon tracks ammunition
}
```

Rules:

* Weapons flagged as `reload: true` require a full action to reload after firing.  If a character attempts to shoot an unloaded weapon, it fails.
* Optional quick reloads allow reloading as a minor action but impose a –1 penalty on the next attack.  This adds a tactical decision: shoot faster at a penalty or reload carefully.

#### 1.7 Opposed resolution (ranged)

When resolving an attack, compute the probability that the attacker succeeds (P\_A) and the probability that the defender succeeds (P\_D, including cover bonuses).  The final hit chance is:

\[ P(\text{hit}) = P_A \times (1 - P_D) \]

This formula ensures that both parties’ skills and situational modifiers influence the outcome transparently.

#### 1.8 UI output example

When presenting ranged attack options to players, display the intermediate calculations and outcomes.  For instance:

* **Fire at Goblin (Medium Range)**
  * Hit: 62 % (Good)
  * Critical: 1.9 %
* **Target defence**:
  * Dodge: 38 %
  * Cover: +2
  * Final hit chance: 38 %

This style reinforces probability transparency and highlights how cover and dodge interact.

### 2 Damage & Injury System (Detailed)

#### 2.1 Design intent

Injuries should degrade a character’s effectiveness and force difficult decisions rather than simply depleting a hit‑point pool.  The model must be lightweight and rely on the same mechanics used elsewhere.

#### 2.2 Damage formula

Calculate damage in two stages:

1. **Base damage** – Roll the weapon’s damage dice (plus the attacker’s damage bonus) to obtain a number.
2. **Final damage** – Subtract the defender’s armor damage reduction (DR):

\[ \text{Final Damage} = \max\left(0, \text{Base Damage} - \text{Armor DR}\right) \]

#### 2.3 Health model

Each creature has a pool of hit points derived from Constitution (e.g., HP = CON × 2).  Losing HP moves the creature along injury thresholds.  Keep the total HP small (e.g., 10–20 for human‑like characters) to encourage tactical play.

#### 2.4 Injury thresholds

Instead of recording the exact number of HP remaining, classify the character’s state according to the percentage of HP lost in a single hit:

| HP lost in one hit | Category | State effect |
|-------------------|---------|-------------|
| 0 %–25 %         | **Light Wound** | No immediate penalty.  The blow is mostly superficial but still contributes to pressure gain. |
| 25 %–50 %        | **Heavy Wound** | –1 to all physical actions.  The injury bleeds and slows movement. |
| 50 %–75 %        | **Severe Wound** | –2 to actions.  The victim must test (e.g., CON or WIL) to avoid collapsing before taking any major action. |
| 75 % or more     | **Critical Wound** | The character risks incapacitation; further checks may render them unconscious or worse. |

These thresholds mirror the optional wound categories in GURPS【993098882415824†L88-L90】 but are expressed as percentages to scale across different HP totals.  They change how the character acts rather than just tracking numbers.

#### 2.5 Wound effects and stagger

Represent the current wound with a simple data structure:

```json
WoundState = {
  level: "light" | "heavy" | "severe" | "critical",
  modifiers: []
}
```

Apply the following ongoing penalties by wound level:

| Level     | Effect                                                        |
|-----------|---------------------------------------------------------------|
| Light     | none                                                         |
| Heavy     | –1 to all physical actions                                   |
| Severe    | –2 to actions; must test (CON or WIL) to act                 |
| Critical  | risk of incapacitation or death; actions nearly impossible   |

A **stagger** occurs when a single hit meets or exceeds a designated threshold (e.g., 25 % of max HP).  A staggered character suffers –2 to attack, –1 to defence and can perform only a limited action on their next turn.  This encourages careful resource management and discourages reckless charges.

#### 2.6 Critical outcomes

On a natural 3 or 4, the attacker scores a **critical success**.  They may choose to add 50 % extra damage or apply a special effect (e.g., disarm, knockdown).  On a roll of 17 or 18, the attacker suffers a **critical failure**—their weapon jams, they fall prone, or a friend is inadvertently targeted.  This preserves dramatic high and low moments.

#### 2.7 Death and incapacitation

When HP drops to zero or below, the character must make a Constitution check.  Success means they remain conscious but suffer severe penalties; failure renders them incapacitated.  Additional failed checks (at the GM’s discretion) may result in death.  This simple check ties mortality to character toughness without requiring extra tables.

### 3 Equipment System (Detailed)

#### 3.1 Design intent

Equipment should add variety and flavour, not just bigger numbers.  Each item should confer a small benefit and a potential drawback, reinforcing the principle that no piece of gear trivialises challenges【927586306629711†L59-L64】.

#### 3.2 Weapon schema

Represent each weapon as a record with clear fields:

```json
Weapon = {
  id: "short_sword",
  type: "melee" | "ranged",
  accuracy: +1,
  damage: {
    base: 4,
    variance: "1d6"  # optional for variable damage
  },
  parry_bonus: +1,
  traits: ["fast", "light"],
  range_band: null | "NEAR",   # ranged weapons set this field
  reload: false,                # whether the weapon requires reloading
  ammo_capacity: null           # number of shots before reloading, if applicable
}
```

#### 3.3 Weapon traits

Traits modify how a weapon behaves and encourage tactical choices.  Examples include:

| Trait      | Effect                                             |
|------------|-----------------------------------------------------|
| **fast**   | +1 to initiative or counter‑attack                  |
| **heavy**  | +2 damage but –1 to hit                             |
| **precise**| +1 to aim bonus                                     |
| **unwieldy** | cannot be used for counter‑attacks                 |
| **close\_only** | cannot attack beyond the NEAR range band         |

Assigning traits allows two weapons with identical damage to feel different in play.

#### 3.4 Armor schema

Armor is defined by its damage mitigation and agility penalty:

```json
Armor = {
  id: "leather",
  damage_reduction: 2,
  dodge_penalty: -1,
  traits: ["flexible"]
}
```

#### 3.5 Armor effects

Armor alters two parts of combat resolution:

* **Damage reduction** – Reduce incoming damage by the armor’s DR (to a minimum of zero).
* **Dodge penalty** – Apply the negative modifier to the defender’s Dodge Target when they attempt to evade (this stacks with the ranged dodge penalty).  Heavy armor slows characters down and makes them easier targets.

#### 3.6 Item schema (non‑weapon)

Other items are simple containers of limited‑use effects:

```json
Item = {
  id: "binding_shard",
  uses: 3,
  effects: [
    {
      type: "modifier",
      target: "bind_action",
      value: +2
    }
  ]
}
```

#### 3.7 Equipment slots (optional minimal)

For simplicity, allow each character to equip: one main weapon, one offhand item, one armor, and up to three utility items.  Encumbrance rules may restrict how many items a character can carry without penalty.

#### 3.8 Encumbrance (lightweight)

Categorise total carried weight into three bands:

* **Light** – No penalties; the character is free to act normally.
* **Medium** – –1 to Dexterity (affects all DX‑based targets, including missile attacks and defence).  The character tires more quickly.
* **Heavy** – –2 to Dexterity and –1 to Dodge.  The character may not Sprint or Commit.

Encumbrance integrates with the injury system: wounded characters may find themselves effectively in the Medium band due to reduced strength or stamina.

### 4 Integration with the Existing System

The following pseudocode demonstrates how Phase 1 mechanics dovetail with the core engine.

#### 4.1 Unified target calculation

```python
def compute_target(attribute, skill_rank, equipment_bonus, state_mods, situation_mods):
    return attribute + skill_rank + equipment_bonus + state_mods + situation_mods
```

#### 4.2 Probability engine

```python
def probability(target):
    T = clamp(3, 17, target)
    return CDF_3d6[T]
```

#### 4.3 Opposed resolution

```python
def hit_chance(attacker_target, defender_target):
    pA = probability(attacker_target)
    pD = probability(defender_target)
    return pA * (1 - pD)
```

#### 4.4 Damage resolution

```python
def resolve_damage(base_damage, armor_dr):
    return max(0, base_damage - armor_dr)
```

#### 4.5 Apply injury

```python
def apply_damage(entity, damage):
    entity.hp -= damage
    update_wound_state(entity)
```

#### 4.6 Update wound state

```python
def update_wound_state(entity):
    ratio = (entity.max_hp - entity.hp) / entity.max_hp
    if ratio < 0.25:
        state = "light"
    elif ratio < 0.5:
        state = "heavy"
    elif ratio < 0.75:
        state = "severe"
    else:
        state = "critical"
    entity.wound_state.level = state
    # apply the appropriate modifiers based on the state
```

This framework keeps all calculations transparent and easily adjustable.  It can be encoded directly into a digital tool or executed by a game master with pencil and paper.

### 5 Design consistency check

By adhering to the above specification, Phase 1 preserves the fundamental design principles of this system:

1. **Single resolution mechanic** – All actions resolve using `3d6 ≤ target`, ensuring system cohesion.
2. **Small modifiers** – Bonuses and penalties rarely exceed ±3, keeping the probability curve meaningful【566123300269821†L74-L83】.
3. **Decision clarity** – Players see how each factor contributes to success or failure; UI examples should display intermediate values.
4. **State‑driven outcomes** – Injuries and encumbrance impose narrative state changes rather than just numerical subtraction.
5. **Probability transparency** – Show percentage chances for success and failure so players can make informed choices.

### 6 What Phase 1 enables

With Phase 1 implemented, the system immediately supports:

* Mixed melee and ranged encounters where positioning and cover matter.
* Tactical decisions about taking aim, reloading, and taking cover.
* Meaningful differentiation between weapons and armor through traits and bonuses【927586306629711†L29-L39】.
* A lightweight but impactful injury model that degrades performance and introduces stagger states.
* An expandable item ecosystem with defined schemas, enabling easy extension and digital integration.

### 7 Next step

Phase 1 provides a robust combat foundation.  Logical next steps include:

* Implementing **Phase 2** systems: a full instability‑driven magic system, formal status effect tags, and a defined action economy (major/minor/reaction).
* Expanding the combat loop to seamlessly integrate melee, ranged and wound mechanics.
* Adding character creation rules (attributes, skills, traits) and social interaction mechanics, using the same 3d6 resolution engine.  These will make the game feel more complete while retaining the clarity and transparency established thus far.

\*

## Fully Integrated Combat System: Ranged, Melee & Wounds

The preceding sections outline ranged combat, injury, and equipment in isolation.  This section explains how those components plug into the core resolution engine alongside existing melee rules to create a cohesive, self‑contained combat system.

### Unified probability framework

At the heart of the game is a single resolution mechanic: roll **3d6** and compare it to a **target number**.  Whether swinging a sword, loosing an arrow, casting a spell or resisting intimidation, the procedure is the same:

1. **Compute the effective target** using the unified formula (attribute + skill + equipment bonuses + state modifiers + situation modifiers).
2. **Clamp** the target to the range 3–17 and look up its probability in the 3d6 cumulative distribution function.
3. **Opposed resolution** uses both parties’ probabilities: the attacker’s chance of success multiplied by one minus the defender’s chance.
4. **Resolve the outcome** – if the attack hits, calculate damage and apply wounds; if it misses, apply any side effects.

This framework ensures that every modifier—whether from range, aim, armor, wounds or encumbrance—feeds into a single target calculation.  Players can therefore understand how their choices affect success and failure without learning multiple subsystems.

### How melee and ranged differ yet remain compatible

Melee and ranged attacks both use the same probability engine; the difference lies in the modifiers applied:

* **Melee attacks** use Strength‑based skills and often benefit from reach or weapon traits.  Defenders may respond with **parry**, **block** or **dodge** reactions.  Wound penalties reduce attack and defence values, and encumbrance slows movement or prevents certain manoeuvres.
* **Ranged attacks** use Dexterity and missile skills.  They apply **range band modifiers** and may gain **aim bonuses**.  **Cover bonuses** replace the parry/block bonuses of melee.  **Reload times** insert pacing decisions.  Dodge against ranged is weaker (–2) but a defender can **take cover** as a reaction.

Despite these differences, both attack types resolve identically: compute attacker target, compute defender target, and derive the hit chance via the opposed formula.  This consistency allows players to switch between melee and ranged tactics seamlessly and encourages strategic positioning.

### Wound integration

The injury model ties back into the probability system by modifying attributes and action availability:

* **Heavy and severe wounds** impose –1 or –2 penalties to all physical actions.  These penalties directly reduce the attacker’s target number or the defender’s Dodge Target, lowering their success probabilities.
* **Critical wounds and stagger** may prevent actions altogether unless a roll is made to remain conscious.  This further influences the probability space: a staggered defender is easier to hit because their defence target drops; a staggered attacker has a lower chance to hit.
* **Pressure and encumbrance** interact with wounds: carrying heavy loads or experiencing high pressure raises the effective difficulty of actions.  The same penalty mechanism applies, feeding into the unified target calculation.

By expressing injuries as modifiers rather than a separate subsystem, the wound system integrates naturally with both melee and ranged combat.  Players see the immediate impact of taking damage on their hit chances and reaction options, reinforcing the importance of tactical play.

### Self‑contained combat loop example

To illustrate the integrated system, here is a simplified turn sequence for a melee and ranged exchange:

1. **Initial state** – Archer A (DX 12, Missile Skill 2) and Swordsman B (ST 11, Melee Skill 3) face each other.  B has **Heavy Wound** from a prior hit (–1 all actions).  A is behind **Light Cover** (+1 defence vs ranged) but exposed to melee.
2. **Action declaration** – A decides to **aim** at B; B chooses to **charge and attack**.  Both use a major action this turn.
3. **Resolution order** – Because both act simultaneously, compare SPD; suppose A is faster.  A resolves first:
   * A’s ranged target = DX (12) + Skill (2) + Weapon Acc (2) + Aim Bonus (1) + Range Modifier (0) = **17** → clamp to 17 → P\_A ≈ 95 %.
   * B’s defence vs ranged = base Dodge Target (DX 11) – Heavy wound penalty (1) + Light Cover (1) – ranged dodge penalty (2) = **9** → P\_D ≈ 27 %.
   * Final hit chance = 0.95 × (1 – 0.27) ≈ **69 %**.  A rolls 3d6; on success, damage is applied and B’s wound state may worsen.
4. **B’s melee attack** – If still able, B closes distance and swings:
   * B’s melee target = ST (11) + Skill (3) – Heavy wound penalty (1) = **13** → P\_A ≈ 74 %.
   * A’s defence vs melee = base parry/dodge (DX 12) + cover doesn’t apply – armour penalty (if any).  Suppose A chooses to **dodge**: target = 12 → P\_D ≈ 74 %.
   * Hit chance = 0.74 × (1 – 0.74) ≈ **19 %**.  If B hits, apply damage and update A’s wound state.
5. **Update states** – After resolving both attacks, subtract damage from HP, update wound categories and apply pressure.  Characters may become staggered or incapacitated.  Next turn, they choose new actions based on their altered states.

This example demonstrates how melee and ranged actions use the same calculation pipeline while allowing distinct tactical considerations (aim and cover vs. reach and parry).  Wounds feed back into the loop as penalties, altering future probabilities.

### Why the system is self‑contained

* **Single probability engine** – Every roll in combat uses 3d6 and the same success calculation.  There is no need to learn separate attack, defence or damage mechanics.
* **Modular modifiers** – Range, armour, wounds, encumbrance and cover all translate into simple ±1–±3 adjustments【566123300269821†L74-L83】.  Designers can add new traits or situational effects by assigning small modifiers without altering the underlying math.
* **State‑driven complexity** – Instead of layering on multiple subsystems, the game tracks a few states (wound level, pressure, encumbrance, aim stacks) that feed into the target calculation.  This keeps bookkeeping manageable for both tabletop and digital implementations.
* **Consistency across subsystems** – Spellcasting, social interactions, skills and opposed contests all use the same 3d6 ≤ target structure.  Players can apply the lessons learned in combat to any part of the game, enhancing cohesion.

By integrating ranged, melee and wound mechanics through a unified probability framework, the system remains intuitive and flexible.  It rewards tactical decision‑making without overwhelming players with disparate rules, paving the way for future expansions like magic, social encounters and character creation.
