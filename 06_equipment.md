# Game Rulebook — Section 6: Equipment

## Equipment as Probability Modifiers and Timing Modifiers

Equipment does two things in this system: it shifts target numbers, and it shifts Exposure Windows. A fast weapon (EW –1) makes a character harder to exploit during their attack. Heavy armor (Armor DR +3, armor penalty to RS) makes a character more resistant to damage but more vulnerable to being hit by exposing a smaller defense window. A shield does not just "add to block" — it adjusts the Block Target and provides situational cover against frontal ranged attacks. Focus items and robes modify magic attempt parameters, exposure, or instability; they do not unlock special abilities.

Every piece of equipment is defined with timing and exposure in mind, not initiative. The old trait language that gave weapons "+1 to initiative" or "–1 to initiative" has been replaced entirely with the Exposure Window model. A *fast* weapon creates a smaller EW. A *heavy* weapon creates a larger EW. These are timing facts, not queue-position bonuses.

The design principle is: **for every advantage a piece of gear provides, incorporate a cost or limitation.** Plate armor reduces damage dramatically but makes the wearer slower to react and harder to use without strength training. A great axe hits with devastating force but exposes the wielder for a long window. Equipment creates interesting decisions, not statistical runaway.

---

## Weapons

Each weapon is defined with the following fields:

```python
Weapon = {
    "id": "broadsword",
    "class": "melee",
    "mode": "finesse" | "heavy" | "balanced",
    "accuracy": 0,
    "damage": "1d6+2",
    "parry_bonus": 1,
    "block_bonus": 0,        # only for applicable weapons
    "range_band": None,      # ranged weapons set this
    "reload": False,
    "ammo_capacity": None,
    "min_st": 10,
    "exposure_mod": 0,
    "traits": ["balanced"]
}
```

### Weapon Properties

- **Accuracy (Acc):** Bonus applied to attack target. Most melee weapons grant +0; daggers/rapiers may grant +1; bows and firearms range from +1 to +3.
- **Damage:** Base damage dice and modifiers (e.g., 1d6–1 for a dagger, 1d6+2 for a broadsword, 2d6 for a great axe). Add the attacker's DB on top.
- **Parry Bonus:** Bonus to the Parry Target when this weapon is used to parry. Small agile weapons may grant +1; large unwieldy weapons grant 0 or –1.
- **Min ST:** Minimum Strength to use without penalty (see Section 2 for under-strength penalties).
- **Exposure Modifier:** Adjusts base EW for this weapon's primary attack mode.

### Weapon Examples

| Weapon | Acc | Damage | Parry | Mode | Min ST | EW Mod | Traits |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Dagger | +1 | 1d6–1 | +1 | Finesse | 6 | 0 | fast, thrown, small |
| Rapier | +1 | 1d6+0 | +1 | Finesse | 8 | –1 | precise, reach |
| Broadsword | 0 | 1d6+2 | +1 | Balanced | 10 | 0 | balanced |
| Longsword | 0 | 1d6+2 | +2 | Balanced | 11 | 0 | balanced, reach |
| Battle Axe | –1 | 1d6+3 | 0 | Heavy | 12 | +1 | heavy, cleaving |
| Great Axe | –1 | 2d6+0 | 0 | Heavy | 14 | +2 | heavy, cleaving, two-handed |
| Shortbow | +1 | 1d6+0 | — | Ranged | 8 | 0 | ranged, near–medium |
| Longbow | +2 | 1d6+1 | — | Ranged | 11 | 0 | ranged, medium–far, two-handed |
| Crossbow | +3 | 1d6+2 | — | Ranged | 10 | +2 | ranged, reload, medium–far |

---

## Weapon Traits

Replace all old initiative-based trait language with the following:

| Trait | Effect |
| --- | --- |
| **fast** | Exposure Window –1 for its primary attack mode |
| **heavy** | Exposure Window +2; +2 damage; may enable glancing force damage |
| **precise** | +1 to aimed or carefully prepared attacks |
| **unwieldy** | Exposure Window +1; cannot Counter effectively |
| **reach** | May attack from one range band farther in melee terms |
| **close_only** | Cannot attack beyond Near range |
| **balanced** | No special EW bonus or penalty; reliable parry |
| **thrown** | Can be used as a missile weapon (Near range by default) |
| **shielded** | Improves Block when used with the Block reaction |
| **suppressive** | Near misses can apply Pressure more easily |
| **cleaving** | On a hit that incapacitates the target, may continue to an adjacent enemy (at –2) |
| **two-handed** | Requires both hands; cannot use offhand item or shield simultaneously |
| **reload** | Requires a full action (Extended EW) to reload after firing |

