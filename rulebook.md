# Game Rulebook (Draft Version)

## Introduction

This rulebook describes the core mechanics of a planned tactical fantasy role‑playing game that mixes elements from **Tunnels & Trolls** (TNT), **The Fantasy Trip** (TFT) and **GURPS**.  The primary goals are:

- **Transparency:** Players initially see the probabilities underlying each action so they learn how the system works.  As the game matures, the computer will handle all dice rolling and bookkeeping behind the scenes while presenting the player with intuitive descriptions and choices.
- **Tactical depth:** The design incorporates positional effects, moment‑to‑moment choices, and reactions to enemy actions, making combat feel both strategic and cinematic.
- **Computational readiness:** The rules are structured in a way that they can later morph into pseudocode and then into working code for a digital game.  A 3d6 probability distribution is used for most checks because it approximates a bell curve (similar to GURPS success rolls)【357966311584499†L53-L55】.

## Core Resolution Mechanic

- **Dice:** The system uses *3d6* (three six‑sided dice) for most resolution checks.  A roll of 3d6 produces a roughly bell‑shaped distribution and aligns with GURPS‑style success rolls【357966311584499†L53-L55】.  Rolling 3d6 is straightforward for a computer to simulate.

- **Skills and Attributes:** Each character has numerical attributes (e.g., Strength, Dexterity, Constitution/Endurance, Intelligence, etc.) and may have specific skills (weapon skills, magic, etc.).  When a character performs an action, they roll 3d6 and succeed if the result is less than or equal to the relevant skill or attribute after modifiers; otherwise the action fails.【357966311584499†L53-L55】

- **Opposed Rolls and Degrees of Success:** In opposed situations (e.g., two swordsmen trying to strike/evade), both parties roll 3d6 against their effective skill.  The result is measured in **margin of success/failure** (effective skill minus roll).  Higher margins win contested rolls; ties or near‑ties may produce partial success.

## Character Stats and Condition

### Attributes

*These may expand or be refined as the game develops.*

- **Strength (ST):** Governs melee damage and physical feats.
- **Dexterity (DX):** Governs accuracy with weapons, ability to evade, and initiative order if needed.
- **Constitution/Endurance (CON):** Determines health pool and resilience against fatigue or poison.
- **Intelligence (IQ):** Governs magic, strategy, and some reactions.
- **Morale/Will:** Handles resistance to fear or intimidation.

### Secondary Stats and Derived Values

- **Health Points (HP):** Based on ST and CON; when HP falls to zero the character is down.
- **Stamina/Fatigue:** Certain actions cost stamina; when exhausted, penalties apply or actions become impossible.
- **Armor and Damage Reduction (DR):** Armor reduces incoming damage according to its rating.

### Derived Statistics: Calculations and Examples

Although the list above names the most important secondary values, the system also defines **how** to compute them from a character’s core attributes.  This section formalizes those calculations.  Designers may adjust these formulas for balance, and future supplements may add special cases (for example, racial templates that grant bonus HP or alternative carrying capacity).  When testing the game, treat these formulas as **default** values.

#### Speed (SPD)

Speed governs how far a character can move in one five‑second turn and influences initiative when simultaneous actions occur.  It combines physical quickness and endurance:

```
SPD = ⌊ (DX + CON) / 4 ⌋
```

where `DX` is Dexterity and `CON` is Constitution/Endurance.  The result is rounded down.  A typical human with DX 10 and CON 10 therefore has SPD 5.  A high‑dexterity rogue (DX 14, CON 11) would have SPD 6.  Encumbrance and armor may reduce SPD (see Load below).  A character with SPD 0 can no longer move under their own power.

#### Carrying Capacity (Load)

Characters can carry gear and treasure, but doing so slows them down.  Comfortable load (the amount you can carry without penalties) is proportional to Strength:

```
Comfortable Load (in kg) = ST × 5
Maximum Load (in kg)     = ST × 15
```

Carrying up to the comfortable load imposes no penalty.  For every **25 % of comfortable load** beyond that, reduce SPD by 1.  If a character carries more than their comfortable load, they are *encumbered*: SPD is halved (minimum 1), reaction options are reduced, and some actions (such as Evade or Counter‑attack) may be unavailable.  A character cannot move or act if they exceed the maximum load.

#### Damage Bonus (DB)

Strength translates into extra damage in melee.  Damage Bonus is added to a weapon’s base damage or unarmed damage.  It is defined relative to an average Strength of 10:

```
DB = ⌊ (ST − 10) / 2 ⌋
```

