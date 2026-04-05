# Game Rulebook — Section 9: Encounter and Exploration Rules

## Preamble: The Frame Around Combat

The probability engine governs what happens when characters are in conflict. But a playable game also needs rules for *how conflict starts*, *what happens in the spaces between fights*, and *what the physical environment does to the numbers*. This section fills those gaps.

Every rule here uses the same 3d6 ≤ target structure as combat. Surprise is a contested Perception vs. Stealth roll. Exploration challenges are skill checks with defined difficulty targets. Rest and recovery are time-gated resource resets. Nothing in this section requires a new dice mechanic — it is the same engine applied to a different phase of play.

---

## Surprise and Ambush

### Determining Surprise

When one group attempts to ambush another, or when a hidden enemy is suddenly revealed, resolve surprise with an **opposed 3d6 check**:

- **Attacker (ambushing):** 3d6 ≤ DX + Stealth Skill + situational modifiers
- **Defender (being ambushed):** 3d6 ≤ IQ + Perception Skill + situational modifiers

| Situation | Modifier |
|---|---|
| Attacker in dim light or foliage | +2 to Stealth |
| Attacker in darkness | +4 to Stealth |
| Attacker moving quickly | –2 to Stealth |
| Defender actively watching for threats | +2 to Perception |
| Defender distracted (eating, reading, etc.) | –2 to Perception |
| Defender asleep | –4 to Perception (or automatic failure) |
| Multiple attackers — noisiest member applies | Use the lowest Stealth roll |

### Surprise Outcomes

| Result | Effect |
|---|---|
| Attacker succeeds, defender fails | **Full Surprise.** Defenders have RS = 0 and RB = 0 for the entire first round. They may not react to any action. |
| Both succeed or both fail | **Alert.** No surprise. Combat begins normally. |
| Defender succeeds, attacker fails | **Foiled ambush.** The ambushers begin round 1 **Off-Balance**. Defenders gain +2 RS against those attackers during the first round and may react normally to their exposure. |

---

## Perception and Detection

Outside of ambush situations, characters may notice hidden threats, traps, concealed passages, or approaching enemies with a **Perception check**:

```
Perception Target = IQ + Perception Skill + situational modifiers
```

The GM sets a difficulty. Suggested target numbers:

| Difficulty | Target | Examples |
|---|---|---|
| Easy | 12 | A poorly hidden goblin; a fresh blood trail |
| Moderate | 10 | A deliberately concealed enemy; a disguised trap |
| Hard | 8 | A professional ambush; a hidden door |
| Very Hard | 6 | A master thief in shadow; a magical illusion |

These are the *defender's* target numbers — lower means harder to notice (the check is harder to succeed). A character who fails a Perception check is simply unaware; they do not know they failed.

---

## Rest and Recovery

### Short Rest (10 minutes)

During a short rest, characters may:
- Recover **FP** fully (Fatigue Points reset to maximum)
- Reduce Pressure by up to **⌊PR / 4⌋** (natural decompression)
- Apply First Aid to one Light Wound per character (stabilize bleeding, no HP gain)

A short rest requires no combat, no sprinting, and no major exertion. If interrupted by an encounter before 10 minutes are up, no recovery occurs.

### Long Rest (1 hour)

During a long rest, characters may:
- Recover FP fully
- Recover **HP** at a rate of **CON per hour** (i.e., one long rest restores CON HP)
- Heal one **Light Wound** completely per character
- Reduce Pressure to zero
- A character with Medicine skill may attempt to treat one Heavy or Severe Wound (3d6 ≤ IQ + Medicine; on success, the wound drops one category)

A long rest requires shelter, safety, and either food/water or a character willing to stand watch.

### Full Recovery (8 hours sleep)

- HP fully restored (unless a Severe or Critical Wound is present — those require days of recovery or magic)
- All Wounds drop one category (Severe → Heavy, Heavy → Light, Light → healed)
- All FP and Pressure fully restored

Critical Wounds do not heal overnight without medical care or magic healing.

---

## Victory and Defeat Conditions

### Encounter Victory