---

## Armor

Armor reduces incoming damage but makes the wearer less agile. Each armor type interacts explicitly with movement, reactions, and RS.

```python
Armor = {
    "id": "chain",
    "armor_dr": 3,
    "armor_penalty": 1,
    "min_st": 11,
    "traits": ["medium_armor"]
}
```

### Armor Effects

- Reduce incoming damage by Armor DR. Total DR is Natural DR + Armor DR.
- Apply armor penalty to Dodge Target.
- Apply armor penalty to Response Speed (RS).
- May reduce SPD if the wearer does not meet Min ST.
- May restrict Sprint, Counter, or certain movement reactions when too heavy (see Section 2 for ST requirements).

### Armor Examples

| Armor | Armor DR | Armor Penalty | Min ST | Traits |
| --- | --- | --- | --- | --- |
| Leather | 1 | 0 | 8 | flexible |
| Studded Leather | 2 | 0 | 9 | flexible |
| Chainmail | 3 | –1 | 11 | medium_armor |
| Scale / Lamellar | 4 | –1 | 12 | medium_armor, bulky |
| Plate | 5 | –2 | 14 | heavy_armor, bulky |
| Mage Robes | 0 | 0 | — | light, unstable (+1 instability cost to spells) |

### Armor Traits

| Trait | Effect |
| --- | --- |
| **flexible** | Reduces penalty when Prone; does not restrict sprint. |
| **bulky** | Reduces SPD by 1; may restrict Counter. |
| **heavy_armor** | Applies armor penalty twice if Min ST not met (see Section 2). |
| **unstable** | Interferes with magic attempts; adds +1 to instability costs. |

---

## Shields

Shields are first-class equipment. They function differently from weapons and armor by improving the Block Target and providing limited protection against frontal ranged threats.

```python
Shield = {
    "id": "heater_shield",
    "block_bonus": 2,
    "cover_bonus_vs_ranged": 1,
    "min_st": 10,
    "traits": ["shield", "frontal"]
}
```

### Shield Effects

- Improve Block Target when using the Block reaction.
- Provide small situational cover against ranged attacks from the front.
- Less effective against flank or rear attacks (Block is limited by facing).
- Cannot substitute for terrain cover in a prolonged missile exchange.

### Shield Examples

| Shield | Block Bonus | vs. Ranged (Frontal) | Min ST | Traits |
| --- | --- | --- | --- | --- |
| Buckler | +1 | 0 | 8 | shield, fast |
| Heater Shield | +2 | +1 | 10 | shield, frontal |
| Kite Shield | +2 | +2 | 12 | shield, frontal, bulky |
| Tower Shield | +3 | +3 | 14 | shield, frontal, heavy, –1 SPD |

---

## Item Schema (Non-Weapon)

Other items are containers of limited-use effects:

```python
Item = {
    "id": "binding_shard",
    "uses": 3,
    "effects": [
        {
            "type": "modifier",
            "target": "bind_action",
            "value": +2
        }
    ]
}
```

### Item Examples

| Item | Uses | Effect |
| --- | --- | --- |
| Healing Potion (Minor) | 1 | Closes 1 Light Wound; restores ~5 HP. Standard action to use. |
| Healing Potion (Major) | 1 | Closes 1 Heavy Wound; restores ~10 HP. Slow action to use. |
| Focus Crystal | 3 | +1 to a Magic Attempt Target for 1 attempt; reduces Instability gain by 1. |
| Smoke Bomb | 1 | Creates Heavy Cover in Near zone for 2 rounds. Fast action to throw. |
| Binding Shard | 3 | +2 to a bind or grapple action. |

---

## Equipment Slots

Each character may equip:

- One main weapon
- One offhand item (shield, second weapon, or focus item)
- One armor set
- Up to three utility items

If using a two-handed weapon, the offhand slot is occupied by that weapon.

---

## Item Design Guidelines

1. **Balance bonuses with drawbacks.** For every advantage a piece of gear provides, incorporate a cost or limitation. This keeps scenarios from being trivialised by single items.
2. **Keep modifiers small.** Equipment bonuses should typically range from ±1 to ±3 to fit within the 3d6 bell curve.
3. **Emphasize traits.** Traits expand the tactical toolkit by modifying parameters, timing, and positioning rather than by granting discrete abilities.
4. **Narrative consistency.** Gear should fit the game's world and tone. Unusual items should enhance, rather than derail, the story.
5. **Timing over queue.** All weapon traits affecting speed are expressed as EW modifiers, not initiative bonuses.