For ST 10 or 11, DB = 0.  For ST 14, DB = +2; for ST 8, DB = −1 (minimum −2).  Unarmed attacks use a base damage of 1d6 + DB.  Weapon classes (dagger, sword, axe, spear, etc.) add their own damage dice on top of DB; see **Weapons** for examples.

#### Hit Points (HP)

A character’s health is mostly determined by their Constitution/Endurance.  Hit Points represent how much damage they can take before collapsing:

```
HP = CON × 2
```

For example, a brawny warrior with CON 12 has HP 24.  Some game variants fold Strength into HP, in which case a more robust formula is:

```
HP = 2 × ⌊ (ST + CON) / 2 ⌋
```

but the simpler CON‑based calculation is recommended for clarity.  Traits, species templates, or magic can modify HP up or down.  When HP drops to zero, the character is *downed*; further damage may cause death (see **Damage and Wounds**).

#### Magic Points (MP)

Magic Points fuel spells and supernatural abilities.  They are primarily a function of Intelligence:

```
MP = INT × 2
```

A wizard with INT 13 has MP 26.  Will and special talents may provide bonus MP.  Depleting MP does not injure the character but may cause fatigue if spells draw on HP as a secondary resource.

#### Pressure Resistance (PR)

Pressure (fear, exhaustion, morale stress) accumulates during combat.  Pressure Resistance determines how much pressure a character can absorb before becoming **Shaken** or **Broken**.  PR combines willpower with physical toughness:

```
PR = WIL + ⌊ CON / 2 ⌋
```

Here `WIL` is the Morale/Will attribute.  A knight with WIL 12 and CON 11 has PR 17.  When forced to resist a pressure effect (intimidation, pain, overwhelming odds), roll 3d6 ≤ PR to resist.  Some creatures or player characters may have *Pressure Thresholds* (e.g., Slightly Shaken at PR/2, Panicked at PR/4) that determine when they suffer penalties; those thresholds are described in **Pressure Effects**.

#### Defense Value (DV)

Defense is not a fixed statistic but is recalculated whenever an attack occurs.  The baseline used in this system follows GURPS‑style active defense:

```
DV = 9 + DX + Relevant Skill ± State Modifiers
```

The “relevant skill” might be Shield, Acrobatics (for dodging), or Weapon skill (for parrying) depending on the chosen reaction.  Modifiers account for stance (Prone, Behind Cover), pressure state (Evading, Committed), and environmental effects.  When an attacker rolls to hit, they compare their own attack margin of success against the defender’s DV; the difference determines whether the attack lands.  Because DV is situational, it is not listed on the character sheet as a static number; instead, the computer calculates it each time based on the current intent and reaction choice.

#### Damage Resistance (DR)

DR reflects how much damage a character can shrug off before it reduces HP.  It has two components: **natural** DR from tough skin or Constitution, and **armor** DR from equipment.  Humans and similar creatures have little natural DR: for every two full points of CON above 10, gain +1 natural DR (e.g., CON 14 → +2).  For every two points of CON below 10, natural DR drops by 1 (minimum 0).  Thus a soldier with CON 12 has DR 1 before armor.  Armor pieces contribute additional DR according to their material and coverage; these stack with natural DR.  When damage is inflicted, subtract DR from the incoming damage roll (minimum damage of 1).  Magic or piercing attacks may ignore some or all DR.

#### Other Derived Values

Characters also rely on a collection of *secondary statistics* that are calculated from the primary attributes.  These values govern endurance, reflexes, movement, and resistances.  Making the underlying math explicit helps both designers and players understand how changes to attributes ripple through the rest of the character.

##### Stamina (Fatigue Points, FP)

Stamina measures how much physical or mental effort a character can expend before tiring.  Running, dodging, climbing, spellcasting, and other intensive actions cost FP.  When Stamina reaches zero, the character suffers penalties to movement and attack rolls and cannot make certain reactions until they rest.

The default formula ties Stamina to Constitution:

```
FP = 2 × CON
```

For example, a character with CON 11 has **FP 22**.  This mirrors the HP formula and keeps endurance proportional to overall fitness.  Designers may choose to fold Speed into Stamina for agile characters (e.g., `FP = 2 × CON + ⌊SPD / 2⌋`), but the simple CON‑based calculation is recommended for the base game.  Stamina recovers at a rate of **1 FP per minute** of complete rest, **1 FP per 5‑second turn** if performing only light actions, and does not recover while sprinting or fighting.  Special abilities, spells, or race traits may modify FP or recovery.