An encounter ends when:
- All enemies are **downed** (HP ≤ 0) or **incapacitated** (failed CON check)
- All remaining enemies **flee** or **surrender** (GM discretion; enemies typically flee when their side reaches fewer than half their starting numbers, or when a leader is killed)
- The party achieves its objective (escaping through a door, holding a position, etc.)

### Defeat and Party Collapse

The party is **defeated** when all player characters are simultaneously downed or incapacitated. If at least one PC remains standing, the encounter continues — even if badly wounded.

**Being Downed:** A character at 0 HP is unconscious and dying. Each round they remain at 0 HP, roll 3d6 ≤ CON. Failure means HP decreases by 1 further. Reaching –CON in HP means death. A successful First Aid action (Standard EW from an ally) stabilizes the character (stops HP loss; they remain unconscious until treated further or given a Healing potion).

**Capture vs. Death:** The GM may rule that downed characters are captured rather than killed, particularly when enemies have tactical reasons to take prisoners. This is a narrative decision.

---

## Monster Stat Block

All creatures use the same attributes as player characters. A monster stat block includes:

```
Name: [Monster Name]
ST:   [value]   DX:  [value]   CON: [value]
IQ:   [value]   WIL: [value]

HP:  [CON × 2]    FP:  [CON × 2]    PR:  [WIL + floor(CON/2)]
SPD: [floor((DX+CON)/4)] RS: [DX + floor(IQ/2)]  RB: [1 + floor(IQ/4)]
WB:  [floor(CON/4)]      DB: [floor((ST-10)/2)]  Natural DR: [floor((CON-10)/2)]

Armor:   [type, Armor DR value, armor penalty]
Weapon:  [name, damage, parry bonus, traits, EW modifier]
Skills:  [weapon skill rank, any other relevant skills]
Traits:  [special abilities]
Tactics: [brief description of how this creature fights]
```

### Example Monster: Goblin Raider

```
Name: Goblin Raider
ST: 7    DX: 11   CON: 8
IQ: 8    WIL: 7

HP: 16   FP: 16   PR: 11
SPD: 4   RS: 13   RB: 3
WB: 2    DB: -2   Natural DR: 0

Armor:   Leather scraps, DR 1, no penalty
Weapon:  Short sword — 1d6–1+DB (avg 2), Parry +1, fast trait (EW –1)
         OR Shortbow — 1d6+0, range Near–Medium, no parry
Skills:  Small Blades Competent (+2), Bows Novice (+0), Stealth Competent (+2)
Traits:  Pack Tactics — if two or more goblins are Flanking the same target,
         each gains an additional +1 to attack (stacks with standard flanking +2).
Tactics: Goblins prefer ambush (Stealth +2). They fight from range when possible,
         closing only when they outnumber the target. They flee when reduced to
         half their number.
```

### Example Monster: Orc Warrior

```
Name: Orc Warrior
ST: 14   DX: 10   CON: 13
IQ: 8    WIL: 10

HP: 26   FP: 26   PR: 16
SPD: 5   RS: 12   RB: 3
WB: 3    DB: +2   Natural DR: 1

Armor:   Chainmail, DR 3, armor penalty –1
Weapon:  Battle Axe — 1d6+3+DB (avg 8.5), Parry 0, heavy trait (EW +2)
         Shield — Block Bonus +2, frontal
Skills:  Axes Proficient (+4), Shield Competent (+2)
Traits:  Tough — once per encounter, when first reduced to 0 HP, make a free
         CON check. On success, remain at 1 HP instead of being downed.
Tactics: Orcs advance directly and Commit on the first attack. They use their
         shield against ranged threats. They do not flee until below ¼ HP.
```

### Example Monster: Dungeon Skeleton

```
Name: Dungeon Skeleton
ST: 10   DX: 9    CON: 10
IQ: 4    WIL: 12

HP: 20   FP: 20   PR: 17
SPD: 4   RS: 11   RB: 2
WB: 2    DB: 0    Natural DR: 0

Armor:   Exposed bone, DR 1 vs slashing, DR 0 vs blunt (blunt weapons bypass)
Weapon:  Rusty Sword — 1d6+1, Parry +1
Skills:  Swords Novice (+0)
Traits:  Undead — immune to Pressure and fear effects; WIL-based resistances
         always succeed; does not bleed; cannot be healed by medicine; magic
         healing requires a Warding/Necromancy spell.
         Slow Mind — RB is capped at 2; cannot Counter.
Tactics: Skeletons advance and attack without tactics. They do not flee.
```

