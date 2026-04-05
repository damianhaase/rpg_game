# Game Rulebook — Section 1: Introduction

## Probability System Overview

This rulebook governs a tactical fantasy role-playing game that draws from **Tunnels & Trolls** (TNT), **The Fantasy Trip** (TFT), and **GURPS**. Every mechanical rule in this system ultimately reduces to a single probability question: *what is the chance this action succeeds given current conditions?* Understanding that question is understanding the game.

The probability model is a **3d6 bell curve**. Rolling three six-sided dice and summing the result produces values from 3 to 18, with the mass of outcomes clustered around 10–11. This distribution means that moderate skill bonuses (+1 or +2) have significant impact near the centre of the curve, while extreme values (3 or 18) are genuinely rare. Combat, spellcasting, social interaction, and skill checks all flow through this same engine, so every lesson a player learns in one context applies across the whole game.

The rules are written so that each section explains not just *what* to roll but *why* the formula is shaped the way it is. Each section opens with a preamble describing how that subject plugs into the probability system and what design theory governs it.

---

## Design Goals

- **Transparency:** Players see the probabilities underlying each action so they learn how the system works. A digital implementation will handle dice and bookkeeping behind the scenes, presenting intuitive descriptions and choices.
- **Tactical depth:** The design incorporates positional effects, exposure windows, reaction budgets, and commitment states. Combat feels both strategic and cinematic.
- **Computational readiness:** Rules are structured so they can be translated into pseudocode and then working code. Formulas are explicit; modifiers are small and bounded; outcomes are deterministic once probabilities are resolved.
- **Coherence:** One resolution engine governs everything. There is no separate initiative subsystem, no separate ranged subsystem, and no separate magic subsystem. All actions create exposure, and all exposure is resolved through the same timing and probability model.

---

## Core Resolution Mechanic

**Dice:** 3d6 for all resolution checks.

**Skill and Attribute Checks:** Each character has numerical attributes and skills. When acting, roll 3d6 and succeed if the result is ≤ the relevant effective target number (attribute + skill + modifiers). Otherwise the action fails.

**Opposed Rolls and Margins:** In contested situations both parties roll. The result is measured in **margin of success** (effective target − roll). Higher margins win; ties produce partial success. This margin comparison is the canonical resolution method used throughout the rules.

If an implementation wants to display a quick estimated hit chance in a UI, it may show a simplified approximation based on the attacker and defender targets. That approximation is only an aid for presentation; it is not the rules engine.

**Critical Results:** A natural 3 or 4 is a critical success. A natural 18 is a critical failure. A natural 17 is a near-miss failure. Specific consequences are defined section by section.

---

## Implementation Framework

The following pseudocode outlines the core loop. It is intentionally high-level; each section expands on the relevant details.

```python
class Character:
    def __init__(self, name, stats, hp, armor, state):
        self.name = name
        self.stats = stats        # ST, DX, CON, IQ, WIL, and derived values
        self.hp = hp
        self.armor = armor        # Armor DR; Natural DR is derived from CON
        self.state = state        # position, commitment, wound, pressure
        self.reaction_budget = 0  # recalculated each round from IQ

    def choose_intent(self, enemies, allies):
        return intent

    def get_reaction_options(self, enemy_action):
        # legal reactions depend on RB, RS, commitment state, and EW
        return list_of_reactions

    def apply_damage(self, damage):
        reduced = max(0, damage - self.armor)
        self.hp -= reduced
        if self.hp <= 0:
            self.state = 'down'

class Action:
    def __init__(self, actor, target, action_type, weapon=None):
        self.actor = actor
        self.target = target
        self.action_type = action_type
        self.weapon = weapon
        self.exposure_window = self.calculate_ew()
        self.base_target = self.calculate_base_target()

    def calculate_ew(self):
        # based on action type, weapon traits, commitment state
        return exposure_window

    def calculate_base_target(self):
        return compute_target(self.actor, self.weapon, self.target)

    def resolve(self):
        roll = roll_3d6()
        margin = self.base_target - roll
        success = (margin >= 0)
        return success, margin
```

The overall **Game Loop**:

1. Each character declares one primary intent (Action).
2. Exposure Windows are calculated for all declared actions.
3. Characters with sufficient Response Speed and remaining Reaction Budget may react.
4. All actions and reactions resolve via 3d6 rolls.
5. Apply damage, pressure, wound state, and position updates.
6. Recalculate derived values and begin the next round.

---

## Document Structure

This rulebook is split into subject-oriented sections. Each section governs a self-contained slice of the system and opens with a preamble explaining how that subject connects to the probability engine.

| File | Contents |
|------|----------|
| `01_introduction.md` | This document — design goals, core mechanic, structure |
| `02_attributes_and_derived_stats.md` | Attributes, derived statistics, formulas (including natural DR, movement) |
| `03_turn_structure_and_actions.md` | Rounds, exposure windows, actions, reactions, flanking, grapple, disengage |
| `04_combat_resolution.md` | Attack targets, margins, ranged combat, worked examples |
| `05_damage_wounds_conditions.md` | Damage model, wound categories, status effects, pressure |
| `06_equipment.md` | Weapons, armor, shields, traits, equipment schema |
| `07_magic.md` | Instability-based magic system |
| `08_skills_and_progression.md` | Skill ratings, proficiency categories, advancement |
| `09_encounter_and_exploration.md` | Surprise, rest/recovery, monster stat blocks, light, terrain, victory/defeat |