##### Initiative (Basic Speed and Turn Order)

Initiative determines who acts first in each 5‑second combat turn.  It is derived from the Speed and Dexterity attributes:

```
Initiative Bonus = SPD + ⌊ DX / 2 ⌋
```

At the start of combat, each participant rolls **3d6 + Initiative Bonus**.  Higher totals act earlier in the order.  Rolling exactly your Initiative Bonus counts as an automatic **first** position for that turn (representing perfect anticipation).  On ties, compare SPD; if still tied, compare DX; if still tied, simultaneous actions occur.  Because Initiative is re‑rolled each turn, faster characters tend to act first but can be surprised by slower foes.

##### Movement (Basic Move)

Movement speed during a 5‑second turn depends on Speed.  A simple conversion is used:

```
Move (metres per turn) = SPD × 2

Move (hexes per turn)  = SPD ÷ 1.5 (round up)
```

Thus a character with SPD 10 can move 20 metres or roughly 7 hexes in one turn if they spend their action on movement.  Armour, encumbrance, rough terrain, or being **Shaken** can reduce movement.  Sprinting (a manoeuvre) adds +50 % to Move but costs **1 FP** per sprinting turn.

##### Pressure Thresholds and Resistance

While Pressure Resistance (PR) was introduced above, the system also uses *thresholds* to model how stress accumulates.  Divide PR into fractions to determine when penalties apply:

- **Calm:** Above ¾ of PR.  No penalty.
- **Uneasy:** Between ½ and ¾ of PR.  –1 to attack and defence checks.
- **Shaken:** Between ¼ and ½ of PR.  –2 to checks; may not perform **Commit** manoeuvre.
- **Panicked/Broken:** Below ¼ of PR.  –4 to checks; may only **Evade** or flee.

Each failed Pressure roll reduces current PR by an amount equal to the margin of failure.  Successful morale checks restore **1** PR; resting outside of combat restores PR at a rate of **1 per minute**.  Magic or leadership abilities can restore PR more quickly.  Designers may modify threshold fractions to adjust overall lethality and tension.

##### Resistances (Saving Throws)

Several effects require special resistance rolls.  These are analogous to saving throws in other systems but are computed from the core attributes so that resilient characters excel at resisting hazards.

| Resistance | Formula | Usage |
|-----------|---------|-------|
| **Poison/Disease** | `3d6 ≤ CON + WIL` | Resist toxins, illness, and drugs. |
| **Magic/Enchantment** | `3d6 ≤ INT + WIL` | Resist spells that charm, control or alter the mind/body. |
| **Fear/Terror** | `3d6 ≤ WIL + ⌊CON/2⌋` | Resist fear effects; penalties equal to Pressure thresholds apply. |
| **Illusion/Deception** | `3d6 ≤ INT + PER` | See through disguises and illusionary effects. |

If a resistance roll succeeds by 5 or more, the character is unaffected; a failure by 5 or more may impose an extra penalty or condition at the GM’s discretion.  Items, spells, and species traits may add bonuses or penalties to these rolls.

##### Encumbrance and Load Limits

Carry capacity influences movement and some actions.  Define **Encumbrance Levels** based on Strength (or Strength bonus if you include ST as an attribute).  A simple table looks like:

| Encumbrance Level | Maximum Load | Move Multiplier | Notes |
|------------------|-------------|-----------------|------|
| **Light** | `ST × 5 kg` | ×1 | No penalty. |
| **Medium** | `ST × 10 kg` | ×0.75 | –1 to defence checks. |
| **Heavy** | `ST × 15 kg` | ×0.5 | –2 to defence checks; +1 FP cost per turn. |
| **Overloaded** | Above `ST × 15 kg` | ×0.25 | –4 to checks; cannot sprint. |

If using the variant without a separate ST attribute, substitute **CON** for ST in the table.  The designer may refine these multipliers based on playtesting; the values above reflect typical human capabilities and scale to other species by adjusting the multiplier.

##### Skill Proficiencies and Effective Skill (preview)

The system will include a wide range of skills (Swordplay, Athletics, Observation, Arcane Lore, etc.).  Each skill is rated by a **rank** that represents training: **Untrained**, **Novice** (+0), **Competent** (+2), **Proficient** (+4), **Expert** (+6), **Master** (+8).  The rank bonus is added to the relevant attribute to form the **Base Skill**.  Your final target number to succeed at a task is the *Effective Skill*:

```
Effective Skill = Base Skill + Equipment Bonus + Circumstance Bonus − Penalties

Base Skill = Rank Bonus + Relevant Attribute
```