---

## Exploration Rules

### Light and Vision

Characters need light to act without penalty in enclosed environments.

| Light Condition | Effect |
|---|---|
| Full light (torches, daylight) | No penalty |
| Dim light (distant torch, dawn) | –1 to Perception and ranged attacks |
| Near darkness (moonlight, embers) | –2 to all attack and Perception targets |
| Total darkness | –4 to all attacks; Perception checks fail unless using other senses |

**Light sources:** A torch illuminates a Near zone (radius ~3m). A lantern illuminates a Near–Medium zone. Both burn for ~1 hour. Characters with dark vision (species trait) ignore penalties up to near-darkness.

### Terrain and Difficult Ground

| Terrain | Effect |
|---|---|
| Normal floor / open ground | No penalty |
| Rubble, slippery, uneven | –1 SPD; Prone recovery EW +1 |
| Water (wading, knee-deep) | –2 SPD; –1 to DX-based actions |
| Deep water / swimming | SPD halved; most reactions unavailable; FP costs doubled |
| Stairs (combat on stairs) | Uphill: –1 attack; Downhill: +1 attack, –1 defense |
| Mud / deep sand | –2 SPD; Sprint unavailable |

### Doors and Obstacles

| Action | Roll | Notes |
|---|---|---|
| Open an unlocked door | No roll | Costs movement; EW Standard (4) while doing so |
| Break down a stuck door | 3d6 ≤ ST + Athletics | Each attempt costs 1 FP; on fail, door holds |
| Pick a lock | 3d6 ≤ DX + Stealth/Thievery | Difficulty set by lock quality (target 12 to 6) |
| Kick down a door in combat | 3d6 ≤ ST | Extended EW (8); allies may react to protect the breacher |
| Barricade a door | 3d6 ≤ ST + Athletics | Requires heavy furniture nearby; takes ~1 minute |

### Traps

Traps are detected with a Perception check (see above). Difficulty depends on how well-concealed the trap is.

**Disarming a trap** requires 3d6 ≤ DX + relevant skill (Thievery, Engineering) and takes 1–5 minutes. Failure may trigger the trap; failure by 5+ definitely triggers it.

**Triggered traps** resolve as a surprise attack against any character in the trap's area. The trap has its own Attack Target (set by GM) and damage value. The victim's only legal reaction is Dodge (1 RB), if they were not fully surprised.

---

## Victory Rewards (Optional Framework)

The following is a minimal reward structure for test play. Full advancement rules will be defined in a later supplement.

- **Encounter cleared:** Each participant marks one skill that was used meaningfully under pressure. (Used for advancement; see Section 8.)
- **Objective completed:** All participants recover FP fully immediately (adrenaline fading; equivalent to a Short Rest).
- **Treasure:** Equipment found may be looted and used immediately if the character meets Min ST requirements.
- **Level-up trigger:** After 3–5 encounters (GM's discretion), players may increase one skill rank or gain +1 to one attribute. This is deliberately light — full advancement will be codified later.

---

## Encounter Design Guidelines (For GMs and Designers)

For a simple dungeon playtest:

1. **Standard encounter:** 2–4 enemies per PC. Goblins or skeletons are good baseline opponents. One or two should be ranged if possible.
2. **Elite encounter:** 1–2 enemies of roughly equal stats to a PC (e.g., Orc Warriors). One per 2 PCs.
3. **Boss encounter:** One significantly stronger enemy (ST/CON 14–16, Proficient skills, a unique trait) supported by 2–3 minions.
4. **Rest opportunity:** Plan at least one short-rest opportunity between two encounters per dungeon level.
5. **Terrain:** Give each room at least one tactical feature (a column for cover, a stairway for high ground, a pit to push enemies into). The system's cover and positioning rules only matter if the environment creates choices.