The relevant attribute is usually **DX** for physical skills (Athletics, Melee Weapons, Stealth), **INT** for knowledge skills (Arcane Lore, Medicine), **PER** for perception skills (Investigation, Awareness), and **CHA** for social skills (Leadership, Persuasion).  Equipment bonuses come from quality tools or masterwork weapons.  Circumstance bonuses cover situational advantages (high ground, favourable weather); penalties include pressure, wounds, poor lighting, or improvised tools.  A roll of **3d6** equal to or under *Effective Skill* means success.  Critical success (3–4) may grant an additional benefit; critical failure (18) may cause mishaps.  A full skill list and detailed rules for training and advancement are forthcoming.

These formulas ensure that derived statistics scale sensibly with the 3d6 bell curve while leaving room for growth through experience, magic, and gear.  They provide both players and game designers with clear, predictable numbers while still supporting creative play through modifiers and narrative decisions.

### Status Effects

Characters can be affected by conditions that modify their actions and available reactions:

- **Stunned:** Cannot perform complex actions; reactions limited to dodging or blocking.
- **Prone:** Lying on the ground; penalty to attacks, easier to hit.
- **Grappled:** Limited movement; may attempt to break free.
- **Frightened:** Morale reduces; may flee or freeze.

## Position/State System

Positional tactics are central to the game.  Each character’s *state* is described by two orthogonal properties:

1. **Position (cover/exposure):**
   - **Standing:** Default state; no bonuses or penalties.
   - **Prone:** Voluntarily drop (dodge) or as a result of knock‑down; harder to hit at range but easier to hit in melee.
   - **Behind Cover:** Partial or full cover; incoming attacks have lower hit probability; leaving cover costs movement.

2. **Momentum/Pressure State:** Reflects how committed a character is to movement or attack.  It influences how susceptible they are to enemy reactions.

   - **Neutral:** Balanced stance with no active pressure.  Standard defensive position; moderate chance to evade or shift.
   - **Moving:** Character is actively repositioning; better chance to evade some attacks but cannot launch strong attacks.
   - **Committed:** Character is fully committed to attacking or heavily pressing the opponent; gains bonuses to attack but suffers penalties to defense if attacked by others.
   - **Evading:** Character is focusing on defense and evasion; higher chance to avoid attacks but cannot attack effectively.
   - **Broken/Off‑balance:** Result of pressure pressure; penalties to all actions and reactions.

**Transitions:**  Characters usually start neutral.  They declare an intent (e.g., attack, move) which shifts their pressure state.  Critical successes or failures can force them into off‑balance or broken states.

## Pressure Effects

Pressure is a meta‑mechanic describing how much psychological and physical pressure a character is under.  It influences decisions about reactions and actions.

- **Pressure Gain:** Occurs when a character is aggressively attacked, flanked, or suffers repeated damage.  Pressure can also be raised by environmental hazards or morale shocks.
- **Effects:** High pressure penalizes skill rolls, may cause the character to choose safer actions (evade, defend) and can eventually lead to a *panic state*.
- **Pressure Release:** Can occur via successful morale checks, rally actions, or elimination of threats.

## Turn Structure

The game uses **five‑second turns** for clarity and to allow the player to plan without micromanaging every second (GURPS uses 1‑second turns【357966311584499†L53-L55】, but for our purposes a slightly longer turn improves narrative flow).  Each turn has two phases:

1. **Intent Declaration Phase**
   - At the start of the turn, each character chooses an *intent* (attack, move, reposition, etc.).  In a digital game, the AI or player selects the action via a menu.
   - The system determines the baseline probabilities for success, based on skills, weapons, range, position, and state.

2. **Reaction/Resolution Phase**
   - After all intents are declared, characters may get an opportunity to **react** to an opponent’s action.  Reaction options depend on the initial intent and pressure state.
   - The player can choose to accept the default intent (no reaction) or select one of the available reactions (e.g., dodge, block, counter‑attack).  Reactions modify the probability distributions of success/failure for all participants and may have costs (e.g., stamina, pressure gain).  Choosing *not to react* leaves the original probabilities unchanged.
   - Actions then resolve, damage is applied, states and positions are updated, and the next turn begins.

**Note:**  The reaction system adds a layer of depth.  For instance, after committing to a heavy attack, a character might still react with a quick parry against a surprise thrust, but this reaction will impose a penalty on the original attack since the fighter must split attention.

## Actions and Reactions

### Primary Actions (Intent Options)

- **Move/Reposition:** Adjust position, gain or leave cover, close or open distance.  Modifiers: terrain difficulty, encumbrance.
- **Attack:** Strike with a weapon or cast a spell at a target within range.  Variants include thrusts, slashes, shots, and spells; success depends on DX, skill, and target state.
- **Evade/Defend:** Focus entirely on evading or blocking; improves chance to avoid attacks at the cost of offensive output.
- **Special:** Use an item, reload, perform a ritual, attempt to rally allies, or other non‑combat actions.

### Reaction Options

Reactions are more limited than primary actions and depend on the current intent:

- **Dodge / Parry / Block:** Attempt to avoid or deflect an incoming attack.  Requires DX or shield skill; successful dodge decreases chance of being hit but may reduce your own attack effectiveness if taken after committing to an attack.
- **Counter‑attack / Riposte:** If your intent was offensive, you may choose to counter at the risk of taking more damage if you fail.
- **Shift / Sidestep:** A small reposition to avoid being flanked or to gain a better angle.  May break your commit or move states.
- **Hold:** No reaction; proceed with the planned action.

**Reaction Constraints:**

- A character cannot switch from a fully committed attack to an entirely different action (e.g., from *Commit* to *Evade*) within the same turn without severe penalties.  Small adjustments (e.g., adding a block while attacking) are allowed but reduce attack success.
- An exhausted or stunned character may have no reaction options available.

### Consequences of Reactions

Each reaction alters the underlying success probabilities.  For example:

- **Dodge**: Reduces the attacker’s chance of hitting by a certain margin, but if the defender was attacking, their own attack chance decreases due to divided attention.
- **Parry**: Provides moderate defense while maintaining some attack potential.  A failed parry may leave the defender off‑balance.
- **Counter‑attack**: Increases your chance to deal damage if the opponent misses but increases your exposure.
- **Shift**: Adjusts position; may reduce chance of being hit by follow‑up attacks.

A digital interface should present these probability adjustments clearly: when offering reaction choices, the UI shows the new success/failure odds relative to the initial intent so the player understands the trade‑offs.

## Damage and Equipment

- **Weapon Classes:** Weapons are grouped into broad classes (daggers, swords, axes, polearms, bows, etc.).  Each class has a base damage range inspired by GURPS.  For example, a dagger might deal *1d6–1* (average ~2.5) while a broadsword might deal *1d6+2* (average ~5.5).  These ranges are subject to balancing.
- **Armor:** Provides *Damage Reduction (DR)*.  Chainmail may offer DR 3, plate armor DR 5–6, etc.  Lightweight armor reduces DR but offers higher mobility.
- **Shields:** Provide bonus to block reactions and may reduce pressure gain.
- **Items:** Potions, scrolls, and traps can be used as special actions.  Their numerical effects will be specified later.

Damage is subtracted from a character’s HP after DR.  Critical hits may bypass some armor or inflict status effects.

## Skills and Proficiency (Provisional)

Many of the rules above refer to a character’s **skill** or **proficiency** with a weapon.  In earlier drafts this was left as an undefined concept.  To avoid leaving a gap in the system, this section defines a simple provisional framework for skills.  These rules will be refined as we expand the game’s character‑creation options, but they provide enough structure to play and to interpret hit chances.

1. **Skill Ratings:** Characters have one or more **weapon skill ratings** corresponding to broad weapon classes—**Small Blades**, **Axes**, **Bows**, **Polearms**, and so on.  A skill rating represents your training and familiarity with that class and is expressed as a target number on 3d6.  Starting characters typically have ratings in the **8–14** range:
   - **10** – Basic competence: you know how to use the weapon without hurting yourself.
   - **12** – Trained proficiency: you are a practiced fighter.
   - **14+** – Expert mastery: you handle the weapon with exceptional precision.
   Your skill rating functions as a **bonus to your base to‑hit chance** when using a weapon of that class (see the *Hit Probability and Resolution* section).

2. **Defaulting When Untrained:** If you attempt to use a weapon class for which you have **no skill**, you default to **Dexterity (DX) – 4**.  For example, a hero with DX 12 picking up a battleaxe but lacking the **Axes** skill would treat their effective skill as 8.  You may still attempt the action; your roll is just much harder.

3. **Assigning Skills:** At character creation you assign a limited number of weapon skills to reflect your background.  A novice might start with one skill at 11 or 12.  A seasoned fighter could have two or three skills in the 12–14 range.  Training, experience, or magical enhancement may increase these ratings later.  Non‑combat skills (knowledge, magic, climbing, etc.) are not yet defined; until they are, you default to the relevant attribute minus 4 for any unlisted task.

4. **Proficiency Categories:** To simplify bookkeeping, weapons are grouped into broad categories.  **Small Blades** covers daggers, shortswords, and rapiers; **Axes** covers hatchets and battleaxes; **Polearms** covers spears, halberds, and similar two‑handed sticks; **Bows** covers longbows and shortbows.  When wielding a weapon, use the skill for the category that matches it best.  Future expansions may split or add categories, but the principle is to keep the list manageable.

5. **Skill vs. Attribute:** In line with GURPS and TFT, **skill is at least as important as raw Dexterity**.  A low‑DX character with a high skill rating can outfight a high‑DX character who swings wildly.  Because the game uses 3d6, each point of skill has a meaningful impact on your success probability.  Designers can tune typical starting skills and maximum values to adjust game difficulty and pacing.

6. **Provisional Nature:** These rules are intentionally lightweight.  When the full character‑creation system is introduced, we will revisit skills and proficiencies, expand the list beyond combat, and address how characters learn and improve.  For now, treat this as a temporary but functional backbone that ensures hit probability calculations are not incomplete.

## Example Turn Sequence (2v1 Combat)

Below is a narrative example illustrating a 2v1 fight between a hero (**Hero**) and two enemies (**Goblin A**, **Goblin B**).  The probabilities are hidden once the player knows the system, but shown here to illustrate the mechanics.

1. **Start of Turn (Intent Declaration)**
   - **Hero** (state: neutral, position: standing): chooses **Attack Goblin A** with a broadsword.  Base hit chance: 62%; damage: 1d6+2.
   - **Goblin A** (neutral): chooses **Attack Hero** with a dagger.  Base hit chance: 50%.
   - **Goblin B** (neutral): chooses **Flank** to move behind the hero.  Movement success: automatic if unopposed.

2. **Reaction Decision**
   - The system checks whether any characters react.  Because Goblin B is flanking, the hero can react to this second threat.  UI shows:
     - **No Reaction**: Hero continues attacking Goblin A; Goblin B gets a free attack next turn.
     - **Shift to Defend**: Hero spends part of his action to watch the flank; his attack chance drops to 50% but Goblin B’s later attack chance will be reduced.
     - **Dodge Goblin A**: Hero abandons his attack and focuses entirely on evasion; Goblin A’s hit chance drops to 20% but the hero does no damage.
   - **Hero** chooses **Shift to Defend**.
   - **Goblin A** may choose a reaction to the hero’s shifting (e.g., try a quick stab).  Suppose Goblin A does **Counter‑attack**, increasing its hit chance to 55% but increasing risk.

3. **Resolution**
   - Rolls are performed in an order determined by initiative (DX).  
   - **Hero vs Goblin A**: Hero’s modified hit chance is 50%; he rolls 3d6 against his effective skill and succeeds with a margin of 2.  Goblin A’s parry fails; Hero deals 1d6+2 damage (rolls a total of 7).  Goblin A’s DR 1 chain shirt reduces damage to 6; Goblin A is badly wounded.
   - **Goblin A** counter‑attacks with a 55% chance.  Hero’s shift reduces his defense; he fails to parry and takes 1d6–1 damage (rolls 3).  DR reduces to 2; Hero loses 1 HP.
   - **Goblin B** completes the flanking move.  Because the hero reacted, Goblin B’s attack next turn will have only a +10% instead of +20% bonus.
   - Update states: Goblin A enters **Off‑balance** due to damage; Hero remains **Neutral** but with small pressure; Goblin B is now in a flanking position.

4. **Next Turn**
   - New intents are declared, considering new positions and health.

This example demonstrates how reactions influence probabilities, damage, and positioning.

## Implementation Framework (Pseudocode Outline)

The following is a high‑level pseudocode description to guide eventual coding.  It assumes a turn‑based system with objects representing characters, actions, and reactions.

```python
class Character:
    def __init__(self, name, stats, hp, armor, state):
        self.name = name
        self.stats = stats  # includes ST, DX, CON, etc.
        self.hp = hp
        self.armor = armor  # Damage Reduction (DR)
        self.state = state  # position/momentum state
        self.pressure = 0

    def choose_intent(self, enemies, allies):
        # Player or AI chooses an action (attack, move, evade, special)
        return intent

    def get_reaction_options(self, enemy_action):
        # Determine legal reactions based on current state and intent
        return list_of_reactions

    def apply_damage(self, damage):
        reduced = max(0, damage - self.armor)
        self.hp -= reduced
        if self.hp <= 0:
            self.state = 'down'

class Action:
    def __init__(self, actor, target, type, weapon=None):
        self.actor = actor
        self.target = target
        self.type = type  # e.g., 'attack', 'move'
        self.weapon = weapon
        self.base_chance = self.calculate_base_chance()

    def calculate_base_chance(self):
        # Use actor.stats, target.state, weapon modifiers, etc.
        return chance

    def resolve(self):
        roll = roll_3d6()
        margin = self.actor.stats['DX'] + modifiers - roll
        success = (margin >= 0)
        return success, margin
```

An overall **Game Loop** would:

1. For each character, call `choose_intent` to obtain an `Action`.
2. Offer reaction options as appropriate, adjusting base chances.
3. Resolve actions based on initiative order (DX or another metric).
4. Apply results (damage, position changes, pressure changes).
5. Update states and check for victory/defeat.

## Hit Probability and Resolution

The attack and defense system boils down to a single **Hit Probability** calculation that mixes your character’s physical aptitude with their training, the weapon you are using, and situational factors. Because this game is ultimately a set of tactical decisions wrapped around dice rolls, understanding how your hit chance is derived is critical both for players and for designers tuning the system. The following subsections explain hit probability from two perspectives.

### Player‑Facing Hit Rules

When you take an action that could harm another character—whether stabbing with a sword or loosing an arrow—you must make a **hit check**. Hit checks use the **3d6 system** described earlier; you succeed if your roll is **less than or equal to** your effective chance to hit.

1. **Determine the Base To‑Hit:**
   - For **melee attacks**, start with your **Dexterity (DX)** and add your **weapon skill bonus**. Highly trained fighters therefore hit more often than novices even with the same DX.
   - For **ranged attacks**, start with the **weapon’s Accuracy (Acc)** rating, add your **skill with that weapon**, and (optionally) a portion of your DX if the design chooses to let DX assist with aim. This reflects that bows and crossbows vary in mechanical precision.

2. **Apply Situational Modifiers:** Once you have a base number, adjust it up or down based on what is happening in the scene. Typical modifiers include:

   - **Target Defensive State:**
     - The target is **Evading**: –3 to hit; they are moving unpredictably and presenting a smaller target.
     - The target is **in a Normal or Static state**: no modifier; they are neither dodging nor committing.
     - The target is **Committed (full offense)** or **Prone**: +1 to +2; they are easier to strike.

   - **Attacker State:**
     - If you are **Commiting**, you gain +1 to hit but suffer –1 to defense on other people’s attacks.
     - If you are **Evading**, you lose –2 to your own hit chances because you are sacrificing offense for defense.
     - **Prone attackers** suffer –4 unless making a thrusting attack that is easier to perform while prone.

   - **Weapon Properties:** Some weapons are easier to land a blow with. A **light rapier** might grant +1 to hit due to its agility, whereas a **heavy flail** might impose –1 because it is unwieldy. These bonuses are folded into your base to‑hit or applied as modifiers depending on the implementation.

   - **Pressure and States:** If the target is **Shaken** or **Pressured** (see the Pressure system above), their defense suffers; you get +1 or more to hit. Conversely, if you are **Fatigued** or **Wounded**, you might take –1 or worse.

   - **Range:** For **ranged weapons**, add –1 per range band beyond the weapon’s optimal distance. At very close range (point blank), you might get +1, but in melee contact ranged weapons can incur big penalties or be unusable.

   - **Cover and Visibility:** Partial cover (tree trunks, doorways) imposes –2 to –4; total cover means you cannot hit at all. Fighting in darkness or against a camouflaged opponent can impose similar penalties.

   These modifiers are guidelines; future equipment, talents, and magic will introduce additional factors. When in doubt, start with a ±1 or ±2 shift for each significant advantage or disadvantage.

3. **Reactions:** After intents are declared, each participant may choose a **reaction** such as Block, Parry, Counter, or Dodge. Reactions occur **after** the base hit chance is declared but **before** the dice are rolled. Taking a reaction adjusts the effective chance:

   - **Block (with shield)**: You add your shield bonus (+2–+4) to your defense; the attacker must subtract that from their to‑hit chance.
   - **Parry (with weapon)**: You add your weapon’s parry rating (usually +1 or +2) but suffer –1 to your own next attack because you had to re‑position your weapon.
   - **Dodge**: You substitute your Evade value for your current state (usually –3 to the attacker’s chance) but cannot make an offensive action this turn.
   - **Counter**: You sacrifice –2 to your own defense in hopes of reversing the attack if the attacker misses. If the attacker fails by 3 or more, you immediately strike back at +1.

   Reactions are optional; if you do nothing, the attacker’s chance remains unchanged, and you save your position for your next action.

4. **Roll and Compare:** Roll 3d6. If the total is **less than or equal to** your final to‑hit value, the attack lands. If it is greater, you miss. Note that extremely high or low rolls can produce **critical successes or failures** (e.g., a natural 3 automatically hits; a natural 18 automatically misses), subject to the optional rules you choose to include later.

5. **Determine Outcome:** If you hit, roll damage as defined by your weapon class and apply it to the target’s Hit Points (HP) after accounting for armor and other defensive effects.

**Example:** A lightly armored thief (DX 12, Small Blade Skill +2) lunges at an orc warrior who is in a normal stance. The thief’s base to‑hit is 14. The orc chooses to parry with a large axe (+2 parry bonus). The thief’s effective to‑hit is now 12. The thief rolls 3d6 and gets 11—success! They hit and then roll damage.

### Design and Balance Rationale

From a design perspective, hit probability serves as the primary way to balance action speed against lethality. The following considerations underpin the numbers above:

**3d6 Distribution:** The bell‑curve distribution of 3d6 means that small bonuses (±1 or ±2) meaningfully change your chance to hit. A character with an effective to‑hit of 10 has only ~50 % success, while 12 yields ~75 % and 14 yields ~90 %. This encourages incremental advantages from positioning, teamwork, and equipment.

**Skill vs. Attribute:** We follow the GURPS principle that skill matters at least as much as raw Dexterity. A DX 10 character with Sword‑14 can out‑fight a DX 14 character with Sword‑10. This allows characters to specialize and encourages variety in builds. However, we cap situational modifiers to prevent runaway stacking (rarely more than ±4 total).

**State and Pressure Interaction:** The state system (Evade, Commit, Prone, etc.) and the Pressure track (Composed → Shaken → Panicked) provide knobs for controlling both hit and defense probabilities. Raising your shield (Evade) reduces your offense but increases your defense; Committing increases offense at the cost of vulnerability. Pressure effects lower defense, giving momentum to the side that lands hits. These interacting systems ensure that combat flow is not purely random and that tactical decisions matter.

**Reactions as Choice:** Unlike some systems where defensive counters are always “on,” we require players (and the AI) to choose whether to react. This has two balancing effects: (a) reactions impose costs (usually to your next action or to your overall momentum), and (b) they present a risk‑reward decision—do you accept a slightly higher chance to be hit now in order to preserve your next attack, or do you block and potentially miss an opening? Clear modifiers (e.g., Block gives the attacker –3) make these trade‑offs explicit to the player.

**Weapon Differentiation:** By assigning modest accuracy bonuses and parry values to each weapon class, we differentiate playstyles without forcing exhaustive tables. Daggers and small blades are quick (+1 to hit, +1 parry) but do modest damage; axes hit hard but are slower (–1 to hit, +2 damage). These bonuses mirror GURPS and TFT while remaining simple.

**Scaling and Future Expansion:** Our baseline numbers (skill 10–14, DX 10–14, modifiers ±1–±3) echo GURPS’s “average human” calibrations. If we add higher‑powered monsters, magic, or hero levels later, we can extend the scale (e.g., skill 16+) while preserving the same probability curve. We also plan to revisit hit probability if we introduce advanced mechanics like called shots, reach advantages, or group maneuvers.

As the system evolves, this section will remain the authoritative source for how to compute hit chances. Designers can adjust base numbers and modifier ranges to fine‑tune the overall lethality and pacing of combat, while players can always see a clear explanation of why their attack hits or misses.

## Expanding the System

This rulebook is a living document.  Future additions will include:

- **Detailed weapon tables** with more granular damage ranges, special effects (bleeding, armor penetration), and minimum strength requirements.
- **Magic system** based on energy points or fatigue, with spells as actions and reactions.
- **Monsters and NPCs** with unique pressure thresholds, reactions, and AI decision trees.
- **Environmental factors** such as light, weather, terrain, and traps.
- **Character progression**, including experience, leveling, and talent trees.

We intend to incorporate further ideas from GURPS, TFT, and TNT as the game evolves, always focusing on clarity for the player and ease of computation.

---

*This document sets out the core principles of a tactical fantasy game engine that melds the simplicity of TNT with the tactical richness of TFT and the granularity of GURPS.  It will serve as the foundation for pseudocode and eventual implementation.*
